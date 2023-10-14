# EX-9 THRESHOLDING
### Aim:
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.
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
- Use Adaptive thresholding to segment the image.
  ```Python
  ret,thresh_dipt6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
  ```
- Use Otsu's method to segment the image.
  ```Python
  thresh_dipt7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
  thresh_dipt8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
  ```
- Display the results.
  ```Python
  titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
          ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
  images=[image_gray,thresh_dipt1,thresh_dipt2,thresh_dipt3,thresh_dipt4,thresh_dipt5,thresh_dipt6,thresh_dipt7,thresh_dipt8]
  for i in range(0,9):
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()
  ```
### Output:
<img height=20% width=49% src="https://github.com/ROHITJAIND/EX-9-THRESHOLDING/assets/118707073/87419e9f-2321-4244-b3ad-e3c497d171af">
<img height=20% width=49% src="https://github.com/ROHITJAIND/EX-9-THRESHOLDING/assets/118707073/fe27abb5-af35-4b15-b15a-5112fdfc5248">
<img height=20% width=49% src="https://github.com/ROHITJAIND/EX-9-THRESHOLDING/assets/118707073/2351195b-158c-481f-aa61-d3c63f55397a">
<img height=20% width=49% src="https://github.com/ROHITJAIND/EX-9-THRESHOLDING/assets/118707073/393fc999-b73f-4e49-bcf2-bee4fa5b82ca">
<img height=20% width=49% src="https://github.com/ROHITJAIND/EX-9-THRESHOLDING/assets/118707073/f96f7f91-af31-4916-9aba-7e0a9484f03b">
<img height=20% width=49% src="https://github.com/ROHITJAIND/EX-9-THRESHOLDING/assets/118707073/a0839f02-0ac6-4679-9aa9-9b51caccae05">
<img height=20% width=49% src="https://github.com/ROHITJAIND/EX-9-THRESHOLDING/assets/118707073/98fbdd5d-a038-4a47-9e9a-a47940193ca6">
<img height=20% width=49% src="https://github.com/ROHITJAIND/EX-9-THRESHOLDING/assets/118707073/f5e1db82-b216-4515-84a1-5e6de15c9b70">
<img height=20% width=49% src="https://github.com/ROHITJAIND/EX-9-THRESHOLDING/assets/118707073/b3dd9514-6fcc-4b7b-91c0-7e5980f1cea5">

### Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

