# EXPERIMENT 8 – THRESHOLDING
# Name: DHIVYASHREE R
# REGNO :212225040077

## Aim

To segment the image using Global Thresholding, Adaptive Thresholding and Otsu's Thresholding using Python and OpenCV.

## Software Required

1. Anaconda – Python 3.7
2. OpenCV
3. NumPy
4. Matplotlib

## Algorithm

**Step 1:** Import the necessary packages such as OpenCV, NumPy and Matplotlib.

**Step 2:** Read the input image and convert it into a grayscale image.

**Step 3:** Apply Global Thresholding using a threshold value of 127 to segment the image.

**Step 4:** Apply Adaptive Thresholding using the Gaussian method.

**Step 5:** Apply Otsu's method for optimal thresholding and display the original image and all segmented images.

## Program

```python
# Step 1: Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
```
# Step 2: Read the image and convert to grayscale
image = cv2.imread('me.jpeg')  # Replace with your image file path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
```
```
# Original Image
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Original Image")
plt.axis('off')
```
```
# Step 3: Use Global Thresholding to segment the image
# Apply global thresholding with a threshold value of 127
_, global_thresholded = cv2.threshold(
    gray_image, 127, 255, cv2.THRESH_BINARY
)
```
```
# Step 4: Use Adaptive Thresholding to segment the image
# Apply adaptive thresholding using Gaussian method
adaptive_thresholded = cv2.adaptiveThreshold(
    gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
    cv2.THRESH_BINARY, 11, 2
)
```
```
# Step 5: Use Otsu's method to segment the image
# Apply Otsu's method for optimal thresholding
_, otsu_thresholded = cv2.threshold(
    gray_image, 0, 255,
    cv2.THRESH_BINARY + cv2.THRESH_OTSU
)
```
```
# Global Thresholding
plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')
```
```
# Adaptive Thresholding
plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')
```
```
# Otsu's Method
plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')
```
```
# Show the plot
plt.tight_layout()
plt.show()
```

## Output

### 1. Original Image
<img width="145" height="209" alt="image" src="https://github.com/user-attachments/assets/989f4a87-4a9b-4174-b05a-154843ab24f8" />


### 2. Global Thresholding
<img width="232" height="287" alt="image" src="https://github.com/user-attachments/assets/89f1d150-56fb-4684-9897-593a7692c972" />


### 3. Adaptive Thresholding
<img width="281" height="307" alt="image" src="https://github.com/user-attachments/assets/930e4f68-00df-4cc2-b008-3d9ccc830ce9" />

### 4. Optimum Global Thresholding using Otsu's Method
<img width="207" height="280" alt="image" src="https://github.com/user-attachments/assets/0e1c9c17-8ade-4658-85a3-120310a220aa" />

## Result

Thus, the images are segmented using Global Thresholding, Adaptive Thresholding and Optimum Global Thresholding using Otsu's Method with Python and OpenCV.
