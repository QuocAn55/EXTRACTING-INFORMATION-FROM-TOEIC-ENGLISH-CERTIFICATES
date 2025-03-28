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

To lableling data, we used the OpenLabeling tool to annotate the images.

## Method
<p align="center">
  <img width="600" src="https://github.com/QuocAn55/EXTRACTING-INFORMATION-FROM-TOEIC-ENGLISH-CERTIFICATES/blob/main/Images/Method.png?raw=true" alt="Method">
  <br>
  <em>Figure 2: Method for extracting information from TOEIC certificates.</em>
</p>
In this study, we implemented an object detection and text extraction system to extract key information from TOEIC certificates. We used YOLOv5 for object detection, leveraging its speed and accuracy. YOLOv5's architecture consists of CSPDarknet (Backbone), PANet (Neck), and YOLO Layer (Head) to detect text regions effectively.

For text extraction, we applied EasyOCR, a pre-trained OCR model based on PyTorch, using CRAFT for text detection and CRNN (ResNet + LSTM + CTC) for character recognition. The system processes cropped text regions detected by YOLOv5 and extracts key fields from TOEIC certificates. Our experiments yielded promising results, demonstrating the effectiveness of this approach in automated information extraction.
## Experimental results


<p align="center">
  <img width="600" src="https://github.com/QuocAn55/EXTRACTING-INFORMATION-FROM-TOEIC-ENGLISH-CERTIFICATES/blob/main/Images/Model.png?raw=true" alt="Model">
  <br>
  <em>Figure 3: Evaluation of results using Accuracy and Character Error Rate (CER).</em>
</p>

Overall, the character recognition and information extraction model performs quite accurately for score-related labels. Specifically, the accuracy for the "TOTAL SCORE" label is 0.85 with a character error rate of 0.07, "LISTENING SCORE" achieves 0.84 accuracy with a 0.12 error rate, and "READING SCORE" reaches 0.81 accuracy with a 0.14 error rate.
However, for date-related labels, the accuracy is significantly lower: "DOB" (Accuracy: 0.05, Error Rate: 0.17), "TEST DATE" (Accuracy: 0.27, Error Rate: 0.16), and "VALID UNTIL" (Accuracy: 0.25, Error Rate: 0.17). The main reason for this lower performance is the incorrect or extra characters extracted in some cases.
