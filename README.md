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
image = cv2.imread("road.jpeg")
smoothImage = cv2.GaussianBlur(image,(3,3),0)
plt.imshow(smoothImage)
grayImage = cv2.cvtColor(smoothImage,cv2.COLOR_BGR2GRAY)
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
    cv2.line(image,(x1, y1),(x2, y2),(255, 0, 0),3)



# Display the result
plt.title("Hough Transform")
plt.imshow(image)
plt.show()








```

## Output

### Input image and grayscale ima!
![ex8](https://user-images.githubusercontent.com/94154780/174640769-e2ef3c78-7154-490f-87c1-917cdc110caa.png)
![ex8 1](https://user-images.githubusercontent.com/94154780/174640798-e756d01f-f49c-42d2-8c0f-9093f82620ef.png)



### Canny Edge detector output
![ex8 2](https://user-images.githubusercontent.com/94154780/174640516-a60dedc6-35f3-4e83-891d-9a830ca80bab.png)




### Display the result of Hough transform
![ex8 3](https://user-images.githubusercontent.com/94154780/174640613-e07f8941-f1df-48aa-93b9-41c4bea97d49.png)





## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
