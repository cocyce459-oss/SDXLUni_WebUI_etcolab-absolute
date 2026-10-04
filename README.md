<div align="center">

# 🌌 ✦ STABLE DIFFUSION WEBUI FORGE — NEO ✦ 🌌
### ⚡ *Next-Generation High-Performance Neural Synthesis Engine* ⚡

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=0:#03001e,25:#7303c0,50:#ec38bc,75:#00d2ff,100:#3a7bd5&height=220&section=header&text=NEO%20✦%20FORGE%20ENGINE&fontSize=42&fontColor=ffffff&animation=twinkling&fontAlignY=38&desc=Starry%20Night%20Cyberpunk%20Architecture%20%7C%20SDXL%20%26%20Modern%20DiT%20Workflows&descSize=17&descAlignY=62&descAlign=50" width="100%" alt="Header Banner" />
</p>

<!-- Star Badges Cycling through Red, Orange, White, Cyan, and Blue -->
<p align="center">
  <a href="#-star-tier-constellation"><img src="https://img.shields.io/badge/★%20ALPHA%20STAR-CRIMSON%20CORE-ff003c?style=for-the-badge&logo=stars&logoColor=ffffff" alt="Star Red" /></a>
  <a href="#-star-tier-constellation"><img src="https://img.shields.io/badge/★%20SOLAR%20PULSE-AMBER%20GLOW-ff6b00?style=for-the-badge&logo=sparkles&logoColor=ffffff" alt="Star Orange" /></a>
  <a href="#-star-tier-constellation"><img src="https://img.shields.io/badge/★%20ASTRAL%20BEAM-STELLAR%20WHITE-f8f9fa?style=for-the-badge&logo=star&logoColor=111111&labelColor=e0e0e0" alt="Star White" /></a>
  <a href="#-star-tier-constellation"><img src="https://img.shields.io/badge/★%20CYBER%20NEBULA-NEON%20CYAN-00f5ff?style=for-the-badge&logo=target&logoColor=03001e&labelColor=00c4cc" alt="Star Cyan" /></a>
  <a href="#-star-tier-constellation"><img src="https://img.shields.io/badge/★%20DEEP%20COSMOS-ELECTRIC%20BLUE-0051ff?style=for-the-badge&logo=galaxy&logoColor=ffffff" alt="Star Blue" /></a>
</p>

<!-- Repository Meta Badges -->
<p align="center">
  <a href="https://github.com/Haoming02/sd-webui-forge-classic/tree/neo"><img src="https://img.shields.io/badge/BRANCH-NEO%20(ACTIVE)-7303c0?style=flat-square&logo=git&logoColor=white" alt="Branch Neo" /></a>
  <a href="https://github.com/Haoming02/sd-webui-forge-classic/tree/classic"><img src="https://img.shields.io/badge/LEGACY-CLASSIC%20ARCHIVE-2c3e50?style=flat-square&logo=github&logoColor=gray" alt="Branch Classic" /></a>
  <img src="https://img.shields.io/badge/PYTHON-3.13.12%20ISOLATED-00d2ff?style=flat-square&logo=python&logoColor=white" alt="Python 3.13" />
  <img src="https://img.shields.io/badge/PYTORCH-2.13.0%2Bcu130-ec38bc?style=flat-square&logo=pytorch&logoColor=white" alt="PyTorch 2.13" />
  <img src="https://img.shields.io/badge/GRADIO-4.40.0%20%2B%20RANGE-ff003c?style=flat-square&logo=gradio&logoColor=white" alt="Gradio 4.40" />
  <img src="https://img.shields.io/badge/PACKAGER-ASTRAL%20UV%20FAST-ff6b00?style=flat-square&logo=fastapi&logoColor=white" alt="Astral UV" />
  <a href="COLAB_FORGE_NEO_SDXL.ipynb"><img src="https://img.shields.io/badge/COLAB-OPEN%20SDXL%20NOTEBOOK-F9AB00?style=flat-square&logo=googlecolab&logoColor=white" alt="Open Colab" /></a>
  <img src="https://img.shields.io/badge/LICENSE-GPL--3.0-0051ff?style=flat-square" alt="License" />
</p>

