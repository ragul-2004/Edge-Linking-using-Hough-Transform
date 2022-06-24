# Edge-Linking-using-Hough-Transform
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
<br>
Import the necessary packages.

### Step2:
<br>Read the image

### Step3:
<br>
Convert the image to greyscale.

### Step4:
<br>
Using Canny operator from cv2,detect the edges of the image.

### Step5:
<br>
Detect line co-ordinates for every points in the images. Draw the lines on the found co-ordinates and display the image.


## Program:
```Python

# Read image and convert it to grayscale image

import cv2
import numpy as np
import matplotlib.pyplot as plt
image1=cv2.imread('1.jpg',0)
img= cv2.GaussianBlur(image1,(3,3),0)
plt.imshow(img)



# Find the edges in the image using canny detector and display
edges1 = cv2.Canny(img,100,200)
plt.imshow(edges1,cmap = 'gray')
plt.title('Edge Image'), plt.xticks([]), plt.yticks([])
plt.show()


# Detect points that form a line using HoughLinesP
lines=cv2.HoughLinesP(edges1,1,np.pi/180, threshold=80, minLineLength=50,maxLineGap=250)


# Draw lines on the image
for line in lines:
    x1, y1, x2, y2 = line [0] 
    cv2.line(edges1,(x1, y1),(x2, y2),(255, 0, 0),3)


# Display the result
plt.imshow(edges1)



```
## Output

### Input image and grayscale image
![1](https://user-images.githubusercontent.com/94367917/175531738-82a12a18-84d7-4ee4-968f-0071a4c7983e.jpg)


### Canny Edge detector output


![2](https://user-images.githubusercontent.com/94367917/175531759-e19a8ba5-14b6-4562-b17b-88ef7b703020.jpg)

### Display the result of Hough transform

![3](https://user-images.githubusercontent.com/94367917/175531784-824bf2ae-50f1-42db-b154-de7f5c153b3d.jpg)


## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
