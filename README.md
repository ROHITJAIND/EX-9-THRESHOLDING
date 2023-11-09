# EX-9 THRESHOLDING
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;**DATE:** 18.10.2023<br>
### Aim: 
To segment the image using global thresholding,adaptive thresholding and Otsu's thresholding using OpenCV. 
### Software Required:
Anaconda - Python 3.7 , OpenCV
### Algorithm:
- Step1: Load the necessary packages.
- Step2: Read the Image and convert to grayscale.
- Step3: Use Global thresholding to segment the image.
- Step4: Use Adaptive thresholding to segment the image.
- Step5: Use Otsu's method to segment the image.
```
Developed By: ROHIT JAIN D
Register No: 212222230120
```
### Program:
- Load the necessary packages.
  ```Python
  import cv2
  import numpy as np
  import matplotlib.pyplot as plt
  ```
  - Read the Image and convert to grayscale.
  ```Python
  image=cv2.imread("flo.jpg",1)
  image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
  image_gray=cv2.imread("flo.jpg",0)
  ```
- Use Global thresholding to segment the image.
  ```Python
  ret,thresh_dipt1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
  ret,thresh_dipt2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
  ret,thresh_dipt3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
  ret,thresh_dipt4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
  ret,thresh_dipt5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
  ```
- Use Otsu's method to segment the image.
  ```Python
  ret,thresh_dipt6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
  ```
- Use Adaptive thresholding to segment the image.
  ```Python
  thresh_dipt7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
  thresh_dipt8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
  ```
- Display the results.
  ```Python
  titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
        ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
  images=[image_gray,thresh_dipt1,thresh_dipt2,thresh_dipt3,thresh_dipt4,thresh_dipt5,thresh_dipt6,thresh_dipt7,thresh_dipt8]
  plt.title("Original Image")
  plt.imshow(image)
  plt.axis("off")
  plt.show()
  for i in range(0,9):
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()
  ```
### Output:
<div align="center">
  <img height=16% width=24% src="https://github.com/ROHITJAIND/EX-9-THRESHOLDING/assets/118707073/bd2932d3-c4b6-4fa9-9cef-64b82537452f">
  <img height=16% width=24% src="https://github.com/ROHITJAIND/EX-9-THRESHOLDING/assets/118707073/8a9f5ba2-1530-4d31-a7bf-d678cf2a1373">
</div>
<br>
<img height=16% width=24% src="https://github.com/ROHITJAIND/EX-9-THRESHOLDING/assets/118707073/6369ecf1-c4e7-470d-b31f-e0461a95e347">
<img height=16% width=24% src="https://github.com/ROHITJAIND/EX-9-THRESHOLDING/assets/118707073/ef410220-311c-4ac2-8c91-c729ea08eb10">
<img height=16% width=24% src="https://github.com/ROHITJAIND/EX-9-THRESHOLDING/assets/118707073/54cea3b1-ffa8-46a1-b0a6-fcdc5c5f3b0b">
<img height=16% width=24% src="https://github.com/ROHITJAIND/EX-9-THRESHOLDING/assets/118707073/967a322e-d54f-46b8-8712-075702edf43b">
<img height=16% width=24% src="https://github.com/ROHITJAIND/EX-9-THRESHOLDING/assets/118707073/2a81045e-5f38-44db-a129-4acbcc0e3aea">
<img height=16% width=24% src="https://github.com/ROHITJAIND/EX-9-THRESHOLDING/assets/118707073/6eba90df-0f1c-45fd-9fa9-42736d5f24f6">
<img height=16% width=24% src="https://github.com/ROHITJAIND/EX-9-THRESHOLDING/assets/118707073/ed838784-71d3-40da-a1a3-9db9026108a0">
<img height=16% width=24% src="https://github.com/ROHITJAIND/EX-9-THRESHOLDING/assets/118707073/c9d334a1-3ff3-4573-931f-a208e1b131c8">


### Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

