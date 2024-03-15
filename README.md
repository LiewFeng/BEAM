<div align="center">
<h1>RayDN</h1>
<h3>Ray Denoising: Depth-aware Hard Negative Sampling for Multi-view 3D Object Detection</h3>
</div>

[![PWC](https://img.shields.io/endpoint.svg?url=https://paperswithcode.com/badge/beam-beta-distribution-ray-denoising-for/3d-object-detection-on-nuscenes-camera-only)](https://paperswithcode.com/sota/3d-object-detection-on-nuscenes-camera-only?p=beam-beta-distribution-ray-denoising-for)
[![arXiv](https://img.shields.io/badge/arXiv-Paper-<COLOR>.svg)](https://arxiv.org/abs/2402.03634)


<div align="center">
  <img src="figs/framework.png" width="800"/>
</div><br/>

## Introduction

This repository is an official implementation of [Ray Denoising](https://arxiv.org/abs/2402.03634).


## Getting Started

Our code is built based on [StreamPETR](https://github.com/exiawsh/StreamPETR). Please follow [StreamPETR](https://github.com/exiawsh/StreamPETR) to [setup enviroment](https://github.com/exiawsh/StreamPETR/blob/main/docs/setup.md) and [prepare data](https://github.com/exiawsh/StreamPETR/blob/main/docs/data_preparation.md) step by step.

## Training and Inference
You can train the model following:

```angular2html
tools/dist_train.sh projects/configs/RayDN/raydn_eva02_800_bs2_seq_24e.py 8 
```

You can evaluate the detection model following:
```angular2html
tools/dist_test.sh projects/configs/RayDN/raydn_eva02_800_bs2_seq_24e.py work_dirs/raydn_eva02_800_bs2_seq_24e/latest.pth 8 --eval bbox
```


## Results on NuScenes Val Set.
| Model | Setting |Pretrain| Lr Schd | NDS| mAP| Config |
| :---: | :---: | :---: | :---: | :---:|:---:| :---: |
| RayDN | R50 - 428q | NuImg | 60ep | 56.3 | 46.9 | [config](projects/configs/RayDN/raydn_r50_flash_704_bs2_seq_428q_nui_60e.py) |
| RayDN | EVA02-L - 900q | EVA02 | 24ep | 62.4 | 54.1 | [config](projects/configs/RayDN/raydn_eva02_800_bs2_seq_24e.py) |






## Acknowledgements

We thank these great works and open-source codebases:

[MMDetection3d](https://github.com/open-mmlab/mmdetection3d), [StreamPETR](https://github.com/exiawsh/StreamPETR), [DETR3D](https://github.com/WangYueFt/detr3d), [PETR](https://github.com/megvii-research/PETR).



