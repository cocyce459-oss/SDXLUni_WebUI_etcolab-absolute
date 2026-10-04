# Absolute Colab Setup — WebUI Forge **NEO** (latest) + SDXL
Repo: `https://github.com/Haoming02/sd-webui-forge-classic` — branch **`neo`** (**the repo default**)

Verified against source on the `neo` branch, last commit **`2026-10-03T14:34:50Z`**
(Classic's last commit is `2026-04-22` — Neo is ~6 months ahead).

---

## 0. Neo vs Classic — the verified delta

| Feature / Pin | **Classic** | **Neo** |
|---|---|---|
| Python | 3.11 (tested 3.11.9) | **3.13 (tested 3.13.12)** |
| Gradio | `3.43.2` | **`4.40.0`** + `gradio_rangeslider==0.0.8` |
| torch | `2.10.0+cu130` / tv `0.25.0` | **`2.13.0+cu130` / tv `0.28.0+cu130`** |
| xformers | `0.0.34` → **requires `torch==2.10.0` exactly** | `0.0.35` → requires **`torch>=2.10`** (looser) |
| numpy | `1.26.4` | **`2.3.5`** |
| pydantic | `1.10.22` | **`2.10.6`** |
| packaging | `26.0` | `26.2` |
| insightface pin | `insightface==0.7.3` | *removed* |
| `requirements_versions.txt` | exists, **empty** | **does not exist (HTTP 404)** |
| `--nunchaku` | no | yes (forces torch `2.11.0+cu130`) |
| `--uv-local-cache` | no | yes (ideal for Colab) |
| `--expandable-segments` | no | yes |
| `--tiled-conv2d` | no | yes |
| `--use-ck-attention` | no | yes (Comfy-Kitchen) |
| `--fast-fp8` | no | yes |
| `--autotune` | no | yes |
| model dirs | `--model-ref`, `--ckpt-dir`, `--vae-dir`, `--lora-dir` | `--model-ref`, `--data-dir` (early parser) **+** `--ckpt-dirs`, `--lora-dirs`, `--vae-dirs`, `--text-encoder-dirs` |
| `--disable-safe-unpickle` | yes (no-op, added *for* ADetailer) | **removed** |

**New model families in Neo** (vs Classic's SD1/SDXL-only): `sdxl`, `qwen`, `flux1`, `flux2`,
PiD 1.5, Nunchaku SVDQ, Wan VAE. Plus the **Comfy-Kitchen** attention backend.

> **SDXL note:** you lose nothing by moving to Neo. SDXL is fully supported, and Neo adds
> `v-pred` SDXL, tiled-conv2d VAE (`--tiled-conv2d` — "greater reduction for SD1 and SDXL VAE"),
> and the `Diffusion in Low Bits` / fp8 paths.

---

## 1. Corrections to my earlier Classic guide

Two errors in the Classic write-up, both now fixed in `COLAB_FORGE_CLASSIC_SDXL.md`:

1. **`COMMANDLINE_ARGS` *does* work.** I claimed it was ignored. It is not —
   `modules/paths_internal.py` reads it and appends to `sys.argv`:
   ```python
   commandline_args = os.environ.get("COMMANDLINE_ARGS", "")
   sys.argv += shlex.split(commandline_args)
   ```
   Only **positional** args passed to `webui-user.sh` are dropped (bare `exec` doesn't inherit them).
2. **`--extensions-dir` does not exist** in either branch. Extensions resolve as
   `os.path.join(data_path, "extensions")` — symlink it, or relocate via `--data-dir`.

Both branches share this early pre-parser, which is also why `--data-dir` / `--model-ref`
work even though they are not in `modules/cmd_args.py`.

---

## 2. Cell 1 — Drive + model tree

```python
# %% Cell 1 — Drive layout
import os
from google.colab import drive
drive.mount('/content/drive')

ROOT      = "/content/drive/MyDrive/forge-neo"
MODEL_REF = f"{ROOT}/models"
OUTPUT    = f"{ROOT}/outputs"

SUBS = ["Stable-diffusion", "VAE", "Lora", "ESRGAN", "ControlNet",
        "ControlNetPreprocessor", "embeddings", "Adetailer", "text_encoder"]

for p in [MODEL_REF, OUTPUT] + [f"{MODEL_REF}/{s}" for s in SUBS]:
    os.makedirs(p, exist_ok=True)
print("model_ref =", MODEL_REF)
```

---

## 3. Cell 2 — Clone Neo + Python 3.13 venv

```bash
# %% Cell 2 — Neo needs Python 3.13; Colab's system Python is 3.12
set -e
cd /content
pip install -q uv
export UV_LINK_MODE=copy

rm -rf sd-webui-forge-neo
git clone --branch neo --depth 1 https://github.com/Haoming02/sd-webui-forge-classic
cd /content/sd-webui-forge-neo

uv venv venv --python 3.13 --seed
./venv/bin/python -V          # MUST be 3.13.x
```

`uv venv --python 3.13` downloads a **standalone CPython 3.13.12** — non-negotiable, Neo's
`check_python_version()` hard-warns on anything else.

---

## 4. Cell 3 — Pin build deps before first launch

```bash
# %% Cell 3 — overrides (all read via os.environ.get in prepare_environment)
set -e
cd /content/sd-webui-forge-neo

# ---- CUDA build selection ----
# Neo default is cu130 (torch 2.13.0). Verified: torch-2.13.0+cu130-cp313 EXISTS on the cu130 index.
# If you get "Please update your GPU driver to support cu130": note cu128 does NOT have
# torch 2.13.0 — its newest cp313 build is 2.11.0. So the fallback is torch 2.11.0/cu128.
export TORCH_INDEX_URL="https://download.pytorch.org/whl/cu130"
export TORCH_COMMAND="pip install torch==2.13.0+cu130 torchvision==0.28.0+cu130 --extra-index-url ${TORCH_INDEX_URL}"
#  --- fallback (driver too old) ---
# export TORCH_INDEX_URL="https://download.pytorch.org/whl/cu128"
# export TORCH_COMMAND="pip install torch==2.11.0+cu128 torchvision==0.26.0+cu128 --extra-index-url ${TORCH_INDEX_URL}"

export GRADIO_PACKAGE="gradio==4.40.0 gradio_rangeslider==0.0.8"
export XFORMERS_PACKAGE="xformers==0.0.35 --extra-index-url ${TORCH_INDEX_URL}"

# ADetailer on torch>=2.6 (Neo removed --disable-safe-unpickle)
export TORCH_FORCE_NO_WEIGHTS_ONLY_LOAD=true

# Colab's own torch/numpy must not leak into the venv
./venv/bin/python -m pip uninstall -y -q torch torchvision numpy gradio 2>/dev/null || true
```

---

## 5. Cell 4 — Launch

```bash
# %% Cell 4 — Launch Forge Neo
set -e
cd /content/sd-webui-forge-neo

export GRADIO_SERVER_NAME="0.0.0.0"
export GRADIO_SERVER_PORT="7860"
export GRADIO_ANALYTICS_ENABLED="False"

export COMMANDLINE_ARGS="--no-download-sd-model --xformers --listen --port 7860 --model-ref /content/drive/MyDrive/forge-neo/models --api"

# extensions/ + outputs persist via symlink (no --extensions-dir flag exists)
mkdir -p extensions
ln -sfn /content/drive/MyDrive/forge-neo/outputs outputs 2>/dev/null || true

exec ./venv/bin/python launch.py
```

### Reconnect after a drop
```python
from google.colab.output import eval_js
eval_js("google.colab.kernel.proxyPort(7860)")
```

### Neo-specific flags worth adding on Colab

| Flag | Effect |
|---|---|
| `--uv-local-cache` | puts `UV_CACHE_DIR` in `./.uv-cache` — avoids re-downloading into the system cache each session. **Best fit for Colab.** |
| `--expandable-segments` | experimental PyTorch allocator; "may prevent OutOfMemory errors on certain platforms" |
| `--tiled-conv2d 256` | tiled VAE convs — "greater reduction for SD1 and SDXL VAE", but **slower** |
| `--use-ck-attention` | Comfy-Kitchen attention, overrides xformers |
| `--fast-fp8` | `torch._scaled_mm` for fp8_e4m3fn UNet |
| `--cuda-malloc` / `--cuda-stream` / `--pin-shared-memory` | perf, can cause OOM |

> Skip `--sage` / `--flash` on a T4 (compile-heavy; Sage2 also needs both pos+neg prompts
> or you get `NaN`). The Neo README notes `xformers` **does not support RTX 50s** —
> irrelevant for Colab T4/L4, which are fine.

---

## 6. SDXL settings in Neo

Same fundamentals as Classic: **SD VAE = Automatic/None** (never an SD1.x VAE),
DPM++ 2M Karras, 25–30 steps, CFG 5–7, 1024×1024.

Additions worth knowing:
* **Diffusion in Low Bits** (*Settings → Optimizations*) — keeps VRAM manageable for fp8/fp16 LoRAs on a 15 GB T4.
* **Text Encoder dir** — Neo adds `--text-encoder-dirs`, so SDXL refiner / TE2 encoders can live on Drive.
* Refiner and text-encoder-on-CPU defaults differ slightly from Classic — verify in *Settings*.

---

## 7. ADetailer on Neo — important

**Do not install `Bing-su/adetailer` on Neo.** Per
[issue #769](https://github.com/Haoming02/sd-webui-forge-classic/issues/769),
ADetailer `26.x` breaks against Neo; use:

```bash
cd /content/sd-webui-forge-neo/extensions
rm -rf adetailer
git clone https://github.com/abzaloff/aadetailer-neoforge adetailer
```

Plus:
* `export TORCH_FORCE_NO_WEIGHTS_ONLY_LOAD=true` (Neo **removed** the no-op
  `--disable-safe-unpickle` flag that Classic carried specifically for ADetailer).
* **mediapipe has no Python 3.13 wheels**, so mediapipe detectors stay broken
  ([mediapipe#5708](https://github.com/google-ai-edge/mediapipe/issues/5708)). Use **YOLO** detectors.

---

## 8. Troubleshooting (Neo)

| Error | Cause | Fix |
|---|---|---|
| `/bin/sh: line 1: uv: command not found` | `--uv` used without installing uv (known report: StabilityMatrix#1552) | `pip install -q uv` first (Cell 2) |
| `This program is tested with 3.13.12 Python, but you have 3.12` | Colab system Python | `uv venv venv --python 3.13 --seed` |
| `Please update your GPU driver to support cu130` | driver older than CUDA 13 | cu128 / torch **2.11.0** fallback (not 2.13) |
| `AssertionError: Torch not compiled with CUDA enabled` | CPU/ROCm torch wheel picked | delete venv, re-pin `TORCH_COMMAND` |
| UI blank / tab errors | gradio not 4.40.0 | re-export `GRADIO_PACKAGE` incl. `gradio_rangeslider==0.0.8` |
| Extension deps never install | skip-flags left on | remove `--skip-install --skip-prepare-environment` |
| ADetailer errors on Neo | wrong fork | `abzaloff/aadetailer-neoforge` + env var + YOLO |
| OOM on T4 | 15 GB VRAM | `--expandable-segments`, fp8 / low-bits, Hires fix off |

---

## 9. Recommendation

**Yes, move to Neo** — it is the default branch, actively maintained, and strictly a
superset for SDXL. Two concrete costs on Colab:

1. **ADetailer needs a different fork** (`abzaloff/aadetailer-neoforge`) — the real migration cost.
2. **cu130 driver risk.** If your Colab driver is older, the fallback is torch `2.11.0+cu128`
   (cu128 has no 2.13.0 cp313 build).

Everything else in the Classic guide carries over unchanged — same Drive layout, same
`--model-ref`, same `COMMANDLINE_ARGS` mechanism, same direct `launch.py` invocation.

If you want zero risk, keep **both** notebooks: Classic for the extensions you already
tuned, Neo for newer models. They can share the same Drive model folder.
