# Edge-Linking-using-Hough-Transform
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
## Step 1:
Import the necessary packages.

## Step 2:
Read the image.

## Step 3:
Convert the image to greyscale.

## Step 4:
Using Canny operator from cv2,detect the edges of the image.

## Step 5:
Detect line co-ordinates for every points in the images. Draw the lines on the found co-ordinates and display the image.

## Program:
```Python
Developed by : A.sasidharan
Registration Number : 212221240049
# Read image and convert it to grayscale image
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1=cv2.imread('n.jpg',0)
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
![dio1](https://user-images.githubusercontent.com/94154712/173248984-a75ef433-72b9-4c88-98d4-52f8f271ab5e.png)

<br>
<br>
<br>

### Canny Edge detector output
![dip2](https://user-images.githubusercontent.com/94154712/173249015-f32dbaa4-edeb-4fdb-932e-0e64dc26935c.png)

<br>
<br>
<br>


### Display the result of Hough transform
![dip3](https://user-images.githubusercontent.com/94154712/173249027-501f6da3-a266-4094-9cda-721856a0080f.png)

<br>
<br>
<br>



## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
