# Auto-WCEBleedGen-Challenge
Wireless capsule endoscopy (WCE) is the criterion standard for detecting small-bowel diseases. Manual examination of WCE is time-consuming and can benefit from automatic detection using artificial intelligence (AI). Here, the team has employed Faster R-CNN, single-shot detector (SSD), YOLO-v1, YOLO-F to detect the bleeding frame. Faster R-CNN achieved better result compared to others mentioned architecture. Faster R-CNN state-of-the-art performance at the time of its publication on VOC12, VOC10(with additional data), and VOC07. Therefore, the architecture use has been explored in many research fields for object detection problems.

### Install
TorchVision: 0.8.1+cu101 \
OpenCV: 4.8.0 \
MMCV: 1.3.11 \
MMCV Compiler: GCC 7.3 \
MMCV CUDA Compiler: 10.1 \
[MMDetection: 2.15.1+] (https://mmdetection.readthedocs.io/en/v2.15.1/) 

### Steps
MMdetection uses a configuration .py file to build and train models. To run the code, first and foremost, install the specified version of mmdetection library.

config_file name: config_bleedingfnn.py

Run the following command in the terminal:
  1. Train
```
python tools/train.py config_file
```
  2. validation: bbox
```
python tools/test.py config_file directoryPath_where_best_model.pth file is saved  --eval bbox
```
  3. validation: Image
```
python tools/test.py config_file directoryPath_where_model.pth file is saved  --show
```
  4. Test (on a particular image):
```
python demo/image_demo.py test_images config_file directoryPath_where_model.pth file is saved
```
### Results
| Metrics            | Value  |
|--------------------|--------|
| Average Precision  | 0.355  |
| Average Recall     | 0.626  |
| Average F1         | 0.4081 |

![Test Results](./ScreenShots/T2_5.png =100x20)

