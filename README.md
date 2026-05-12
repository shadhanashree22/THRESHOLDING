# THRESHOLDING

## Aim

To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using Python and OpenCV.

---

## Learning Objective

* Understand image segmentation techniques
* Learn Global Thresholding
* Learn Adaptive Thresholding
* Understand Otsu’s Thresholding Method
* Visualize segmented images using OpenCV

---

## Software Required

1. Anaconda – Python 3.x
2. Jupyter Notebook / VS Code
3. OpenCV (`cv2`)
4. NumPy
5. Matplotlib

---

# Algorithm

### Step 1:
Import the required libraries such as OpenCV, NumPy, and Matplotlib.

---

### Step 2:
Read the input image using OpenCV and convert the image into grayscale.

---

### Step 3:
Apply Global Thresholding using a fixed threshold value to segment the image.

---

### Step 4:
Apply Adaptive Thresholding using the Gaussian method to segment different regions of the image.

---

### Step 5:
Apply Otsu’s Thresholding method to automatically determine the optimal threshold value.

---

### Step 6:
Display the original image and all thresholded output images using Matplotlib.

---

# Name: S V SHADHANASHREE

# Register No: 212223230202

---

# Program

```python
# Import required libraries
import cv2
import numpy as np
import matplotlib.pyplot as plt


# Step 1: Read the image using OpenCV
image = cv2.imread('Qn8_thresholding.tif')


# Step 2: Convert the image into grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)


# Step 3: Apply Global Thresholding
# Threshold value = 127
_, global_thresholded = cv2.threshold(
    gray_image,
    127,
    255,
    cv2.THRESH_BINARY
)


# Step 4: Apply Adaptive Thresholding
# Gaussian adaptive thresholding
adaptive_thresholded = cv2.adaptiveThreshold(
    gray_image,
    255,
    cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
    cv2.THRESH_BINARY,
    11,
    2
)


# Step 5: Apply Otsu's Thresholding
# Automatically calculates optimal threshold value
_, otsu_thresholded = cv2.threshold(
    gray_image,
    0,
    255,
    cv2.THRESH_BINARY + cv2.THRESH_OTSU
)


# Step 6: Display Original Image
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Original Image")
plt.axis('off')


# Display Global Thresholding Result
plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')


# Display Adaptive Thresholding Result
plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')


# Display Otsu's Thresholding Result
plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')


# Adjust layout and display images
plt.tight_layout()
plt.show()
```

---

# Output

### Original Image

* Displays the original input image.
<img width="209" height="208" alt="image" src="https://github.com/user-attachments/assets/38c9a149-d94b-4e22-9525-c6f78f0afcc1" />

---

### Global Thresholding

* Displays the segmented image using a fixed threshold value.

  <img width="545" height="470" alt="image" src="https://github.com/user-attachments/assets/72841ecf-1e36-45b3-8e87-b89f8027b77e" />


---

### Adaptive Thresholding

* Displays the segmented image using local adaptive threshold values.
<img width="545" height="470" alt="image" src="https://github.com/user-attachments/assets/e43a9d9f-e0c8-4ed6-8be5-98cb50e75823" />

---

### Otsu's Thresholding

* Displays the segmented image using automatically calculated threshold values.

<img width="545" height="470" alt="image" src="https://github.com/user-attachments/assets/93ee14a3-7552-43b2-9b38-6998a03c2a62" />

---

# Result

Thus, the images are successfully segmented using Global Thresholding, Adaptive Thresholding, and Otsu’s Thresholding using Python and OpenCV.
