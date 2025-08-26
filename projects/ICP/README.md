# ID Card OCR

In this workflow, you will take a dataset of 
various ID cards and build a pipeline to classify 
which country they belong to.
The pipeline will have 3 nodes described below:

## Image Enhancement Step
The first step of the pipeline will be to
use the cv2 library from python to enchance the
base image if need be.
    
You may increase the sharpness or the brightness
of the image or make no changes at all. This is just
a sample, as you may make other operations that
can help increase the accuracy of the pipeline.

## Channel Selection Step
The next step is choose to extract a specific color
channel from the image array. You may choose one color
or a combination of colors or the orignal image as well.

## OCR Step
The final step is to actually perform actual ocr.
To do this, we provide two initial ocr models:

1. EasyOcr
2. Tesseract

## Assertion

As an example, we provide a very simple assertion to check the 
accuracy of the pipeline.

As it is an ocr pipeline, you can choose to check the date
such that the format of the date is correct, i.e. month is
between 1-12, and so on.

## Dataset

The dataset that is provided here is the `lansinuote/ocr_id_card` from HuggingFace.
Please note that it is in Chinese, and you will have to configure the ocr models
to handle Chinese characters.

## Sample
In the container, there is a sample notebook that has some sample code on loading the dataset
and utilizing the example models.