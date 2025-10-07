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

## PROGRAM:
``````
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('me.jpg') 
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
plt.title("Input Image")
plt.axis('off')
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
for line in lines:
    x1, y1, x2, y2 = line[0]
cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Result of Hough Transform")
plt.axis('off')
````````
## Output


<img width="438" height="342" alt="image" src="https://github.com/user-attachments/assets/1c038286-d7dc-436f-90bd-17fbfa0eee98" />
<img width="452" height="326" alt="image" src="https://github.com/user-attachments/assets/e91c75d2-17d9-4333-9616-f1cb7b37cae8" />
<img width="492" height="329" alt="image" src="https://github.com/user-attachments/assets/1a74102d-a27c-4f01-a7af-28ead98531b6" />
<img width="439" height="313" alt="image" src="https://github.com/user-attachments/assets/d8032969-501e-42de-bf7f-aa9511263e10" />


