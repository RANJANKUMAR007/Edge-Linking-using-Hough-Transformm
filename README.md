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
## Output

### Original Image:
<img width="338" height="277" alt="image" src="https://github.com/user-attachments/assets/87911884-362d-4935-949d-d55eca0c6563" />

## gray scale:
<img width="367" height="286" alt="image" src="https://github.com/user-attachments/assets/301c36ed-0853-4223-ab58-d1a66687946d" />


### Canny Edge detector output
<img width="400" height="302" alt="image" src="https://github.com/user-attachments/assets/bd55c000-5f0e-44fe-919c-0c114b1d98c1" />

### Display the result of Hough transform
<img width="368" height="292" alt="image" src="https://github.com/user-attachments/assets/dfc2e695-8b84-453d-b615-1db8d571153e" />

# Result:
Thus, the image has been successfully converted.


