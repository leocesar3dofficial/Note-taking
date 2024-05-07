# Stable Diffusion

## ComfyUI

### Installation

1. Clone the repo: https://github.com/comfyanonymous/ComfyUI

2. Install pytorch:

   ```bash
   pip install torch torchvision torchaudio --extra-index-url https://download.pytorch.org/whl/cu121
   ```

3. Install the dependencies inside the ComfyUI folder:

   ```bash
   pip install -r requirements.txt
   ```

4. Clone the manager extension repo in the folder (/ComfyUI/custom_nodes): https://github.com/ltdrdata/ComfyUI-Manager

### Running

```bash
python3 main.py
```

### User guide

- Install resources through manager extension or manually:
  - Checkpoints (/ComfyUI/models/checkpoints):
    - sd_xl_base_1.0.safetensors
  - Upscalers (/ComfyUI/models/upscale_models):
    - 4x-UltraSharp
