# Image-Acquisition-from-Web-Camera
## Aim
 
Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Import cv2 and capture the video using cv2.VideoCapture(0)

### Step 2:
Write the captured image using cv2.imwrite("NewPicture.jpg",frame)

### Step 3:
Write the captured image using cv2.imwrite("NewPicture.jpg",frame)

### Step 4:
Display the image until the loop gets over

### Step 5:
Rotate the image using cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)

## Program:
``` Python
### Developed By:Marella Dharanesh
### Register No:212222240062

## i) Write the frame as JPG file

import cv2
import numpy as np
cap=cv2.VideoCapture(0)
ret,frame=cap.read()
cv2.imwrite("pic_1.jpg",frame)

```



## ii) Display the video
```python
import cv2
import numpy as np

cap = cv2.VideoCapture(0)


while True:
    ret, frame = cap.read()

    cv2.imshow("NewPicture",frame)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

videoCaptureObject.release()
cv2.destroyAllWindows()




```



## iii) Display the video by resizing the window

```python
import cv2
import numpy as np
cap=cv2.VideoCapture(0)

while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    
    image=np.zeros(frame.shape, np.uint8)
    smaller_frame=cv2.resize(frame, (0,0), fx=0.5, fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    
    cv2.imshow('frame', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

```



## iv) Rotate and display the video

```python
import numpy as np
import cv2

cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    
    image = np.zeros(frame.shape, np.uint8)
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:,: width//2] = smaller_frame
    image[:height//2, width//2:] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:] = smaller_frame


    cv2.imshow('frame', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

```







## Output

### i) Write the frame as JPG image
![WhatsApp Image 2023-03-20 at 12 48 20](https://user-images.githubusercontent.com/118707669/226645662-dce32bdf-f70c-4ba6-a427-c41bfcc84427.jpg)


### ii) Display the video
![WhatsApp Image 2023-03-20 at 12 16 04](https://user-images.githubusercontent.com/118707669/226645754-4afca1bd-ae3e-4385-8c04-814d52a77ca8.jpg)



### iii) Display the video by resizing the window


![Screenshot from 2023-03-20 11-57-53-3](https://user-images.githubusercontent.com/118707669/226647046-1e36cea8-e181-4484-8e77-7f3a358fdc98.png)

### iv) Rotate and display the video




![WhatsApp Image 2023-03-20 at 12 16 04](https://user-images.githubusercontent.com/118707669/226645915-85c64524-b26b-463e-9294-c75ce37e69c7.jpg)




## Result:
Thus the image is accessed from webcamera and displayed using openCV.
