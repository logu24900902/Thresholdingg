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

```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread("shinchan Image.jpeg")  # Replace with your image file path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)  # Convert to grayscale
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert from BGR to RGB for display
plt.title("Original Image")
plt.axis('off')

# Use Global thresholding to segment the image

_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)

# Use Adaptive thresholding to segment the image

adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)

# Use Otsu's method to segment the image 

_, otsu_thresholded = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)


# Display the results

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
<br>
<img width="395" height="244" alt="image" src="https://github.com/user-attachments/assets/70cf03ca-7bee-4fe4-b6b4-bd19148df113" />

<br>
<br>
<br>
<br>

### Global Thresholding
<br>
<img width="393" height="252" alt="image" src="https://github.com/user-attachments/assets/2fe39cbe-4bc0-4a6a-b329-ce4f0cba0d62" />

<br>
<br>
<br>
<br>

### Adaptive Thresholding
<br>
<img width="386" height="252" alt="image" src="https://github.com/user-attachments/assets/82bc0159-f60d-433c-ab22-7cf66f21ff15" />

<br>
<br>
<br>
<br>

### Optimum Global Thesholding using Otsu's Method
<br>
<img width="396" height="250" alt="image" src="https://github.com/user-attachments/assets/473c79df-b3e3-4dc6-86a0-9619f2538715" />

<br>
<br>
<br>
<br>


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
