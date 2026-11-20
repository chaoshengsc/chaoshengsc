# Chao Sheng

I fine-tune robot manipulation policies on demonstrations and test how public VLA policies respond to wrist-camera masking and first-frame freezing in simulation.

## π0.5 fine-tuning on LIBERO

I fine-tuned OpenPI’s π0.5 with LoRA on one RTX A5000. The policy used scene and wrist images plus a language instruction to predict actions. With the same evaluation protocol and 400 fixed initial states across 10 LIBERO-Spatial tasks, it succeeded in **0/400 episodes before fine-tuning** and **382/400 (95.50%) after 2,000 updates**.

[Release v1.1.0](https://github.com/chaoshengsc/pi05-libero-finetuning/releases/tag/v1.1.0) · [Checkpoint comparisons and failure analysis](https://github.com/chaoshengsc/pi05-libero-finetuning/blob/v1.1.0/docs/results.md)

## Camera inputs in VLA policies

I tested wrist-camera masking and first-frame freezing on matched initial states. For LeRobot π0.5 v044, success fell from **492/500 with normal input to 23/500 with the wrist camera masked**. During the study, I found that a missing camera input could shift the remaining images into the wrong slots. I reviewed and submitted a fix covering six LeRobot policies.

[Camera ablation project](https://github.com/chaoshengsc/libero-camera-ablation) · [LeRobot PR #5129](https://github.com/huggingface/lerobot/pull/5129)

[Personal website](https://chaoshengsc.github.io/) · [中文主页](https://chaoshengsc.github.io/index_cn.html)
