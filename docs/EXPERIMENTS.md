# Workflow experiments

| Version | Graph evidence | Role |
| --- | --- | --- |
| [Repaint v3](../archive/CarVyon_WorkflowA_PartRepaint_v3.json) | 21 nodes, 33 links. Qwen Image Edit FP8, SAM3 grounding, color matching and masked composite. | Early baseline |
| [Repaint v5](../archive/CarVyon_WorkflowA_PartRepaint_v5.json) | 22 nodes, 34 links. Adds an image crop and uses the fused Lightning checkpoint. | Earlier crop experiment |
| [Repaint v6](../CarVyon_WorkflowA_PartRepaint_v6.json) | 24 nodes, 36 links. Includes crop and mask handling alongside color matching. | Reference for a controlled comparison |
| [Repaint v7](../CarVyon_A_PartRepaint_v7.json) | 26 nodes, 37 links. Separates the Lightning LoRA and adds crop/stitch and blend stages. | Current repaint candidate |
| [Wheel swap v7](../CarVyon_B_WheelSwap_v7.json) | 33 nodes, 55 links. Separate front and rear wheel segmentation and edit paths. | Current wheel-swap candidate |
| [Hybrid 1](../hybrid1.json) | 30 nodes, 36 links. Two links reference missing nodes. | Historical experiment requiring repair |
| [Hybrid workflow](../hybridworkflow.json) | 35 nodes, 50 links. Six links reference missing nodes. | Historical experiment requiring repair |

These comparisons describe the saved graphs. A fixed input set, model revisions, seeds, timing and side-by-side images are needed to compare output quality.