<p align="center">
  <b>[ <a href="#-google-colab-absolute-zero-to-hero">Google Colab Guide</a> ]</b> •
  <b>[ <a href="#-new-features-october-edition">Features Matrix</a> ]</b> •
  <b>[ <a href="#-commandline-flags--neo-optimizations">Commandline CLI</a> ]</b> •
  <b>[ <a href="#-installation-suite">Installation</a> ]</b> •
  <b>[ <a href="#-attention-hierarchies">Attention Engine</a> ]</b> •
  <b>[ <a href="#-issues--guidelines">Issue Policy</a> ]</b>
</p>

---

<p align="center">
  <img src="html/ui.webp" width="760" style="border-radius: 14px; border: 2px solid #7303c0; box-shadow: 0 0 25px rgba(115,3,192,0.6);" alt="Forge Neo User Interface" />
</p>

<table align="center" width="100%">
<tr>
<td bgcolor="#050515" style="border-left: 4px solid #00f5ff; border-radius: 8px; padding: 18px 24px;">

> ❝ **Stable Diffusion WebUI Forge** is a cutting-edge platform engineered atop the foundation of AUTOMATIC1111's WebUI. Designed to simplify development, dramatically optimize GPU/system resource allocation, accelerate cross-architecture inference, and foster experimentation with groundbreaking diffusion models.  
> Inspired by the modding milestone *Minecraft Forge*, this engine empowers the generative AI community to forge without boundaries. ❞
> 
> <p align="right"><b>— lllyasviel</b> <i>(paraphrased)</i></p>

</td>
</tr>
</table>

</div>

<br>

## 🌌 Introduction: The "Neo" Paradigm

**"Neo"** serves as the authoritative, actively maintained continuation for the modern generation of Forge (built on Gradio `4.40.0`). While upstream development paused, Neo spearheads bleeding-edge inference acceleration, deep memory management revamps, modern kernel attention integration, and instant first-class support for the latest diffusion transformers (DiTs) including **SDXL**, **FLUX.2-Klein**, **Wan 2.2**, **Qwen-Image**, **Anima**, **Z-Image**, and **PiD 1.5**.

