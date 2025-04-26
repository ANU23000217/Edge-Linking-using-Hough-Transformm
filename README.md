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


# Program

### Input image
```
import cv2
import matplotlib.pyplot as plt
image = cv2.imread('bird.jpg')  # Replace with your image path
# Display Input Image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Input Image')
plt.axis('off')
plt.show()
```

### Grayscale image
```
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Display Grayscale Image
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')
plt.show()
```

### Canny Edge detector output

```
edges = cv2.Canny(gray_image, 50, 150, apertureSize=3)
# Display Canny Edge Detection Output   
plt.imshow(edges, cmap='gray')
plt.title('Canny Edge Detector Output')
plt.axis('off')
plt.show()
```

### Display the result of Hough transform
```
import numpy as np
# Detect lines using the probabilistic Hough transform
lines = cv2.HoughLinesP(edges, rho=1, theta=np.pi/180, threshold=100, minLineLength=50, maxLineGap=10)

# Draw the lines on the original image
output_image = image.copy()

if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = line[0]
        cv2.line(output_image, (x1, y1), (x2, y2), (0, 255, 0), 2)
# Display Hough Transform Result
plt.imshow(cv2.cvtColor(output_image, cv2.COLOR_BGR2RGB))
plt.title('Hough Transform - Line Detection')
plt.axis('off')
plt.show()

```
## Output

### Input image and grayscale image

![image](https://github.com/user-attachments/assets/485742ca-3f52-42df-b09d-ea31bedbb2d9)   ![image](https://github.com/user-attachments/assets/a0d6e0a6-0197-4403-ac7d-28b3bd025dcd)


### Canny Edge detector output

![image](https://github.com/user-attachments/assets/6af5b8d7-39f5-425a-b2bc-043dd625351a)


### Display the result of Hough transform

![image](https://github.com/user-attachments/assets/52699bb4-c976-4265-b2f8-0b8ebbc6df10)


## Result:
 Thus the python program to detect the lines using Hough Transform was successfully completed.

