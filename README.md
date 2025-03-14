# YOLOv8 with CBAM Attention Module for Segmentation

## Introduction
This repository provides an implementation of YOLOv8 integrated with the Convolutional Block Attention Module (CBAM) to enhance object segmentation performance. CBAM improves feature extraction by applying both channel and spatial attention mechanisms, making the model more efficient in identifying important features in images.

This implementation is adapted from [Fracture Detection Improved YOLOv8](https://github.com/RuiyangJu/Fracture_Detection_Improved_YOLOv8.git), originally designed for object detection, and modified for segmentation tasks.

## Features
- YOLOv8-based object segmentation
- CBAM attention module integrated into the model backbone
- Improved feature selection through channel and spatial attention
- Maintains real-time inference capabilities

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/hereisamara/yolov8-cbam.git
   cd yolov8-cbam
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Install Ultralytics YOLOv8:
   ```bash
   pip install ultralytics
   ```

## CBAM Integration
The CBAM module has been integrated into the backbone of YOLOv8 to enhance feature extraction. The module consists of:
- **Channel Attention**: Learns which feature maps are more important.
- **Spatial Attention**: Focuses on important regions within the feature maps.

To integrate CBAM, modifications were made in the YOLOv8 backbone architecture by adding CBAM blocks after key convolutional layers.

## Model Configuration
The model configuration file is located at:
```
./ultralytics/cfg/models/v8/yolov8_CBAM_seg.yaml
```

## Training
To train the YOLOv8 model with CBAM on a custom dataset for segmentation, run the following command:
```bash
python start_train.py --data data.yaml --model ./ultralytics/cfg/models/v8/yolov8_CBAM_seg.yaml --epochs 100 --batch 16 --task segment
```

## Inference
To run inference on an image or video, use:
```bash
python segment.py --weights best.pt --source image.jpg
```

## Evaluation
To evaluate the model on a test set:
```bash
python val.py --weights best.pt --data data.yaml --task segment
```

## Results
The integration of CBAM improves segmentation accuracy by refining feature extraction. Detailed benchmark comparisons are provided in the results section.

## Acknowledgments
- [YOLOv8 by Ultralytics](https://github.com/ultralytics/ultralytics)
- [CBAM: Convolutional Block Attention Module](https://arxiv.org/abs/1807.06521)
- [Fracture Detection Improved YOLOv8](https://github.com/RuiyangJu/Fracture_Detection_Improved_YOLOv8.git)

