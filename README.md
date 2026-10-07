# CarVyon – ComfyUI Workflows

AI-powered car configurator pipeline built in ComfyUI. Upload a photo of a car
and change its paint colour, swap alloy wheels, or repaint individual panels,
while preserving reflections, lighting and shadows.

## Workflows
| File | What it does |
|------|--------------|
| `A_PartRepaint_v7.json` | Segments a selected body panel and repaints it in a new colour |
| `B_WheelSwap_v7.json` | Detects wheels and replaces them with a user-supplied wheel image |
| `archive/` | Older versions and experiments |

## How it works
1. Segmentation: SAM3 (via ComfyUI-SAM3) masks the target part
2. Editing: Qwen Image Edit / inpainting generates the new colour or wheel
3. Compositing: the edited region is blended back into the original image

## Requirements
- ComfyUI (latest)
- Custom nodes: ComfyUI-SAM3, comfyui-inpaint-nodes
- Models: see [models.md](models.md)
- GPU with ~24 GB VRAM recommended (tested on L40S)

## Usage
1. Open ComfyUI and drag a workflow `.json` onto the canvas
2. Install any missing nodes via ComfyUI Manager
3. Load your car image, set the target colour or wheel image
4. Click **Queue Prompt**

## Status
v7 is the current version. Known issues: Mainly lacking accuracy. Need to work on other models,versions and accuracy
