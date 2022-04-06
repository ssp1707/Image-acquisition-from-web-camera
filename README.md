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
Use VideoCapture(0) to access web camera.

### Step 2:
Use imread to read the video or image.

### Step 3:
Use imwrite to save the image.

### Step 4:
Use imshow to save the image.

### Step 5:
End the program and close the output video windows by pressing 'q'. 

## Program:

### Developed By: S. Sanjna Priya
### Register No:212220230043

## i) Write the frame as JPG file
```
import cv2
videoCaptureObject=cv2.VideoCapture(0)
while(True):
  ret,frame=videoCaptureObject.read()
  cv2.imwrite("New Picture.jpg",frame)
  result=False
videoCaptureObject.release()
cv2.destroyAllWindows()
```

## ii) Display the video
```
import cv2
import numpy as np
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('frame',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cap.destroyAllWindows()
```

## iii) Display the video by resizing the window
```
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
```
import cv2
import numpy as np
cap=cv2.VideoCapture(0)

while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    
    image=np.zeros(frame.shape, np.uint8)
    smaller_frame=cv2.resize(frame, (0,0), fx=0.5, fy=0.5)
    image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:]=smaller_frame
    
    cv2.imshow('frame', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```


## Output

### i) Write the frame as JPG image


![EXPT 2 IMG](https://user-images.githubusercontent.com/75234965/161987987-ffe672e4-b645-4031-b87d-2399679da0a4.PNG)


### ii) Display the video

![EXPT 2 VID0](https://user-images.githubusercontent.com/75234965/161986735-88df77df-1105-47d2-8096-585ae4d7f3bb.PNG)

### iii) Display the video by resizing the window

![EXPT 2 VID1](https://user-images.githubusercontent.com/75234965/161986957-2fe6b31a-5c87-490f-b2e4-b49d0539a897.PNG)


### iv) Rotate and display the video


![EXPT 2 VID2](https://user-images.githubusercontent.com/75234965/161986782-55d634b9-9500-4714-815c-72feffdf297d.PNG)



## Result:
Thus the image is accessed from webcamera and displayed using openCV.
