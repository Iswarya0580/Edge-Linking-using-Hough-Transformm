# Edge-Linking-using-Hough-Transformm
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

### Developed by : Iswarya P
### Register no : 212223230082
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Input Image')
plt.axis('off')
image = cv2.imread('tower.jpeg')
```
## Output
![Screenshot 2024-10-03 114730](https://github.com/user-attachments/assets/1b16771f-29db-4b22-ae37-6bcb8a50def0)

## Grayscale Image:
```
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')
```
## Output
![Screenshot 2024-10-03 114738](https://github.com/user-attachments/assets/98e1b1d3-b98b-4020-9ceb-d4b8432c2abf)

## Canny Edge Detector:
```
edges = cv2.Canny(gray_image, 50, 150, apertureSize=3)
plt.imshow(edges, cmap='gray')
plt.title('Canny Edge Detector Output')
plt.axis('off')
```
## Output
![Screenshot 2024-10-03 114744](https://github.com/user-attachments/assets/4836c38f-238f-4b31-8896-90fb696394d9)

## Detect lines using the probabilistic Hough transform
```
lines = cv2.HoughLinesP(edges, rho=1, theta=np.pi/180, threshold=100, minLineLength=50, maxLineGap=10)
output_image = image.copy()

if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = line[0]
        cv2.line(output_image, (x1, y1), (x2, y2), (0, 0, 255), 2)
plt.imshow(cv2.cvtColor(output_image, cv2.COLOR_BGR2RGB))
plt.title('Hough Transform - Line Detection')
plt.axis('off')
```
## Output
![Screenshot 2024-10-03 114752](https://github.com/user-attachments/assets/bdf43caf-cd29-4a8a-af8e-e9ea5707855a)

# Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform.
