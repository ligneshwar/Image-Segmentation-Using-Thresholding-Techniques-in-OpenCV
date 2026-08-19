# Image Segmentation Using Thresholding Techniques in OpenCV

## Aim

To segment an image using **Global Thresholding, Adaptive Mean Thresholding, Adaptive Gaussian Thresholding, and Otsu's Thresholding** techniques using Python and OpenCV.

---

## Description

Image segmentation is a fundamental technique in computer vision used to divide an image into meaningful regions based on pixel intensity.

This project implements four thresholding techniques:

- Global Thresholding
- Adaptive Mean Thresholding
- Adaptive Gaussian Thresholding
- Otsu's Thresholding

The results of all techniques are displayed together for easy comparison.

---

## Software Used

- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- Python
- OpenCV (`cv2`)
- NumPy
- Matplotlib

---

## Algorithm

### Step 1: Import Required Libraries

Import OpenCV, NumPy, and Matplotlib.

### Step 2: Load the Input Image

Load the image using `cv2.imread()`.

### Step 3: Check the Image

Check whether the image has been loaded successfully.

### Step 4: Convert to Grayscale

Convert the BGR image into grayscale using `cv2.cvtColor()`.

### Step 5: Apply Global Thresholding

Use a fixed threshold value of `127` to separate foreground and background pixels.

### Step 6: Apply Adaptive Mean Thresholding

Calculate the threshold value using the local mean of neighboring pixels.

### Step 7: Apply Adaptive Gaussian Thresholding

Calculate the threshold using a Gaussian-weighted neighborhood.

### Step 8: Apply Otsu's Thresholding

Automatically determine the optimal threshold value using Otsu's method.

### Step 9: Display Results

Display the original grayscale image and all thresholded images using Matplotlib.

### Step 10: Compare Results

Compare the segmentation results produced by the different thresholding techniques.

---

## Program

```python


import cv2
import numpy as np
import matplotlib.pyplot as plt



image_path = r"C:\Users\admin\Downloads\m.jpg"

image = cv2.imread(image_path)

# Check whether the image is loaded successfully
if image is None:
    print("Error: Image could not be loaded.")
    print("Please check the image path.")
    exit()



gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)


threshold_value = 127

_, global_threshold = cv2.threshold(
    gray,
    threshold_value,
    255,
    cv2.THRESH_BINARY
)



adaptive_mean = cv2.adaptiveThreshold(
    gray,
    255,
    cv2.ADAPTIVE_THRESH_MEAN_C,
    cv2.THRESH_BINARY,
    11,
    2
)



adaptive_gaussian = cv2.adaptiveThreshold(
    gray,
    255,
    cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
    cv2.THRESH_BINARY,
    11,
    2
)


otsu_threshold_value, otsu_threshold = cv2.threshold(
    gray,
    0,
    255,
    cv2.THRESH_BINARY + cv2.THRESH_OTSU
)



plt.figure(figsize=(12, 8))

# Original Grayscale Image
plt.subplot(2, 3, 1)
plt.imshow(gray, cmap="gray")
plt.title("Original Grayscale Image")
plt.axis("off")

# Global Thresholding
plt.subplot(2, 3, 2)
plt.imshow(global_threshold, cmap="gray")
plt.title("Global Thresholding")
plt.axis("off")

# Adaptive Mean Thresholding
plt.subplot(2, 3, 3)
plt.imshow(adaptive_mean, cmap="gray")
plt.title("Adaptive Mean Thresholding")
plt.axis("off")

# Adaptive Gaussian Thresholding
plt.subplot(2, 3, 4)
plt.imshow(adaptive_gaussian, cmap="gray")
plt.title("Adaptive Gaussian Thresholding")
plt.axis("off")

# Otsu's Thresholding
plt.subplot(2, 3, 5)
plt.imshow(otsu_threshold, cmap="gray")
plt.title("Otsu's Thresholding")
plt.axis("off")

# Otsu Threshold Value
plt.subplot(2, 3, 6)
plt.text(
    0.5,
    0.5,
    f"Otsu Threshold Value:\n{otsu_threshold_value:.2f}",
    fontsize=14,
    ha="center",
    va="center"
)
plt.axis("off")

plt.tight_layout()
plt.show()
```

---

## Output
<img width="1291" height="799" alt="image" src="https://github.com/user-attachments/assets/240c346d-cdae-4411-9bec-3205a530c086" />



## Developed By

**Name:** Ligneshwar K

**Register No:** 212223230113

---

## Result

Thus, image segmentation was successfully performed using **Global Thresholding, Adaptive Mean Thresholding, Adaptive Gaussian Thresholding, and Otsu's Thresholding** techniques using Python and OpenCV.

The segmented images were successfully generated, displayed, and compared.

