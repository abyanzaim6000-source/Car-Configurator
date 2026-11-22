# CarVyon | Car Configurator

ComfyUI workflow prototypes for two targeted edits to a car photo: repaint a selected body panel, or replace the wheels using a reference image. The project focuses on keeping the rest of the photograph visually consistent, including body lines, reflections, lighting and background.

**Status:** Workflow research in progress. The v7 workflows are the current starting point. A configurable app, repeatable output quality, and a clean-environment rendering test are still pending.

## Workflows

| Workflow | What it tests | Graph |
| --- | --- | ---: |
| [Part repaint v7](CarVyon_A_PartRepaint_v7.json) | Grounds an editable region from text (default: hood), grows and softens the mask, edits a crop with Qwen Image Edit, and composites it back into the input. | 26 nodes |
| [Wheel swap v7](CarVyon_B_WheelSwap_v7.json) | Uses a wheel reference and separate front and rear wheel masks to process and stitch the two edits. | 33 nodes |
| [Part repaint v6](CarVyon_WorkflowA_PartRepaint_v6.json) | Earlier repaint approach with color matching and a fused four-step checkpoint. | 24 nodes |

The [experiment archive](docs/EXPERIMENTS.md) compares earlier repaint versions and records the broken graph connections in the hybrid prototypes.

## Try a workflow

1. Open one of the v7 JSON files in ComfyUI.
2. Resolve missing nodes and model selections using the [model and dependency inventory](models.md).
3. Select your own car photo in the first **Load Image** node. For repaint, choose a paint reference and adjust the SAM3 text target (for example, `hood`). For wheel swap, supply a wheel reference and preview both masks.
4. Queue the workflow and inspect the result side by side with the original. Check panel edges, reflections, wheel alignment, and the unchanged areas outside the mask.

The workflow JSON loads by filename, so replace the saved example image selectors with your own inputs. This snapshot includes the graphs and model references. Recreating a run requires compatible weights, custom nodes, and input images.

## Earlier repaint experiment

![ComfyUI repaint experiment with a Qwen edit prompt and a car output](Screenshot%202026-06-07%20at%2016.47.46.png)

This saved experiment shows the output and its edit prompt. It predates this snapshot and serves as process documentation.

## Next milestone

Build a fixed set of reusable car photos with side and three-quarter views. Compare v6 and v7 on the same hood repaint inputs and track edits outside the mask, boundary quality, and reflection consistency. For wheel swap, check spoke identity, rim perspective and consistency between front and rear. Record the model versions, seed, settings and runtime with each comparison before building a configurator interface.

**Verified for this snapshot:** All seven workflow files parse as JSON. The v3, v5, v6 and both v7 graphs have no dangling link endpoints. Rendering and image quality were not revalidated for this publication.
