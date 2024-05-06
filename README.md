# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages.

### Step2:
Read the Image and convert to grayscale.
### Step3:
Use Global thresholding to segment the image.
### Step4:
Use Adaptive thresholding to segment the image.
### Step5:
Use Otsu's method to segment the image and display the results.
## Program
```
Developed By :VAISHNAVI S
Register Number : 212222230165
```
```python
# Load the necessary packages


import numpy as np
import matplotlib.pyplot as plt
import cv2


# Read the Image and convert to grayscale


image = cv2.imread('kitty.jpeg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('kitty.jpeg',0)

# Use Global thresholding to segment the image

ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)


# Use Adaptive thresholding to segment the image


thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Use Otsu's method to segment the image 

ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)


# Display the results

titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
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
## Output

### Original Image
![327146408-90916955-39cd-46a8-9334-7e0dca43f3a1](https://github.com/Vaishnavi-saravanan/Thresholdingg/assets/118541897/687bd14d-efe1-48da-804f-040719c8cb0e)

### Global Thresholding
![327146636-5c95cd81-7b56-4db0-bcaa-45837cb935b5](https://github.com/Vaishnavi-saravanan/Thresholdingg/assets/118541897/b5314183-a3a0-4842-921c-2c8b12857504)

![327146636-5c95cd81-7b56-4db0-bcaa-45837cb935b5](https://github.com/Vaishnavi-saravanan/Thresholdingg/assets/118541897/6c11df02-acfe-4b3e-9475-a0c998470c07)

![327146760-ad092623-ed88-4235-947a-eaa6e1a42158](https://github.com/Vaishnavi-saravanan/Thresholdingg/assets/118541897/8e137632-5559-47ee-bdd0-d0f86ddcfbd2)

![327146760-ad092623-ed88-4235-947a-eaa6e1a42158](https://github.com/Vaishnavi-saravanan/Thresholdingg/assets/118541897/a0b7795b-bcb6-4d56-ac2a-d1b257af81bc)

![327146894-f23e3011-40d3-42e3-975c-d9aae46ede44](https://github.com/Vaishnavi-saravanan/Thresholdingg/assets/118541897/42bc3cb1-4c5e-46a6-977f-ce512eac5a8d)

### Adaptive Thresholding
![327147478-436d3d17-6cca-4b6f-8131-3f483e79b6bc](https://github.com/Vaishnavi-saravanan/Thresholdingg/assets/118541897/b9a1dcfb-470a-4e18-b3e4-31e78d336494)

![327147478-436d3d17-6cca-4b6f-8131-3f483e79b6bc](https://github.com/Vaishnavi-saravanan/Thresholdingg/assets/118541897/64196ead-9887-477d-8ad9-4d7bffa6ccf4)

### Optimum Global Thesholding using Otsu's Method

![327148240-004d1d9b-a6ef-44e8-b746-54874d0ace04](https://github.com/Vaishnavi-saravanan/Thresholdingg/assets/118541897/814f6c9a-aa70-4488-aa3a-24be747675d2)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
