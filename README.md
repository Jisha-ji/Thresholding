# EX. NO: 8 THRESHOLDING

## Aim

To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1: 
Load all the libraries

### Step2: 
Read the image and convert to grayscale

### Step3: 
Use Global Thresholding to segment the image. Apply global thresholding with a threshold value of 127

### Step4: 
Use Adaptive Thresholding to segment the image. Apply adaptive thresholding using Gaussian method

### Step5: 
Use Otsu's method to segment the image. Apply Otsu's method for optimal thresholding

## Program

### DEVELOPED BY : JISHA BOSSNE SJ
### REG NO : 212224230106
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
```
# Step 2: Read the image and convert to grayscale
image = cv2.imread('Qn8_thresholding.tif')  # Replace with your image file path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)  # Convert to grayscale
```
```
# Original Image
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert from BGR to RGB for display
plt.title("Original Image")
plt.axis('off')
```
```
# Step 3: Use Global Thresholding to segment the image
# Apply global thresholding with a threshold value of 127
_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)
```
```
# Step 4: Use Adaptive Thresholding to segment the image
# Apply adaptive thresholding using Gaussian method
adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)
```
```
# Step 5: Use Otsu's method to segment the image
# Apply Otsu's method for optimal thresholding
_, otsu_thresholded = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)
```
```

# Global Thresholding
plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')

# Adaptive Thresholding
plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')

# Otsu's Method
plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')

# Show the plot
plt.tight_layout()
plt.show()
```
## Output

### Original Image

<img width="290" height="292" alt="image" src="https://github.com/user-attachments/assets/fe582b46-10bc-40e5-ab62-e05419f2bcb2" />


### Global Thresholding

<img width="322" height="310" alt="image" src="https://github.com/user-attachments/assets/3e85f9dc-4221-47f8-a67f-4714b9a0f524" />


### Adaptive Thresholding

<img width="317" height="315" alt="image" src="https://github.com/user-attachments/assets/d173f4d7-d510-4b0f-830a-6afbe65eefcb" />


### Optimum Global Thesholding using Otsu's Method

<img width="352" height="318" alt="image" src="https://github.com/user-attachments/assets/d8b7dfa7-a233-4e41-a56e-8692891fddd1" />

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
