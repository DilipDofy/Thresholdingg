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


```python

#Developed by : DILIP M P
#Register No: 212223230048

# Load the necessary packages

import numpy as np
import matplotlib.pyplot as plt
import cv2

# Read the Image and convert to grayscale

image = cv2.imread(r"C:\Users\admin\Downloads\Taj mahal.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread(r"C:\Users\admin\Downloads\Taj mahal.jpg",0)

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
![Screenshot 2025-04-29 082329](https://github.com/user-attachments/assets/cae91454-952e-455a-8022-8b83ce4af3d6)



### Global Thresholding

![Screenshot 2025-04-29 082415](https://github.com/user-attachments/assets/87759bcb-43d5-49a5-a044-0a6fc2388bef)

![Screenshot 2025-04-29 082415](https://github.com/user-attachments/assets/40309c0e-7727-4148-8f4b-8b3c148227be)

![Screenshot 2025-04-29 082436](https://github.com/user-attachments/assets/6fb06b27-f1ec-44a7-98ae-f0f74bc869e9)

![Screenshot 2025-04-29 082451](https://github.com/user-attachments/assets/f6a5272a-887e-4ead-99ca-02a0663f2b08)

![Screenshot 2025-04-29 082512](https://github.com/user-attachments/assets/99d41e5f-0fd7-4498-a5a9-45b609e26301)




### Adaptive Thresholding

![Screenshot 2025-04-29 082615](https://github.com/user-attachments/assets/66b6ed78-4312-4847-bad4-f7f45ce585cd)

![Screenshot 2025-04-29 082637](https://github.com/user-attachments/assets/65b1132f-9670-475a-9546-712a54e759c8)



### Optimum Global Thesholding using Otsu's Method

![Screenshot 2025-04-29 082548](https://github.com/user-attachments/assets/fcecbdfe-677c-4d3c-b689-baf142ca0974)




## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
