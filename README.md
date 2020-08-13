# Table-Extraction-using-OCR

### Description

This is a Python implementation for converting tables in PDF documents to Excel format using Optical Character Recognition (OCR) and OpenCV.

### Requirements

The code uses `python3.6` and the dependencies required are described in `requirements.txt` and can be installed using the following command:

                                            pip install -r requirements.txt
  
  
### How does it work

The code, as shown in `main.ipynb`, consists of a few steps:

1. Row detection : The first step is to detect the rows in the table. We use morphological tranformation provided by `OpenCV` to extract horizontal and vertical lines and combine them to detect the table. After detection, we look for contours in the table to detect the rows and crop them.<br/>
                                                  <img width="458" alt="Screenshot 2020-08-13 at 3 31 25 PM" src="https://user-images.githubusercontent.com/34549910/90106672-592b9b00-dd7a-11ea-95d3-518b13943656.png">


2. OCR : The next step is to take the cropped rows and apply OCR to extract text and bounding box for location. We use `pytessaract` to perform OCR. As a preporcessing step, we remove the watermark using `Open CV`. It's important to to capture the location too as 
                                          
                                          
