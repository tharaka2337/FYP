# How to Train and Deploy YOLO Models with Ultralytics (YOLO11, YOLOv8, and YOLOv5)
Tutorials and examples showing how to train and deploy Ultralytics YOLO models.

## Train YOLO Models

**Option 1. With Google Colab**

Click below to acces a Colab notebook for training YOLO models. It makes training a custom YOLO model as easy as uploading an image dataset and running a few blocks of code.

<a href="https://colab.research.google.com/github/EdjeElectronics/Train-and-Deploy-YOLO-Models/blob/main/Train_YOLO_Models.ipynb" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

**Option 2. On a Local PC**

I wrote an article that steps through the process of training YOLO models on a local PC equipped with an NVIDIA GPU. Check it out at the link below.

[How to Train YOLO 11 Object Detection Models Locally with NVIDIA](https://www.ejtech.io/learn/train-yolo-models)


## Deploy YOLO Models
The `yolo_detect.py` script provides a basic example that shows how to load a model, run inference on an image source, parse the inference results, and display boxes around each detected class in the image. This script shows how to work with YOLO models in Python, and it can be used as a starting point for more advanced applications. 

To download `yolo_detect.py` from this repository, issue: 

```
curl --output yolo_detect.py https://raw.githubusercontent.com/EdjeElectronics/Train-and-Deploy-YOLO-Models/refs/heads/main/yolo_detect.py
```

To run inference with a yolov8s model on a USB camera at 1280x720 resolution, issue:

```
python yolo_detect.py --model yolov8s.pt --source usb0 --resolution 1280x720
```

Here are all the arguments for yolo_detect.py:

- `--model`: Path to a model file (e.g. `my_model.pt`). If the model isn't found, it will default to using `yolov8s.pt`.
- `--source`: Source to run inference on. The options are:
    - Image file (example: `test.jpg`)
    - Folder of images (example: `my_images/test`)
    - Video file (example: `testvid.mp4`)
    - Index of a connected USB camera (example: `usb0`)
    - Index of a connected Picamera module for Raspberry Pi (example: `picamera0`)
- `--thresh` (optional): Minimum confidence threshold for displaying detected objects. Default value is 0.5 (example: `0.4`)
- `--resolution` (optional): Resolution in WxH to display inference results at. If not specified, the program will match the source resolution. (example: `1280x720`)
- `--record` (optional): Record a video of the results and save it as `demo1.avi`. (If using this option, the `--resolution` argument must also be specified.)

### Deploy on Raspberry Pi
The Raspberry Pi 4 and 5 are just powerful enough to run nano and small-sized YOLO models in real time. The article linked below walks through how to run YOLO models on the Raspberry Pi.

[How to Run YOLO Detection Models on the Raspberry Pi](https://www.ejtech.io/learn/yolo-on-raspberry-pi)
