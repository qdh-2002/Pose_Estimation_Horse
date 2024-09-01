# ViTPose Model on Efrei-Horse Dataset

[![license](https://img.shields.io/github/license/:user/:repo.svg)](LICENSE)
[![standard-readme compliant](https://img.shields.io/badge/readme%20style-standard-brightgreen.svg?style=flat-square)](https://github.com/RichardLitt/standard-readme)

<img src="https://github.com/qdh-2002/Pose_Estimation_Horse/blob/main/img/overview.png" alt="Description of the image" width="500">


## Overview of the Efrei_Horse Dataset
![img](https://github.com/qdh-2002/Pose_Estimation_Horse/blob/main/img/rio_olympics2.gif)
![img](https://github.com/qdh-2002/Pose_Estimation_Horse/blob/main/img/tokyo2020-3.gif)


The Efrei Horse Dataset is a comprehensive dataset designed for equestrian action analysis and pose estimation, which consists of annotated 7,794 images and collected from 87 videos:

- **87 Different Videos**: These videos are sourced from prestigious equestrian competitions such as the FEI and the Olympics, as well as IFCE and various internet sources.
- **Annotations**: The annotations follow the COCO-style format. We adopt a skeleton of 28 keypoints.

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

### Performance Comparison

| Header 1 | Header 2 | Header 3 |
|----------|----------|----------|
| Row 1, Col 1 | Row 1, Col 2 | Row 1, Col 3 |
| Row 2, Col 1 | Row 2, Col 2 | Row 2, Col 3 |
| Row 3, Col 1 | Row 3, Col 2 | Row 3, Col 3 |



### Usage

We use Python v3.7, PyTorch v1.10, and mmcv 1.3.9 for the experiments. Our experiments are based on MMPose.




```
git clone https://github.com/open-mmlab/mmcv.git
```






## Contributing

See [the contributing file](CONTRIBUTING.md)!

PRs accepted.

Small note: If editing the Readme, please conform to the [standard-readme](https://github.com/RichardLitt/standard-readme) specification.


## License

[MIT © Richard McRichface.](../LICENSE)
