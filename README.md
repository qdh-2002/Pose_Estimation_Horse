# Efrei-Horse Benchmark

[![license](https://img.shields.io/github/license/:user/:repo.svg)](LICENSE)
[![standard-readme compliant](https://img.shields.io/badge/readme%20style-standard-brightgreen.svg?style=flat-square)](https://github.com/RichardLitt/standard-readme)



## Overview of the Efrei_Horse Dataset
<div align="center">
  <img src="https://github.com/qdh-2002/Pose_Estimation_Horse/blob/main/img/overview.png" alt="Description of the image" width="440" style="display: inline-block; margin-right: 10px;">
  <img src="https://github.com/qdh-2002/Pose_Estimation_Horse/blob/main/img/overview2.png" alt="Description of the image" width="480" style="display: inline-block;">
</div>

![img](https://github.com/qdh-2002/Pose_Estimation_Horse/blob/main/img/walk.gif)
![img](https://github.com/qdh-2002/Pose_Estimation_Horse/blob/main/img/trot.gif)
![img](https://github.com/qdh-2002/Pose_Estimation_Horse/blob/main/img/canter.gif)


The Efrei Horse Dataset is a comprehensive dataset designed for equestrian action analysis and pose estimation, which consists of annotated 7,794 images and collected from 87 videos:

- **🎦 87 Different Videos**: These videos are sourced from prestigious equestrian competitions such as the FEI and the Olympics, as well as IFCE and various internet sources.
- **✅ Annotations**: The annotations follow the COCO-style format. We adopt a skeleton of 28 keypoints(See [Skeleton](#skeleton)).

🚀 The complete dataset can be accessed on [OneDrive](https://onedrive.live.com/?cid=FEA017F18035C74D&id=FEA017F18035C74D%21s12200e83ccea4cc4b3fe3dbd87a7ee81&parId=FEA017F18035C74D%21sd8aec58d711f4827af93e98bb5c9647f&o=OneUp).


### Data Split

- **Testing Set**: 1,430 images
- **Training Set**: 6,364 images


### Skeleton

We utilize a detailed skeleton consisting of 28 keypoints for comprehensive pose estimation. This set of keypoints provides extensive coverage of the horse's body, capturing critical anatomical landmarks essential for accurate analysis. 

<p align="center">
  <img src="https://github.com/qdh-2002/Pose_Estimation_Horse/blob/main/img/skeleton.png" alt="Description of the image" width="500">
</p>


| Keypoint | Annotation | Description | Keypoint | Annotation | Description | 
|----------|----------|----------|----------|----------|----------|
| 1 | T1 | Nostril Midpoint | 15 | P9 | Right Tuber Sacrale |
| 2 | T2 | Top of Head | 16 | P9' | Left Tuber Sacrale |
| 3 | A8 | Neck Base | 17 | P7 | Right Hip |
| 4 | A7' | Left Shoulder | 18 | P5 | Right Knee |
| 5 | A7 | Right Shoulder | 19 | P3 | Right Fetlock(Back) |
| 6 | A6 | Right Radial Head | 20 | P1 | Right Hoof Solar Border(Back) |
| 7 | A5 | Right Elbow | 21 | P7' | Left Hip |
| 8 | A3 | Right Fetlock(Front) | 22 | P5' | Left Knee |
| 9 | A1 | Right Hoof Solar Border(Front) | 23 | P3' | Left Fetlock(Back) |
| 10 | A6' | Left Radial Head | 24 | P1' | Left Hoof Solar Border(Back) |
| 11 | A5' | Left Elbow | 25 | Q1 | Tail 1 |
| 12 | A3' | Left Fetlock(Front) | 26 | Q2 | Tail 2 |
| 13 | A1' | Left Hoof Solar Border(Front) | 27 | Q3 | Tail 3 |
| 14 | A10 | Tuber Sacrale | 28 | Q4 | Tail 4 |

<p align="left">



## Models

![img](https://github.com/qdh-2002/Pose_Estimation_Horse/blob/main/img/rio_olympics2.gif)
![img](https://github.com/qdh-2002/Pose_Estimation_Horse/blob/main/img/tokyo2020-3.gif)

### Performance Comparison

| Model |Backbone |Resolution | PCK@0.05 | AUC | Config | Log | Weight | Size |
|----------|----------|----------|----------|----------|----------|----------|----------|----------|
| HRNet | HRNet_w32 | 256x256 | 0.8653 | 0.7992 | [config](https://github.com/qdh-2002/Pose_Estimation_Horse/blob/main/configs/efrei_hrnet.py) | [log](https://github.com/qdh-2002/Pose_Estimation_Horse/blob/main/configs/hrnet.log) |OneDrive |134.3 MB  |
| HRNet| HRNet_w48 | 256x256 | ? | ? | [config]() | [log]() |OneDrive | ?  |
| ResNet | ResNet_101 | 256x256 | 0.8630 | 0.7971 | [config](https://github.com/qdh-2002/Pose_Estimation_Horse/blob/main/configs/efrei_resnet.py) |[log](https://github.com/qdh-2002/Pose_Estimation_Horse/blob/main/configs/resnet.log) |OneDrive |218.2 MB  |
| ViTPose | ViTPose_s | 192x256 |Row 3, Col 2 | Row 3, Col 3 |Row 1, Col 3 |Row 1, Col 3 |Row 1, Col 3 |
| ViTPose | ViTPose_h | 192x256 | 0.84 |Row 3, Col 2 | Row 3, Col 3 |Row 1, Col 3 |Row 1, Col 3 |Row 1, Col 3 |
| CSPNeXt | CSPNeXt | 256x256 | 0.88 |Row 3, Col 2 | Row 3, Col 3 |Row 1, Col 3 |Row 1, Col 3 |Row 1, Col 3 |



### Usage

We based our experiments on [MMPose](https://github.com/open-mmlab/mmpose), a comprehensive toolbox for pose estimation. For details on how to install and use MMPose, please refer to its GitHub repository.

To install MMPose and its dependencies, follow these steps:

1. **Clone the MMPose repository:**
   
```
!pip3 install install torch==1.10.1+cu113 torchvision==0.11.2+cu113 torchaudio==0.10.1+cu113 -f https://download.pytorch.org/whl/cu113/torch_stable.html
!pip install -U openmim
!mim install mmengine
!mim install 'mmcv==2.0.0rc3'
!mim install "mmdet>=3.0.0rc6"
!pip install opencv-python pillow matplotlib seaborn tqdm pycocotools -i https://pypi.tuna.tsinghua.edu.cn/simple
!rm -rf mmpose
!git clone https://github.com/open-mmlab/mmpose.git -b tutorial2023
import os
os.chdir('mmpose')
!mim install -e .
import os

os.mkdir('checkpoint')
os.mkdir('outputs')
os.mkdir('data')
os.mkdir('data/test')
```

2. **Install MMDetection:**
```
!mim install mmcv-full
!rm -rf mmdetection
!git clone https://github.com/open-mmlab/mmdetection.git -b 3.x

import os
os.chdir('mmdetection')
!pip install -v -e .
import os
os.mkdir('checkpoint')
os.mkdir('outputs')
os.mkdir('data')
```

*If you are using our ViTPose Model, please run:*
```
!mim install 'mmpretrain>=1.0.0'
```



5. **Test your own videos:**
```
!python mmpose/demo/topdown_demo_with_mmdet.py \
        mmpose/demo/mmdetection_cfg/faster_rcnn_r50_fpn_coco.py \
        https://download.openmmlab.com/mmdetection/v2.0/faster_rcnn/faster_rcnn_r50_fpn_1x_coco/faster_rcnn_r50_fpn_1x_coco_20200130-047c8118.pth \
        mmpose/configs/animal_2d_keypoint/topdown_heatmap/efrei/ViTPose_huge_simple_efrei.py \
        work/May24/epoch_190.pth \
        --input icelandichorse-galop3.mp4 \
        --output-root outputs/ViTPose_huge_simple_efrei \
        --device cuda:0 \
        --bbox-thr 0.5 \
        --kpt-thr 0.2 \
        --nms-thr 0.3 \
        --radius 4 \
        --thickness 2 \
        --draw-bbox \
        --show-kpt-idx \
        --det-cat-id 17
```


## Contributing

See [the contributing file](CONTRIBUTING.md)!

PRs accepted.

Small note: If editing the Readme, please conform to the [standard-readme](https://github.com/RichardLitt/standard-readme) specification.


## License

[MIT © Richard McRichface.](../LICENSE)
