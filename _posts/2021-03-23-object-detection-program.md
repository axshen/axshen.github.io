---
title: A simple object detection program
categories:
- tech
layout: post
---

**Part 1 of [Video processing at scale](/tech/2021/03/09/video-processing-at-scale.html)**

The starting point for the traffic counting software I wrote while working on Pegasus was object detection on batch video data. Let's start from there.

**Data**

We'll need some data. There is this [PETS 2009 Benchmark Data](http://www.cvg.reading.ac.uk/PETS2009/a.html#s2) - Dataset S1: Person Count and Density Estimation, which has videos of a crowd of people walking around. The video data is stored in individual frames, so the following `ffmpeg` command allowed me to reconstruct a video from these frames.

```
ffmpeg -r 60 -f image2 -s 768x576 -i frame_%04d.jpg -vcodec libx264 -crf 25  -pix_fmt yuv420p test.mp4
```

**Object detection model**

I haven't been keeping up to date with the object detection literature but have heard that [YOLOv4](https://arxiv.org/abs/2004.10934v1) is a thing now ([repo](https://github.com/AlexeyAB/darknet)). So we'll use that pre-trained model. [YOLO](https://pjreddie.com/darknet/yolo/) is a model for object detection that is lightweight and performant compared to some of its counterparts. You can read the paper if you're interested to understand how the model works in detail. In previous work I've used YOLOv3.

There's a library that allows you to utilise YOLOv4 with a simple Tensorflow API called [`tf2yolov4`](https://pypi.org/project/tf2-yolov4/). To use this you need to download the [trained weights](https://github.com/AlexeyAB/darknet#pre-trained-models). The `tf2yolov4` library provides a method for converting the `.weights` files into `.h5` to be read into a tensorflow model. The [colab example](https://colab.research.google.com/github/sicara/tf2-yolov4/blob/master/notebooks/YoloV4_Dectection_Example.ipynb) is a very helpful guide for understanding this workflow. Using this library and the pretrained model weights, we can perform inference in a [Keras](https://keras.io/)-consistent manner as follows:

```
# tf2yolov4 library
from tf2_yolov4.model import YOLOv4
from tf2_yolov4.anchors import YOLOV4_ANCHORS

# Load model
model = YOLOv4(
    input_shape=(HEIGHT, WIDTH, 3),
    anchors=YOLOV4_ANCHORS,
    num_classes=80,
    training=False,
    yolo_max_boxes=100,
    yolo_iou_threshold=0.5,
    yolo_score_threshold=0.5,
)
model.load_weights("weights/yolov4.h5")
model.summary()

# Perform inference
boxes, scores, classes, valid_detections = model.predict(img)
```

**OpenCV** 

[OpenCV](https://pypi.org/project/opencv-python/) is a comprehensive computer vision library written for C++ providing optimised functions for image processing. We can use it for running inference on each frame of the video. [This tutorial](https://learnopencv.com/read-write-and-display-a-video-using-opencv-cpp-python/) provides code snippets for reading video files into frames, which we will use too.

The skeleton code for using OpenCV to read video files and providing each frame as an image

```
import cv2

cap = cv2.VideoCapture('/Users/stin/Documents/data/traffic/view1.mp4')
while cap.isOpened():
    ret, img = cap.read()

    if not ret:
        break

    # do something with img

cap.release()
cv2.destroyAllWindows()
```

Mash together the two code snippets above and that's about all of the code required to applying an object detection model to video data. All of the code can be found in [this repository](https://github.com/axshen/traffic-counter). At the moment, the code for processing the video is at `src/run_video.py`.

A simple benchmark is the time for running the program. There is the `time` shell command that allows you to determine the duration of a program. We time the program by running `time python run_video.py`. First run takes damn ages - 11 mins and 54 seconds. Plenty of room for improvement.
