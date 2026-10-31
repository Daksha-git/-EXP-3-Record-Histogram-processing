# -EXP-3-Record-Histogram-processing

# Histogram-of-an-images

## Aim

To obtain a histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255. Also, write a Python program using OpenCV to perform histogram equalization.

## Software Required

- Anaconda - Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

### Step 1
Read the grayscale and color images using the `cv2.imread()` function.

### Step 2
Display the grayscale and color images using the `imshow()` function.

### Step 3
Use the `cv2.calcHist()` function to calculate the frequency of pixel intensities in the grayscale image.

### Step 4
Use the `cv2.calcHist()` function to calculate the histograms of the Blue, Green, and Red channels of the color image.

### Step 5
Plot and display the histograms of the grayscale image and color image.

## Program

**Developed By:** SHRIVARSHAN P G

**Register Number:** 212225240146

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('sv.jpeg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()

img_eq = cv2.equalizeHist(img)

plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')

plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()

img = cv2.imread('sv.jpeg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()

plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()

plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()

plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```

## Output

### Input Grayscale Image

<img width="738" height="440" alt="image" src="https://github.com/user-attachments/assets/ed226899-4207-4a67-8486-ab02c146881f" />

### Input Grayscale Image Range
<img width="877" height="536" alt="image" src="https://github.com/user-attachments/assets/c665c472-3488-40e3-a800-15a724be41a7" />

### Input Grayscale Image Equalized Histogram
<img width="846" height="535" alt="image" src="https://github.com/user-attachments/assets/20f0460e-f2ca-432a-afa8-0d7da62750c3" />


### Histogram of Grayscale Image and Color Image Channels

### Original Image

<img width="775" height="467" alt="image" src="https://github.com/user-attachments/assets/c74ea9af-b263-420d-8e39-ae3a06dc1f9a" />

### Equalized Image

<img width="740" height="441" alt="image" src="https://github.com/user-attachments/assets/cff11798-aa29-4a1f-adb2-ecd245f9d202" />

### Equalized Histogram
<img width="845" height="548" alt="image" src="https://github.com/user-attachments/assets/c37fbf0f-a3b0-4c80-b36c-ccba7f02dd8d" />

### Final Output of Original Image and Equalized 
<img width="1397" height="390" alt="image" src="https://github.com/user-attachments/assets/a9d8ba05-ec07-4198-94cf-752ab29c1657" />


### Final Output of Original Image and its Histogram Equalized
<img width="1428" height="437" alt="image" src="https://github.com/user-attachments/assets/46d7ed22-d3f6-4f4e-bfc8-8ec26c4ef899" />


## Result

Thus, the histogram showing the frequency of pixel intensities ranging from 0 to 255 was obtained for the grayscale image and the color image using OpenCV.
