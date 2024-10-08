# THRESHOLDING
# Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

# Software Required
Anaconda - Python 3.7
OpenCV
## Algorithm
# Step1:

Load the necessary packages.
# Step2:

Read the Image and convert to grayscale.
# Step3:

Use Global thresholding to segment the image.
# Step4:

Use Adaptive thresholding to segment the image.
# Step5:

Use Otsu's method to segment the image and display the results.
## Program
```
Developed By :Ganji Muni Madhuri
Register Number : 212223230060
```
# Load the necessary packages:
```
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
# Read the Image and convert to grayscale
```
image = cv2.imread('SF23.jpg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('SF23.jpg',0)
```
# Use Global thresholding to segment the image
```
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
# Use Adaptive thresholding to segment the image
```
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
# Use Otsu's method to segment the image
```
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
# Display the results
```
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
# Output
# Original Image
![image](https://github.com/user-attachments/assets/285d297a-0dc4-4bb4-b9bc-caa4419dce0c)


# Global Thresholding
![image](https://github.com/user-attachments/assets/45fd6481-d8b6-4908-b267-dd29d16f0e87)

![image](https://github.com/user-attachments/assets/a6078362-f8ee-446c-959a-d411feb33898)
![image](https://github.com/user-attachments/assets/9853ac6e-f289-42b4-af58-968264dfcbcb)


# Adaptive Thresholding
![image](https://github.com/user-attachments/assets/363c9f00-1fe7-47ba-870e-7f231bc9f6e1)

![image](https://github.com/user-attachments/assets/276116fe-d1dc-4038-b6fe-386fc715104d)


# Optimum Global Thesholding using Otsu's Method
![image](https://github.com/user-attachments/assets/7afd382a-441c-412b-a554-258e188b758d)

# Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
