# Object Detection and Tracking Pipeline

Here we will build a pipeline with two steps, object detection and object
tracking.

The following provides a brief outline on the entire process, and you are
encouraged to find more models that suit your needs.

## Object Dectection

To run object detection, we provide you with some popular options:

1. YOLOv8 from Ultralytics
2. facebook/detr-resnet-50 from huggingface
3. fasterrcnn_resnet50_fpn from torchvision

## Object Tracking

To perform object tracking, we provide you with some popular options:

1. ByteTrack : https://github.com/ifzhang/ByteTrack
2. Oc_Sort : https://github.com/noahcao/OC_SORT

## Assertion

As an example we can have an assertion that objects given the same
id by the tracking model must be within a certain distance from each other
across frames.
I.e. A person given id A by the tracking model can only move so far across a
frame, if the gap is too much, then the detection by the tracking model is wrong,
or if the object vanishes and returns after a long time, the detection given by
the object detection model is wrong and needs to be rolled back.
It is up to you to define this threshold.

## Dataset

Download the MOT17 dataset from this website: https://motchallenge.net/data/MOT17/.
If you are running the docker container, then copy the dataset into the container
and then unzip the dataset and place it in the video directory as follows:

eg.
```
video/
|
|
--MOT17/
    |
    |
    --test/
    |
    |
    --train/
```

You can choose to reduce the size of the dataset by copying only a subset of the images
by changing the following line in the dockerfile `COPY MOT17/ /MOT17/`.

## Sample
In the container, there is a sample notebook that has some sample code on loading the dataset
and utilizing the example models.

Note that all the given models work given the dependencies of the requirements file and the
dockerfile.