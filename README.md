# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step 1:
Import the required libraries such as OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the input image using OpenCV and convert it to grayscale using cv2.cvtColor().

### Step 3:
Apply global thresholding using cv2.threshold() with a fixed threshold value (e.g., 127).

### Step 4:
Apply adaptive thresholding using cv2.adaptiveThreshold() with Gaussian or mean method.

### Step 5:
Apply Otsu's thresholding using cv2.threshold() with the cv2.THRESH_OTSU flag, and display all results using matplotlib.pyplot.

## Program
### NAME: HAREVASU S
### REGISTRATION NUMBER :212223230069

```python
# Load the necessary packages

import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale

image = cv2.imread('img_1.jpg')  
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY) 

# Use Global thresholding to segment the image

_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)


# Use Adaptive thresholding to segment the image
adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)



# Use Otsu's method to segment the image 

_, otsu_thresholded = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)


# Display the results
# Create a 2x2 subplot layout

plt.figure(figsize=(10, 8))

# Original Image
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for correct color display
plt.title("Original Image")
plt.axis('off')

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
![image](https://github.com/user-attachments/assets/6857a6e5-ecf4-48d8-a31f-264a858039ad)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
