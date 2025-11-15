# EXP NO. 7: Edge-Linking-using-Hough-Transformm 
# NAME : Markandeyan Gokul
# REG NO : 212224240086
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import all the necessary modules for the program.
### Step2:

Load a image using imread() from cv2 module.
### Step3:

Convert the image to grayscale.
### Step4:

Using Canny operator from cv2,detect the edges of the image.
### Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

## Program:
## Input image and grayscale image:
```
import numpy as np
import cv2
import matplotlib.pyplot as plt

gray = cv2.imread('image02.png', cv2.IMREAD_GRAYSCALE)
img_color = cv2.imread('image02.png', cv2.IMREAD_COLOR)
img_c = cv2.cvtColor(img_color, cv2.COLOR_BGR2RGB)
gray_rgb = cv2.cvtColor(gray, cv2.COLOR_GRAY2RGB)

gray = cv2.GaussianBlur(gray, (3, 3), 0)

plt.figure(figsize=(13, 13))
plt.subplot(1, 2, 1)
plt.imshow(img_c)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1, 2, 2)
plt.imshow(gray_rgb, cmap='gray')
plt.title("Gray Image")
plt.axis("off")
plt.show()
```
## Canny Edge detector :
```
canny = cv2.Canny(gray, 120, 150)

plt.imshow(canny, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()
```
## Display the result of Hough transform:
```
lines = cv2.HoughLinesP(canny, 1, np.pi/180, threshold=80, minLineLength=50, maxLineGap=250)

for line in lines:
    x1, y1, x2, y2 = line[0]
    cv2.line(img_c, (x1, y1), (x2, y2), (255, 0, 0), 3)

plt.imshow(img_c)
plt.title("Result Image")
plt.axis("off")
plt.show()
```
## Output

### Input image and grayscale image
<img width="953" height="623" alt="Screenshot 2025-10-10 201218" src="https://github.com/user-attachments/assets/9a4d6fe0-378d-45e9-b286-e839eb961549" />

### Canny Edge detector output
<img width="375" height="522" alt="Screenshot 2025-10-10 201330" src="https://github.com/user-attachments/assets/f81d6656-37ad-48e3-befb-28ced8647821" />

### Display the result of Hough transform
<img width="379" height="521" alt="Screenshot 2025-10-10 201352" src="https://github.com/user-attachments/assets/de0cd149-6dde-4f30-8bb4-4fc16096233b" />


## Result:
Thus, the image has been successfully converted.
