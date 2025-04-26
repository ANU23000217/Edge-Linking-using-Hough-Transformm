![Screenshot 2025-04-26 103633](https://github.com/user-attachments/assets/aa32e4c6-10ea-4ee2-b0cc-76ab45d69c52)# Edge-Linking-using-Hough-Transformm
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

![Screenshot 2025-04-26 103633](https://github.com/user-attachments/assets/a3b9ebc8-8b41-4d46-83a4-a35101549214)

![Screenshot 2025-04-26 103642](https://github.com/user-attachments/assets/3dc7c0a6-3189-4aca-8beb-f39b5d3f9129)

### Canny Edge detector output

![Screenshot 2025-04-26 103658](https://github.com/user-attachments/assets/d1ce2f8a-27e3-4f46-b96c-904da8d90e3d)


### Display the result of Hough transform

![Screenshot 2025-04-26 103716](https://github.com/user-attachments/assets/b0db56b4-066d-4670-b9bb-9ae20fe96f9a)


## Result:
 Thus the python program to detect the lines using Hough Transform was successfully completed.

