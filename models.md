# Model and dependency inventory

The filenames below come from the saved workflow selectors. Configure the matching model types in ComfyUI and select each required artifact explicitly.

| Purpose | v7 selector | ComfyUI model folder |
| --- | --- | --- |
| Edit diffusion model | `qwen_image_edit_2511_fp8_e4m3fn_scaled.safetensors` | `diffusion_models/` |
| Vision-language text encoder | `qwen_2.5_vl_7b_fp8_scaled.safetensors` | `text_encoders/` |
| VAE | `qwen_image_vae.safetensors` | `vae/` |
| Lightning acceleration | `Qwen-Image-Edit-2511-Lightning-4steps-V1.0-bf16.safetensors` | `loras/` |
| Text-guided masks | `LoadSAM3Model` → `SAM3Grounding` | Set up SAM3 according to the installed node package |

The checked Comfy Desktop shared model directory contained the v7 LoRA and VAE. The v7 diffusion model and text encoder were absent from that directory. SAM3 and package revisions must be verified on the machine that runs the workflow.

The v3 graph references `qwen_image_edit_fp8_e4m3fn.safetensors`. Repaint v5 and v6 reference `qwen_image_edit_2511_fp8_e4m3fn_scaled_lightning_comfyui_4steps_v1.0.safetensors`, a fused variant. The two hybrid graphs reference `qwen_image_edit_2511_fp8mixed.safetensors` and `sam3.1_multiplex_fp16.safetensors`.

When importing a v7 graph, check for missing SAM3 nodes, `GrowMaskWithBlur`, and `InpaintCropImproved` / `InpaintStitchImproved`. Repaint v7 also uses `Image Blending Mode`. Install the matching packages using ComfyUI Manager and record their versions when a full render succeeds. The saved exports do not fully pin package versions or model hashes.

Model weights are kept outside Git. Obtain them from their respective distributors and check the terms for your use case.

The previous project README reports testing on an NVIDIA L40S. Minimum VRAM and compatibility on other GPUs have yet to be measured.
