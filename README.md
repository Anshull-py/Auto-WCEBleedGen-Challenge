# Auto-WCEBleedGen-Challenge
Wireless capsule endoscopy (WCE) is considered the criterion standard for detecting small-bowel diseases. Manual examination of WCE is time-consuming and can benefit from automatic detection using artificial intelligence (AI).
Here the teaam has employed Faster R-CNN for detection of the bleeding frame. 

### Install
  1. [MMdetection](https://mmdetection.readthedocs.io/en/v2.15.1/)

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
python demo/image_demo.py Datasets/data/test_images config_bleedingfnn.py directoryPath_where_model.pth file is saved
```
