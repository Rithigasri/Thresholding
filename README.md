# EXPERIMENT 09: THRESHOLDING OF IMAGES
## AIM:
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## SOFTWARE REQUIRED:
1. Anaconda - Python 3.7
2. OpenCV

## ALGORITHM:

### Step 1:
Load the necessary packages.

### Step 2:
Read the Image and convert to grayscale.

### Step 3:
Use Global thresholding to segment the image.

### Step 4:
Use Adaptive thresholding to segment the image.

### Step 5:
Use Otsu's method to segment the image.

### Step 6:
Display the results.

## PROGRAM:

```
# Load the necessary packages
import numpy as np
import matplotlib.pyplot as plt
import cv2

# Read the Image and convert to grayscale
image = cv2.imread("pic.png",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("pic.png",0)

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
## OUTPUT:

### Original Image:
![image](https://user-images.githubusercontent.com/93427256/235286386-1c7f4752-e476-40a5-ab1e-4c4dffc4c1ba.png)  

### Global Thresholding:
![image](https://user-images.githubusercontent.com/93427256/235286399-1cfbb0fe-d8db-4283-932d-50f019d64bfd.png)  
![image](https://user-images.githubusercontent.com/93427256/235286406-86f2a82a-6c95-4ab7-a052-dbaaaa0021f1.png)  
![image](https://user-images.githubusercontent.com/93427256/235286414-b34dac29-98a1-4861-845b-74359bb62a9b.png)  
![image](https://user-images.githubusercontent.com/93427256/235286426-0d83fb85-1f0b-4c79-8ac4-5118c8cb7b2f.png)  
![image](https://user-images.githubusercontent.com/93427256/235286432-4cffdf6c-710c-404d-8265-65ad0d45ba45.png)  

### Adaptive Thresholding:
![image](https://user-images.githubusercontent.com/93427256/235286456-2090f4f9-f488-4af5-8f23-2fd058110f38.png)  
![image](https://user-images.githubusercontent.com/93427256/235286464-7f841245-5918-40a5-a3a9-6ff9a27df81f.png)  

### Optimum Global Thesholding using Otsu's Method:
![image](https://user-images.githubusercontent.com/93427256/235286446-c2c5844a-7bc1-42f1-b9c4-29ad61c61f2b.png)  



## RESULT:
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

