# Extracting information from Toeic English certificates

## Abstract
In this paper, we develop a key information extraction system for images of TOEIC English certificates for the Listening and Reading skills. We collected our own dataset, applied Data Augmentation techniques to expand the dataset, and manually labeled the data. Our approach utilizes the YOLOv5 model to detect text within images, followed by EasyOCR to recognize characters and extract key information fields. The initial results demonstrate promising accuracy in recognizing and extracting the desired key fields from TOEIC certificates.

## Dataset
We use the TOEICText dataset, which consists of approximately 600 images of TOEIC English certificates. Since the data contains a lot of personal and sensitive information, instead of collecting it, we created a new dataset following the process below.

<p align="center">
  <img width="600" src="https://github.com/QuocAn55/EXTRACTING-INFORMATION-FROM-TOEIC-ENGLISH-CERTIFICATES/blob/main/Images/Build_dataset.png?raw=true" alt="Build_dataset">
  <br>
  <em>Figure 1: Dataset process.</em>
</p>

## Method
<p align="center">
  <img width="600" src="https://github.com/QuocAn55/EXTRACTING-INFORMATION-FROM-TOEIC-ENGLISH-CERTIFICATES/blob/main/Images/Method.png?raw=true" alt="Method">
  <br>
  <em>Figure 2: Method for extracting information from TOEIC certificates.</em>
</p>

## Result
<p align="center">
  <img width="600" src="https://github.com/QuocAn55/EXTRACTING-INFORMATION-FROM-TOEIC-ENGLISH-CERTIFICATES/blob/main/Images/Model.png?raw=true" alt="Model">
  <br>
  <em>Figure 3: Evaluation of results.</em>
</p>

