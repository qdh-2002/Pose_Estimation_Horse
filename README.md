# Efrei-Horse Benchmark

[![license](https://img.shields.io/github/license/:user/:repo.svg)](LICENSE)
[![standard-readme compliant](https://img.shields.io/badge/readme%20style-standard-brightgreen.svg?style=flat-square)](https://github.com/RichardLitt/standard-readme)



## Overview of the Efrei_Horse Dataset
<div align="center">
  <img src="https://github.com/qdh-2002/Pose_Estimation_Horse/blob/main/img/overview.png" alt="Description of the image" width="340" style="display: inline-block; margin-right: 10px;">
  <img src="https://github.com/qdh-2002/Pose_Estimation_Horse/blob/main/img/overview2.png" alt="Description of the image" width="380" style="display: inline-block;">
</div>


<div align="center">
<img src="https://github.com/qdh-2002/Pose_Estimation_Horse/blob/main/img/walk.gif" width="240"/> <img src="https://github.com/qdh-2002/Pose_Estimation_Horse/blob/main/img/trot.gif" width="240"/>
<img src="https://github.com/qdh-2002/Pose_Estimation_Horse/blob/main/img/canter.gif" width="240"/>
</div>

<div align="left">
  
 The Efrei Horse Dataset is a comprehensive dataset designed for equestrian pose estimation, which consists of annotated 7,794 images collected from 87 videos: 



- **🎦 87 Different Videos**: These videos are sourced from prestigious equestrian competitions such as the FEI and the Olympics, as well as IFCE and various internet sources.
- **✅ Annotations**: The annotations follow the COCO-style format. We adopt a skeleton of 28 keypoints(See [Skeleton](#skeleton)).

🚀 The whole dataset can be accessed on [OneDrive](https://1drv.ms/u/c/fea017f18035c74d/EYMOIBLqzMRMs_49vYen7oEBwJGch9L7W869GQ1mIzFMKw?e=ZJACC7).


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

We trained models with various backbones and architectures using our dataset and compared their performance, including HRNET, RESNET, ViTPose and CSPNeXt. We provide all the configuration files and checkpoint files, allowing you to select and use the models as needed.

![img](https://github.com/qdh-2002/Pose_Estimation_Horse/blob/main/img/rio_olympics2.gif)
![img](https://github.com/qdh-2002/Pose_Estimation_Horse/blob/main/img/tokyo2020-3.gif)

### Performance Comparison

| Model    | Backbone    | Resolution | PCK@0.05 | AUC   | Config   | Log     | Weight  | Size   |
|----------|-------------|------------|----------|-------|----------|---------|---------|--------|
| HRNet    | HRNet_w32    | 256x256    | 0.8789   | 0.8116| [config](https://github.com/qdh-2002/Pose_Estimation_Horse/blob/main/configs/efrei_hrnet.py)   | [log](https://github.com/qdh-2002/Pose_Estimation_Horse/blob/main/configs/hrnet.log)  | [OneDrive](https://1drv.ms/u/c/fea017f18035c74d/ESKBOhftowhPpzPGBlBXNpsBqIDQ1RCttF5s-QdExh7F0w?e=bOdqi3)  | 119.2 MB |
| HRNet    | HRNet_w48    | 256x256    | 0.8751   | 0.8101| [config](https://github.com/qdh-2002/Pose_Estimation_Horse/blob/main/configs/hrnet_w48.py)   | [log](https://github.com/qdh-2002/Pose_Estimation_Horse/blob/main/configs/hrnet_w48.log) | [OneDrive](https://1drv.ms/u/c/fea017f18035c74d/Ed_b8vPhD4VGg-EUI0ahghEBm5bYN7BRo7MSEYcHQFV5bA?e=S5nEU5) | 263 MB   |
| ResNet   | ResNet_101   | 256x256    | 0.8630   | 0.7971| [config](https://github.com/qdh-2002/Pose_Estimation_Horse/blob/main/configs/efrei_resnet.py)  | [log](https://github.com/qdh-2002/Pose_Estimation_Horse/blob/main/configs/resnet.log) | [OneDrive](https://1drv.ms/u/c/fea017f18035c74d/ETF934LYmb9HsDHWvneqRBQB18SSzUnxZBKKu9pYk4haTw?e=AePJq1) | 218.2 MB |
| ViTPose  | ViTPose_small| 192x256    | 0.8630   | 0.7994| [config](https://github.com/qdh-2002/Pose_Estimation_Horse/blob/main/configs/ViTPose_small_simple_efrei.py) | [log](https://github.com/qdh-2002/Pose_Estimation_Horse/blob/main/configs/vitpose_small.log) | [OneDrive](https://1drv.ms/u/c/fea017f18035c74d/EQZNVFH-cKtPkT5j2ofiRnQBJnKFRXVuNpMxEPnY1RyU3Q?e=XAnGp6) | 90.1 MB  |
| ViTPose  | ViTPose_huge | 192x256    | 0.8603   | 0.7976| [config](https://github.com/qdh-2002/Pose_Estimation_Horse/blob/main/configs/ViTPose_huge_simple_efrei.py) | [log](https://github.com/qdh-2002/Pose_Estimation_Horse/blob/main/configs/vitpose_huge.log) | [OneDrive](https://1drv.ms/u/c/fea017f18035c74d/EeOLHnNNb5xIkjlkOQ-t52UB0hRwRdLtmjsZFkeamkbqWw?e=29r6Xi) | 7.59 GB  |
| **CSPNeXt** | **CSPNeXt** | **256x256** | **0.8812** | **0.8172** | [**config**](https://github.com/qdh-2002/Pose_Estimation_Horse/blob/main/configs/cspnext.py) | [**log**](https://github.com/qdh-2002/Pose_Estimation_Horse/blob/main/configs/cspnext.log) | **[OneDrive](https://1drv.ms/u/c/fea017f18035c74d/ESyEmueivoZFpbRbB5wzmfIBb8A7PwcIpl4VkrDsfcleEg?e=J7gQkV)** | **142.3 MB** |

### Evaluation Metric
We used the PCK metric normalized by the bounding box (bbox) to evaluate and compare the models. The calculation is:

**PCK** is calculated as:

$$
PCK = (1 / N) * Σ[i=1 to N] (1 / K) * Σ[k=1 to K] I (||k^i - k_i||_2 / bbox_size < thr)
$$

where:
- $$k^i$$ is the predicted keypoint for the $$i-th$$ sample,
- $$k_i$$ is the ground truth keypoint for the $$i-th$$ sample,
- bbox_size is the size of the bounding box,
- thr is the threshold for determining if a keypoint is correctly predicted,
- $$I(...)$$ is the indicator function that returns 1 if the condition is true, otherwise 0.


For details on codes implementation, refer to the official [MMPose](https://mmpose.readthedocs.io/en/latest/_modules/mmpose/evaluation/metrics/keypoint_2d_metrics.html?highlight=PCK) documentation.

### Usage

We based our experiments on [MMPose](https://github.com/open-mmlab/mmpose), a comprehensive toolbox for pose estimation. For details on how to use MMPose, please refer to its GitHub repository.

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

3. **Download config from this repository into MMPose directory**:
```
#create folder for config files
os.chdir('configs/animal_2d_keypoint/topdown_heatmap')
os.mkdir('efrei')
os.chdir('efrei')
#download config file(use cspnext as an exmaple)
!wget "https://raw.githubusercontent.com/qdh-2002/Pose_Estimation_Horse/main/configs/cspnext.py?token=GHSAT0AAAAAACWNANC63BHN5CY467VZZOGUZXB4NKA" -O cspnext.py


#create folder for checkpoints files
cd mmpose/configs/animal_2d_keypoint

os.chdir('../../../../')

```
   


4. **Download checkpoint files from OneDrive into Checkpoint directory**
```
#Download the checkpoint files from OneDrive and upload them into path 'mmpose/checkpoint'.

```


5. **Test your own videos:**
```
!python mmpose/demo/topdown_demo_with_mmdet.py \
        mmpose/demo/mmdetection_cfg/faster_rcnn_r50_fpn_coco.py \
        https://download.openmmlab.com/mmdetection/v2.0/faster_rcnn/faster_rcnn_r50_fpn_1x_coco/faster_rcnn_r50_fpn_1x_coco_20200130-047c8118.pth \
        mmpose/configs/animal_2d_keypoint/topdown_heatmap/efrei/ViTPose_huge_simple_efrei.py \
        # change the config file path if needed
        mmpose/checkpoint/epoch_190.pth \
        # change the checkpoint file path if needed
        --input icelandichorse-galop3.mp4 \
        # change the video/image path
        --output-root outputs/ViTPose_huge_simple_efrei \
        --device cuda:0 \
        --bbox-thr 0.5 \
        --kpt-thr 0.2 \
        --nms-thr 0.3 \
        --radius 4 \
        --thickness 2 \
        --draw-bbox \
        --show-kpt-idx \
        # 17 is the index for horse
        --det-cat-id 17
```


## Contributing

See [the contributing file](CONTRIBUTING.md)!


Small note: If editing the Readme, please conform to the [standard-readme](https://github.com/RichardLitt/standard-readme) specification.


## License

[MIT © Richard McRichface.](../LICENSE)