> [!TIP]
> 🚀 **Ready to deploy on cloud hardware in 5 minutes?** Jump straight into the verified **[Google Colab Absolute SDXL Suite](#-google-colab-absolute-zero-to-hero)** with zero environment drift!

---

## 🌟 Star Tier Constellation

Our telemetry and feature matrix are color-coded across 5 astronomical energy tiers:

| Celestial Tier | Badge Color | Frequency & Role | Core Focus |
|:---:|:---:|:---:|:---|
| 🔴 **Alpha Star** | `#ff003c` Crimson | Hard Critical / Base Execution | PyTorch 2.13.0+cu130 kernel, Python 3.13 isolation, memory patcher |
| 🟠 **Solar Pulse** | `#ff6b00` Amber | High Acceleration & Speed | Astral `uv` pip caching, fast fp8 scaled matrix operations, symlinks |
| ⚪ **Astral Beam** | `#f8f9fa` White | Stability & Precision Layers | Gradio 4.40.0, RescaleCFG, Zero Terminal SNR, v-prediction |
| 🐬 **Cyber Nebula** | `#00f5ff` Cyan | Next-Gen Diffusion Arch | SDXL, FLUX.2-Klein, Wan 2.2 Video, Qwen-Image-Edit, Anima |
| 🌌 **Deep Cosmos** | `#0051ff` Blue | Advanced Attention Kernels | SageAttention, FlashAttention, Radial Attention, Comfy-Kitchen |

---

## ⚡ Google Colab: Absolute Zero-to-Hero

We ship full, verified zero-drift cloud automation for Google Colab GPU instances (`T4` / `L4` / `A100`).

<div align="center">

[![Open In Colab](https://img.shields.io/badge/Colab-Run%20Forge%20Neo%20SDXL-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white)](COLAB_FORGE_NEO_SDXL.ipynb)
[![Read Spec](https://img.shields.io/badge/Specs-COLAB__FORGE__NEO__SDXL.md-00f5ff?style=for-the-badge&logo=markdown&logoColor=white)](COLAB_FORGE_NEO_SDXL.md)

</div>

### 🔮 Architecture Delta: Neo vs Classic
Verified against code commits (`neo` branch default vs legacy `classic`):

```
┌─────────────────────────────────┬─────────────────────────────────┐
│     FORGE CLASSIC (LEGACY)      │        FORGE NEO (ACTIVE)       │
├─────────────────────────────────┼─────────────────────────────────┤
│ Python 3.11.9                   │ Python 3.13.12 (uv isolated)    │
│ Gradio 3.43.2                   │ Gradio 4.40.0 + RangeSlider     │
│ PyTorch 2.10.0+cu130            │ PyTorch 2.13.0+cu130 (cu128 alt)│
│ xformers 0.0.34 (strict pin)    │ xformers 0.0.35 (torch>=2.10)   │
│ numpy 1.26.4 / pydantic 1.10.22 │ numpy 2.3.5 / pydantic 2.10.6   │
│ SD1.5 & SDXL only               │ SDXL, FLUX, Wan, Qwen, Anima... │
└─────────────────────────────────┴─────────────────────────────────┘
```

### 🛰️ Fast Pipeline Setup (Colab / Linux)

```bash
# 1. Install high-speed Astral UV package manager
pip install -q --upgrade uv

# 2. Clone Neo branch
git clone --branch neo --depth 1 https://github.com/Haoming02/sd-webui-forge-classic sd-webui-forge-neo
cd sd-webui-forge-neo

# 3. Create standalone Python 3.13 environment
uv venv venv --python 3.13 --seed

# 4. Set runtime environment flags
export TORCH_INDEX_URL="https://download.pytorch.org/whl/cu130"
export TORCH_COMMAND="pip install torch==2.13.0+cu130 torchvision==0.28.0+cu130 --extra-index-url ${TORCH_INDEX_URL}"
export GRADIO_PACKAGE="gradio==4.40.0 gradio_rangeslider==0.0.8"
export XFORMERS_PACKAGE="xformers==0.0.35 --extra-index-url ${TORCH_INDEX_URL}"
export TORCH_FORCE_NO_WEIGHTS_ONLY_LOAD="true"

# 5. Launch with cloud optimizations
export COMMANDLINE_ARGS="--no-download-sd-model --xformers --listen --port 7860 --expandable-segments --api"
./venv/bin/python launch.py
```

> [!IMPORTANT]
> - **ADetailer on Neo**: Bing-su's legacy repository is incompatible with Gradio 4. Use `https://github.com/abzaloff/aadetailer-neoforge` and select **YOLO** models (MediaPipe lacks cp313 wheels).
> - **T4 VRAM Discipline**: On 15GB VRAM instances, keep Hires.fix disabled for base SDXL generation, use `--expandable-segments`, and leave text encoder on CPU if loading ultra-heavy LoRAs.

---

## 🌌 Features Matrix [October Edition]

> Inherits the rich ecosystem and base capabilities of [AUTOMATIC1111 WebUI](https://github.com/AUTOMATIC1111/stable-diffusion-webui) while overhauling the underlying engine for peak speed and lightweight memory consumption.

### 🐬 Next-Gen Generative Models

<details open>
<summary><b>Click to expand / collapse Supported Model Architectures</b></summary>
<br>

* 🎨 **Krea 2 Engine**: Full support for `Turbo` & `Raw` inference streams.
  * 🎭 **Krea 2 Identity Edit**: Native pipeline support via specific [Identity LoRA](https://civitai.com/models/2761113/krea-2-identity-edit) (Activate under `Settings → Stable Diffusion`).
* 🌌 **Anima Multiverse**: First-class support for `Anima 2B`, `Anima 2.9B`, and `Anima 3.8B`.
  * Automatic cross-architecture LoRA translation between 2B, 2.9B, and 3.8B.
  * `qwen35_4b` adapter support enabled via [Extension](https://github.com/GumGum10/forge-anima-3.8B).
  * 🎭 **Anima Edit**: Supported via official [LoRA](https://civitai.com/models/2650553/anima-edit).
* ⚡ **Flux.2-Klein Transformers**: Native inference for `4B` & `9B` architectures.
  * Toggle standard `img2img` routing under `Settings → Stable Diffusion`.
* 🏮 **Baidu Ernie-Image**: Seamless execution of `ernie-image` and `ernie-image-turbo`.
* 🔬 **PiD 1.5 Scaled Diffusion**: Support for `sdxl`, `qwen`, `flux1`, and `flux2` architectures.
  * Integrated pipeline for automatic post-generation upscaling.
* 🌀 **Tongyi Z-Image**: Full support for both `z-image` and `z-image-turbo`.
* 🎬 **Wan 2.2 Video Suite**: High-capacity `14B` architecture with dynamic **High Noise / Low Noise** refiner switching.
  * *Note: Requires local [FFmpeg](https://ffmpeg.org/) installed for video container export.*
* 🌌 **Mugen Generative Stack**: Full exposure of `Shift` dynamics slider under `Settings → Presets → XL`.
* 🔮 **Advanced SDXL Paradigms**:
  * **v-prediction**: Autodetected when `state_dict` includes `v_pred`.
  * **Zero Terminal SNR**: Triggered automatically when `state_dict` includes `ztsnr`.
  * **Rectified Flow**: Activated when model folder or path contains `rectified`.
* 🤖 **Qwen-Image & Qwen-Image-Edit**: Intelligent route detection when model path contains `qwen` and `edit`.
* 💫 **Flux Kontext**: In-context generation triggered when path includes `kontext`.
* 🧵 **ImageStitch Integrated**:
  * Multi-image input tensor stitching for modern Edit models.
  * FirstLastFrameToVideo temporal generation for Wan 2.2.
* 📦 **MixedPrecision Quantization Modes**:
  * `fp4mixed` • `fp8mixed` • `mxfp8` • `nvfp4` • `fp8_scaled` • `int8_convrot` • `convrot_w4a4` • `asym_w4a8_int8` • `w6a8_int8`.
* 🚀 **Modern Decoders & VAEs**: [Flux.2-Small-Decoder](https://huggingface.co/black-forest-labs/FLUX.2-small-decoder) & [Qwen2D VAE](https://huggingface.co/Anzhc/Qwen2D-VAE).
* 🖼️ **Experimental & Exotic Models**: [Lumina-Image-2.0](https://huggingface.co/Alpha-VLLM/Lumina-Image-2.0) (`Neta-Lumina` / `NetaYume-Lumina`), [Chroma1-HD](https://huggingface.co/lodestones/Chroma1-HD), and legacy Nunchaku (`SVDQ`).

</details>

### ⚙️ Engine Innovations & Workflow Features

* 🎛️ **Deterministic Preset System**: Fully rewritten preset logic storing checkpoint states, module selections, and sampler hyperparameters individually per preset.
* 📐 **Resolution Step Enforcement**: Hard-locked multiple-of-64 dimension steps to eliminate tensor misalignments (configurable in `Settings → System`).
* 🏎️ **Astral `uv` Acceleration**: Lightning-fast package resolution cutting build and launch latency down to seconds.
* 🌟 **Spectrum Acceleration**: Training-free inference speedup across all supported model families.
* ⚡ **Torch Compile**: Zero-overhead `torch.compile` graph optimization after initial kernel warmup.
* 🎨 **RescaleCFG & MaHiRo**:
  * **RescaleCFG**: Drastically mitigates color over-saturation and burn artifacts on `v-pred` models.
  * **MaHiRo**: Alternative CFG weighting algorithm significantly elevating prompt adherence.
* 🧱 **Tiled Conv2d VAE Engine**: Substantially shrinks VRAM footprint during latent decoding for SD1 and SDXL.
* 🎭 **Next-Gen ControlNet Ecosystem**:
  * **LLLite**: SDXL and Anima with `MultiDiffusion` integration.
  * **Union ControlNet**: Full support for SDXL 1.0 Union and Chenkin UniControl-XL.
  * **Region ControlNet**: Color-masked regional generation for Anima.
  * **Dynamic LoRA Control**: Syntax `<lora:name:[w1@t1, w2@t2, ...]>` for time-step gated LoRA injection.
* 🎞️ **Media Formats**: Out-of-the-box support for modern next-gen image codecs: `.avif`, `.heif`, and `.jxl`.
* 🖼️ **ForgeCanvas Overhaul**: Deobfuscated, highly responsive canvas with eraser controls, mobile touch support, hotkeys, and customized brush parameters.

---

## 🗑️ Clean Architecture: Removed Legacy Baggage

To deliver maximum speed, maintainability, and clean dependency trees, obsolete legacy systems have been completely excised:

```
[✗] SD2 / SD3 Base Architectures           [✗] Textual Inversion Legacy Training
[✗] Forge Spaces Cloud Wrappers            [✗] Hypernetworks Architecture
[✗] Outdated CLIP & Deepbooru Interrogator [✗] Obsolete Samplers & Schedulers
[✗] bitsandbytes Inefficient Layer Hooks   [✗] Bloated 3rd-Party Builtin Bundles
```

---

## 🛠️ Performance Optimizations Under the Hood

<div align="center">

| Area | Engineering Transformation | Direct Benefit |
|:---|:---|:---|
| **Memory Engine** | Complete rewrite of `memory_management.py`, `ModelPatcher`, and backend streaming | Eliminates memory leaks when swapping large checkpoints; auto OOM unload |
| **Launch Times** | Removed automatic fresh-install `git clone` loops & `open-clip` dependency | Launches instantaneously; deterministic offline boot |
| **PyTorch Core** | Upgraded to **PyTorch 2.13.0+cu130** with CUDA 13 ecosystem | Maximum Tensor Core compute efficiency on modern GPUs |
| **Spandrel & VAE** | Updated `spandrel` engine and centralized `.pth`/`.safetensors` inside `ESRGAN/` | Fast half-precision upscaling; zero duplicate upscaler code |
| **UI Components** | Infotext parser rewritten; ControlNet tabs modern Gradio migration | Clean multi-unit workflow; prompt emphasis faithfully preserved |

</div>

---

## 💻 Commandline Flags & Neo Optimizations

Add flags to `COMMANDLINE_ARGS` inside `webui-user.bat` (Windows) or `webui-user.sh` (Linux/macOS):

```bash
# Example: High performance configuration
set COMMANDLINE_ARGS=--uv --cuda-malloc --expandable-segments --fast-fp8 --xformers
```

### ⚡ Core & Memory Acceleration
* `--cuda-malloc` — Activates specialized memory allocator to drastically minimize heap fragmentation.
* `--cuda-stream` — Enables asynchronous non-blocking weight offloading between CPU and GPU RAM.
* `--pin-shared-memory` — Locks shared memory allocations for heightened transfer throughput.
* `--expandable-segments` — Enables PyTorch's native expandable segment allocator to suppress OOMs on burst tensors.
* `--pynvml` — Queries the NVIDIA Management Library directly for real-time accurate free VRAM tracking.

### 📦 Astral UV System
* `--uv` — Substitutes slow `pip` invocations with Astral's hyper-fast `uv pip`.
* `--uv-symlink` — Operates in `--link-mode symlink`, drastically cutting venv footprint (`~7 GB` down to `~100 MB`).
* `--uv-local-cache` — Directs package caching to `.uv-cache` inside the WebUI root. Ideal for portable and Colab setups.

### 📁 Unified Storage & Cross-Tool References
* `--model-ref <DIR>` — Replaces the local `models` tree with a centralized external directory (contains `Stable-diffusion`, `Lora`, `VAE`, etc.).
* `--forge-ref-a1111-home <DIR>` — Ingests checkpoints and models directly from an existing AUTOMATIC1111 install.
* `--forge-ref-comfy-home <DIR>` — Links directly to a ComfyUI installation directory.
* `--forge-ref-comfy-yaml <PATH>` — Ingests ComfyUI `extra_model_paths.yaml` configurations.

### 🔮 Compute, Attention & Precision
* `--xformers` — Installs and links memory-efficient cross-attention kernels. *(Note: RTX 50s not supported by xformers).*
* `--sage` — Automatically installs and activates `sageattention` with native Triton bindings.
* `--flash` — Installs and compiles `flash_attn` for high-throughput DiT attention.
* `--use-ck-attention` — Activates **Comfy-Kitchen Attention**, overriding alternative attention kernels.
* `--enable-triton-backend` — Triggers Triton computational kernel backends inside Comfy-Kitchen.
* `--fast-fp8` — Uses native hardware `torch._scaled_mm` acceleration for `float8_e4m3fn` calculations.
* `--fast-fp16` — Enables accelerated `allow_fp16_accumulation` mode.
* `--tiled-conv2d <SIZE>` — Breaks VAE convolutions into tiles (`64`, `128`, `256`, `512`). Massive VRAM reduction for SD1/SDXL!
* `--autotune` — Turns on `torch.backends.cudnn.benchmark` profiling.

---

## 🚀 Installation Suite

### 1. Prerequisites
* **Git**: [Download Git](https://git-scm.com/downloads)
* **Package Manager**: [Astral `uv`](https://github.com/astral-sh/uv#installation) *(strongly recommended)* or [Python 3.13.12](https://www.python.org/downloads/release/python-31312/)

### 2. Clone Repository
```bash
git clone https://github.com/cocyce459-oss/SDXLUni_WebUI_etcolab-absolute.git sd-webui-forge-neo
cd sd-webui-forge-neo
```

### 3. Environment Setup

<details open>
<summary><b>🌟 Recommended: Astral uv Setup (Fastest & Cleanest)</b></summary>

```bash
# Create an isolated Python 3.13 virtual environment with uv
uv venv venv --python 3.13 --seed

# Activate on Linux / macOS:
source venv/bin/activate

# Or activate on Windows:
# .\venv\Scripts\activate
```
Add `--uv` to your `webui-user.bat` or `webui-user.sh`.
</details>

<details>
<summary><b>🐢 Legacy Method: Standard Python 3.13</b></summary>

Install **Python 3.13.12** from python.org. Ensure **"Add Python to PATH"** is ticked during setup.
</details>

### 4. Boot the WebUI
* **Windows**: Double-click `webui-user.bat`
* **Linux / macOS**: Execute `./webui-user.sh`

On first launch, dependencies will be resolved automatically. The Gradio interface will pop open in your default browser at `http://localhost:7860`.

---

## 🌌 Attention Hierarchies

Forge Neo dynamically detects and ranks attention backends, binding the first compatible function in priority sequence:

```
┌────────────────────────────────────────────────────────┐
│  1. SageAttention   (Fastest, requires Triton)         │
│  2. FlashAttention  (High-throughput scaled dot)       │
│  3. xformers        (Industry standard SD/SDXL kernel) │
│  4. PyTorch SDPA    (Native scaled dot product)        │
│  5. Basic           (Fallback standard PyTorch math)   │
└────────────────────────────────────────────────────────┘
```

> [!NOTE]
> Specific attention backends can be disabled at startup by providing disable flags such as `--disable-sage`.

---

## 📋 Comprehensive Troubleshooting Guide

| Symptom / Error | Root Cause | Solution |
|:---|:---|:---|
| `uv: command not found` | `--uv` flag set without `uv` binary on system | Run `pip install --upgrade uv` or install via Astral installer script |
| `This program is tested with 3.13.12` | Runtime executing under Python 3.10/3.11/3.12 | Use `uv venv venv --python 3.13 --seed` to download standalone CPython 3.13 |
| `Please update your GPU driver to support cu130` | Nvidia driver version `< 580` | Set fallback `TORCH_INDEX_URL` to `cu128` (torch `2.11.0`) |
| `AssertionError: Torch not compiled with CUDA` | CPU or ROCm wheel mistakenly installed | Wipe `venv/` directory and reinstall using the pinned `TORCH_COMMAND` |
| `UI blank / slider components broken` | Incompatible Gradio version loaded | Force install `gradio==4.40.0` and `gradio_rangeslider==0.0.8` |
| `ADetailer unpickle / module crash` | Upstream Bing-su repo incompatible with Neo | Clone `abzaloff/aadetailer-neoforge` and export `TORCH_FORCE_NO_WEIGHTS_ONLY_LOAD=true` |
| `CUDA Out Of Memory (OOM)` | High resolution burst without pagination | Add `--expandable-segments --tiled-conv2d 256` and enable Low Bits in Settings |

---

## 📜 Issues & Guidelines

To maintain focused development, please observe our collaboration criteria:

* **Removed Features**: Bug reports requesting restoration of intentionally dropped legacy modules (SD2, Hypernetworks, bitsandbytes) will be closed.
* **Non-Official Quants**: Issues resulting from arbitrary unofficial model conversions or corrupt weights are unsupported.
* **Third-Party Extensions**: Extensions are expected to adapt to the UI architecture, not vice-versa.
* **StabilityMatrix**: Bug submissions must be reproducible on a pristine manual git installation.
* **Community Safety**: Strictly no NSFW content or offensive imagery in issue attachments.

---

## 💖 Credits & Acknowledgments

Deep gratitude to the trailblazers whose tireless contributions power the open generative landscape:

* **AUTOMATIC1111** — The foundational bedrock of WebUI architecture.
* **lllyasviel** — Architectural genius behind Forge, ControlNet, and Fooocus.
* **comfyanonymous** — ComfyUI backend core and modular graph primitives.
* **kijai**, **city96**, and the vibrant open-source AI developer collective.

<br>

<div align="center">

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=0:#03001e,50:#7303c0,100:#00d2ff&height=120&section=footer" width="100%" alt="Footer Banner" />
</p>

<sub><i>Built for the boldest creators. Harness the cosmos of neural generation. 🌌⚡</i></sub>

</div>
