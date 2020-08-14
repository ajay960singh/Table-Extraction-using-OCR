# Table-Extraction-using-OCR

### Description

This is a Python implementation for converting tables in PDF documents to Excel format using Optical Character Recognition (OCR) and OpenCV. The input PDF document can be found in `input/test_input.pdf`. The screenshot of the PDF document used is shown below
<p align='middle'>
<img width = '500' src = "https://user-images.githubusercontent.com/34549910/90256560-7f376500-de78-11ea-8c98-0599d8f8b905.png">
</p>

The table is extracted and converted to excel in `output/pdf2excel.xlsx`.

### Requirements

The code uses `python3.6` and the dependencies required are described in `requirements.txt` and can be installed using the following command:

                                            pip install -r requirements.txt
  
  
### How does it work

The code, as shown in `main.ipynb`, consists of a few steps:

1. **Row detection** : The first step is to detect the rows in the table. We use morphological tranformation provided by `OpenCV` to extract horizontal and vertical lines and combine them to detect the table. After detection, we look for contours in the table to detect the rows and crop them.<br/><br/>
 <p align = 'middle'>                                                 
<img width="800" align ="middle" alt="Screenshot 2020-08-13 at 3 31 25 PM" src="https://user-images.githubusercontent.com/34549910/90106672-592b9b00-dd7a-11ea-95d3-518b13943656.png">
</p>

2. **OCR** : The next step is to take the cropped rows and apply OCR to extract text and bounding box for location. We use `pytesseract` to perform OCR. It's important to to capture the location to account for multiple words in the same column and misssing values. <br/><br/>

 <p align = 'middle'>   
      <img width="800" alt="Screenshot 2020-08-13 at 4 00 30 PM" src="https://user-images.githubusercontent.com/34549910/90109297-30a5a000-dd7e-11ea-839c-a57fc86303cb.png">
</p>  
      
3. **Post-processing** : The final step is to match the position of bounding boxes with texts and convert the format to an Excel file. 






                                          
                                          
