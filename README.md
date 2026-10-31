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

**Developed By:** DAKSHA C

**Register Number:** 212224230048

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('my_photo.jpg', cv2.IMREAD_GRAYSCALE)

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

img = cv2.imread('my_photo.jpg', cv2.IMREAD_COLOR)
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

<img width="337" height="485" alt="Screenshot 2026-10-31 105720" src="https://github.com/user-attachments/assets/4855c467-4633-47e0-8ce0-2d838fa71b3f" />


### Input Grayscale Image Range
<img width="697" height="493" alt="Screenshot 2026-10-31 105729" src="https://github.com/user-attachments/assets/72c46408-b61e-4550-a0fa-8f3f1f359ba4" />


### Input Grayscale Image Equalized Histogram
<img width="697" height="505" alt="Screenshot 2026-10-31 105733" src="https://github.com/user-attachments/assets/3a8651d9-64e9-4a30-ace4-ec8c0b699721" />



### Histogram of Grayscale Image and Color Image Channels

### Original Image
<img width="342" height="488" alt="Screenshot 2026-10-31 105738" src="https://github.com/user-attachments/assets/3fdb46be-f23d-474a-bab9-023ce0d707a9" />


### Equalized Image
<img width="367" height="497" alt="Screenshot 2026-10-31 105743" src="https://github.com/user-attachments/assets/06a2efeb-2e96-4a4a-ac0a-664230155275" />



### Equalized Histogram
<img width="707" height="486" alt="Screenshot 2026-10-31 105747" src="https://github.com/user-attachments/assets/15f2b5da-9b0b-42ef-ba11-7cd3ec0dc0ae" />


### Final Output of Original Image and Equalized 

<img width="1132" height="421" alt="Screenshot 2026-10-31 105753" src="https://github.com/user-attachments/assets/da1b27bb-a157-41f8-b79e-7bbe2fa26c51" />


### Final Output of Original Image and its Histogram Equalized


<img width="1143" height="332" alt="Screenshot 2026-10-31 105758" src="https://github.com/user-attachments/assets/da8644fd-b34a-429a-a093-b6ce96a1f33c" />

## Result

Thus, the histogram showing the frequency of pixel intensities ranging from 0 to 255 was obtained for the grayscale image and the color image using OpenCV.
