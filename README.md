# EXP-3-Record-Histogram-processing
## Aim
To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

Read and display a grayscale image

Plot histogram of the grayscale image

Apply histogram equalization on grayscale image

Read and display a color image

Plot histogram of B, G, R channels

Convert image to HSV color space

Apply histogram equalization on the Value (V) channel

Convert the enhanced image back to BGR format

Display original and enhanced images with histograms

## Software Used
Anaconda – Python 3.7

Jupyter Notebook / VS Code

OpenCV (cv2)

NumPy

Matplotlib

## Algorithm
Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

Step 2:
Read the image parrot.jpg in grayscale format.

Step 3:
Display the grayscale image and plot its histogram.

Step 4:
Apply histogram equalization using cv2.equalizeHist() to enhance contrast.

Step 5:
Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

Step 6:
Read the same image in color format.

Step 7:
Split the image into B, G, R channels and plot their histograms.

Step 8:
Convert the image from BGR to HSV color space.

Step 9:
Apply histogram equalization on the V (Value) channel.

Step 10:
Merge the channels and convert the image back to BGR format.

Step 11:
Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.

## Program
```

1. Import the required libraries and read the grayscale image.
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('CEO.png', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original GrayScale Image')
plt.show()
2. Plot the histogram of the grayscale image.
plt.hist(img.ravel(), 256, range=[0,256])
plt.title('Original GrayScale Image Histogram')
plt.show()
3. Apply histogram equalization.
img_eq = cv2.equalizeHist(img)
4. Display the histogram of the equalized image.
plt.hist(img_eq.ravel(), 256, range=[0,256])
plt.title('Equalized Histogram')
plt.show()
5. Display the equalized grayscale image.
plt.imshow(img_eq, cmap='gray')
plt.title('Equalized Image')
plt.show()
6. Read the image in color mode and convert to HSV.
img = cv2.imread('gta.jpg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
7. Apply histogram equalization to the V channel.
img_hsv[:, :, 2] = cv2.equalizeHist(img_hsv[:, :, 2])
8. Convert the enhanced HSV image back to BGR.
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
9. Display the original and equalized color images.
plt.subplot(121)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')

plt.subplot(122)
plt.imshow(img_eq[:, ::-1])
plt.title('Equalized Image')

plt.show()
10. Display the original and equalized images along with their histograms.
plt.figure(figsize=[12,10])

plt.subplot(221)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')

plt.subplot(222)
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')

plt.subplot(223)
plt.hist(img.ravel(), 256, range=[0,256])
plt.title('Original Histogram')

plt.subplot(224)
plt.hist(img_eq.ravel(), 256, range=[0,256])
plt.title('Histogram Equalized')

plt.show()
```
## output
<img width="616" height="557" alt="image" src="https://github.com/user-attachments/assets/4eb2eda6-2f2b-48d2-b08e-8b57de5b6bfb" />

<img width="822" height="533" alt="image" src="https://github.com/user-attachments/assets/4dc48d93-b86a-46fc-8863-9fa06296b1f7" />

<img width="410" height="336" alt="image" src="https://github.com/user-attachments/assets/ae4cf895-62e5-4bf9-a422-c2df58e1adbb" />

<img width="435" height="318" alt="image" src="https://github.com/user-attachments/assets/f216bf3c-3c1a-4078-bd54-2dae34b41059" />

<img width="787" height="307" alt="image" src="https://github.com/user-attachments/assets/a33d41a0-c773-415d-9e44-effd5eb0cd3c" />

