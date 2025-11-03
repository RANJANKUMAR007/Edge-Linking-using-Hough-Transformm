# Edge-Linking-using-Hough-Transformm
# Developed By:RANJAN KUMAR G
# Reg no:212223240138
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
# Program:
Developed By: Daniel C

Reg no:212223240023
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('sea.png') 
if image is None:
    raise ValueError("Image not found. Please upload it using 'files.upload()'.")

gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

edges = cv2.Canny(gray_image, 50, 150)

lines = cv2.HoughLinesP(
    edges,               
    rho=1,              
    theta=np.pi / 180,   
    threshold=100,       
    minLineLength=50,    
    maxLineGap=10       
)

result = image.copy()
if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = line[0]
        cv2.line(result, (x1, y1), (x2, y2), (0, 255, 0), 2)  
else:
    print("No lines detected!")

plt.figure(figsize=(15, 5))

plt.subplot(1, 4, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Original Image")
plt.axis("off")

plt.subplot(1, 4, 2)
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")

plt.subplot(1, 4, 3)
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis("off")

plt.subplot(1, 4, 4)
plt.imshow(cv2.cvtColor(result, cv2.COLOR_BGR2RGB))
plt.title("Result: Hough Line Transform")
plt.axis("off")

plt.show()
```
## output
## input image:
<img width="622" height="352" alt="image" src="https://github.com/user-attachments/assets/d7cd92f0-ac5e-4def-89ef-c5c0fb853fbb" />


## gray scale:
<img width="618" height="356" alt="image" src="https://github.com/user-attachments/assets/755db523-d532-4f60-89e5-60f511ef8386" />
## candy edge:
<img width="622" height="350" alt="image" src="https://github.com/user-attachments/assets/fe1b5b9a-f9d8-458d-94a2-c0514e7bc3ee" />

### Display the result of Hough transform
<img width="624" height="352" alt="image" src="https://github.com/user-attachments/assets/9a0aa7d3-6598-4cc4-b68b-91794f0bf9d9" />

# Result:
Thus, the image has been successfully converted.


