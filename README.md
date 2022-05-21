# Edge-Linking-using-Hough-Transform
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import the required modules.



### Step2:
Import the image to operate on.



### Step3:
Convert the imported image from BGR to GRAYSCALE.



### Step4:
Find the edges using canny edge detector and display the image.



### Step5:
Detect the points that form a line using hough transform.


### Step6:
Draw the lines on the image


### Step7:
Display the output.


### Step8:
End the program.



## Program:
```Python!
Developed By:P.Siva Naga Nithin
Registeration Number: 212221240037
# Read image and convert it to grayscale image

import cv2
import matplotlib.pyplot as plt
import numpy as np
image = cv2.imread("mg.jpg")
smoothImage = cv2.GaussianBlur(image,(3,3),0)
plt.imshow(smoothImage)
grayImage = cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)
cv2.imshow("Original Image",image)
cv2.imshow("Gray Image",grayImage)




# Find the edges in the image using canny detector and display

cannyEdges = cv2.Canny(smoothImage,120,200)
plt.imshow(cannyEdges,cmap='gray')
plt.title('Edge Image')
plt.xticks([])
plt.yticks([])
plt.show()


# Detect points that form a line using HoughLinesP

lines = cv2.HoughLinesP(cannyEdges,1,np.pi/180,threshold=80,minLineLength = 50,maxLineGap = 250)



# Draw lines on the image

for line in lines:
    x1, y1, x2, y2 = line [0]
    cv2.line(smoothImage,(x1, y1),(x2, y2),(255, 0, 0),3)



# Display the result
plt.title("Hough Transform")
plt.imshow(cannyEdges)
plt.show()




```

## Output

### Input image and grayscale image
![ex82](https://user-images.githubusercontent.com/94154780/169656676-169901b5-4b7e-4e73-ae09-717f1921e492.png)

### Canny Edge detector output
![ex8](https://user-images.githubusercontent.com/94154780/169656690-bd8406ea-9252-4f65-beaf-a259a33d578d.png)


### Display the result of Hough transform
![ex81](https://user-images.githubusercontent.com/94154780/169656696-2b0baaa7-926a-4b23-b0e2-5c55422e0be0.png)



## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
