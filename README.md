# Histogram-Equalization-Using-OpenCV-

### NAME : PRIYA B
### REG.NO : 212224230208

## Aim:
To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:


1.Read and display a grayscale image
 
2.Plot histogram of the grayscale image
 
3.Apply histogram equalization on grayscale image

4.Read and display a color image

5.Plot histogram of B, G, R channels

6.Convert image to HSV color space

7.Apply histogram equalization on the Value (V) channel

8.Convert the enhanced image back to BGR format

9.Display original and enhanced images with histograms

## Software Used:

Anaconda – Python 3.7

Jupyter Notebook / VS Code

OpenCV (cv2)

NumPy

Matplotlib

## Algorithm:

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

## Program:
```
## Import Python necessary libraries
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('pic2.jpeg', cv2.IMREAD_GRAYSCALE)

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
img = cv2.imread('pic2.jpeg', cv2.IMREAD_COLOR)
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
## Output:
<img width="363" height="432" alt="image" src="https://github.com/user-attachments/assets/09918e50-d009-4427-8e9c-677f454ea9c6" />

<img width="606" height="426" alt="image" src="https://github.com/user-attachments/assets/fb619d41-d75d-48c2-b63e-3cdb9dc5e211" />

<img width="597" height="431" alt="image" src="https://github.com/user-attachments/assets/9d0c8d82-eede-4ca6-955e-b2f0a4ca7424" />

<img width="375" height="437" alt="image" src="https://github.com/user-attachments/assets/078afbbb-9fc5-4550-b6e4-2650d4a7720c" />

<img width="395" height="432" alt="image" src="https://github.com/user-attachments/assets/fb8ede32-75e4-4c5b-b85e-a026e97a6805" />

<img width="602" height="422" alt="image" src="https://github.com/user-attachments/assets/b5913220-a0c6-4964-a8aa-49904c23f904" />

<img width="877" height="300" alt="image" src="https://github.com/user-attachments/assets/e43df9ec-216e-41e7-8c47-553720f8b524" />

<img width="887" height="252" alt="image" src="https://github.com/user-attachments/assets/0d01fb05-e3bb-44b0-ab36-b7da0a23e2ba" />

## Result:

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.






