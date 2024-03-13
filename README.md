# Image_Acqusition-_using_Web_Camera
## Aim
 

To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Use cv2.VideoCapture(0) to access web camera
### Step 2:
Use cv2.imread to read the video or image
### Step 3:
Use cv2.imwrite to save the image
### Step 4:
Use cv2.imshow to show the video
### Step 5:
End the program and close the output video window by pressing 'q'.
## Program:
``` Python
### Developed By:VISHAL M.A
### Register No: 212222230177
```
## i) Write the frame as JPG file
```python
import cv2
videoCaptureObject=cv2.VideoCapture(0)
while(True):
    cap,frame=videoCaptureObject.read()
    cv2.imwrite("Jayadeep.jpg",frame)
    result=False
videoCaptureObject.release()
cv2.destroyAllWindows()
```



## ii) Display the video
```python
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('video capture',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

```




## iii) Display the video by resizing the window
```python
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('Video Capture',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

```




## iv) Rotate and display the video
```python
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('Video Capture',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```









## Output

### i) Write the frame as JPG image
![frame as jpg](https://github.com/vishal21004/Image_Acqusition-_using_Web_Camera/assets/119560110/93479bca-5323-4a84-9a45-20242305ad15)




### ii) Display the video

![display vdo](https://github.com/vishal21004/Image_Acqusition-_using_Web_Camera/assets/119560110/2bd3c851-e3ca-453e-bb40-e7ff275e6798)




### iii) Display the video by resizing the window

![resize](https://github.com/vishal21004/Image_Acqusition-_using_Web_Camera/assets/119560110/88b1a165-91ed-4c08-8c65-29026d0245eb)



### iv) Rotate and display the video
![rotate display](https://github.com/vishal21004/Image_Acqusition-_using_Web_Camera/assets/119560110/53d49003-921f-44eb-b4b4-67cbe4621f64)






## Result:
Thus the image is accessed from webcamera and displayed using openCV.
