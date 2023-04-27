# Thresholding of Images
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
Anaconda - Python 3.7
OpenCV
## Algorithm
### Step1:
Load the necessary packages.

### Step2:
Read the Image and convert to grayscale.

### Step3:
Use Global thresholding to segment the image

### Step4:
Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image.

### Step6:
Display the results.

Program
```
NAME: MITTA BHAVISHYA REDDY
REG NO: 212221230061

# Load the necessary packages

import numpy as np
import matplotlib.pyplot as plt
import cv2



# Read the Image and convert to grayscale

image = cv2.imread("shinchan.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("shinchan.jpg",0)


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
![dip b9-1](https://user-images.githubusercontent.com/94679395/234800507-47e9eb31-e4ba-4400-94ce-dd25f31ab0b6.jpg)


### Global Thresholding
![b9-2](https://user-images.githubusercontent.com/94679395/234800556-7cc152c1-7c9b-48e4-946c-850523babe95.jpg)
![b9-3](https://user-images.githubusercontent.com/94679395/234800592-c4617125-c7ed-487f-a57e-d9de5418ba13.jpg)
![b9-4](https://user-images.githubusercontent.com/94679395/234800632-08cf71aa-e1c0-4663-b57c-6984e3a7a159.jpg)
![b9-6](https://user-images.githubusercontent.com/94679395/234800681-9c25ed11-918b-4fad-837d-461fd45a96c1.jpg)
![b9-7](https://user-images.githubusercontent.com/94679395/234800725-399bab57-7576-4e6a-a952-77e7ecd506ae.jpg)


### Adaptive Thresholding
![b9-9](https://user-images.githubusercontent.com/94679395/234800782-869d6188-7ea1-4c79-934d-022f604a6248.jpg)
![b9-10](https://user-images.githubusercontent.com/94679395/234800839-0f5c8117-bde6-479b-81a3-f093908ac4f0.jpg)


### Optimum Global Thesholding using Otsu's Method
![b9-8](https://user-images.githubusercontent.com/94679395/234800895-99549832-c358-49c9-82ea-2c13c5d8a310.jpg)



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

