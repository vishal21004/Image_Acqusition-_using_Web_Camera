### EX 02 : IMAGE AQUISITION USING WEB CAMERA
## Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.

i) Write the frame as JPG 

ii) Display the video 

iii) Display the video by resizing the window

iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Import OpenCV Package.
<br>

### Step 2:
Capture Video from Webcam. Use VideoCapture(0) to access the webcam and start capturing video.
<br>

### Step 3:
Read Video or Image. Utilize 'imread' to read a video frame or image from the webcam.
<br>

### Step 4:
Save Image to File. Employ 'imwrite' to save the captured image to a file.
<br>

### Step 5:
Display Video or Image. Use 'imshow' to display the captured video frame or image, and end Program with 'q'. Allow the program to be terminated by pressing the 'q' key.
<br>

## Program:
``` Python
### Developed By:VISHAL M.A
### Register No:212222230177

## i) Write the frame as JPG file

import cv2
videoCaptureObject = cv2.VideoCapture(0)
while (True):
    ret,frame = videoCaptureObject.read()
    cv2.imwrite("img.jpeg",frame)
    result = False
videoCaptureObject.release()
cv2.destroyAllWindows()



## ii) Display the video

import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imshow('myimage',frame)
    if cv2.waitKey(1) == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()


## iii) Display the video by resizing the window

import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5) 
    image[:height//2, :width//2] = smaller_frame
    image[height//2:, :width//2] = smaller_frame
    image[:height//2, width//2:] = smaller_frame 
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()



## iv) Rotate and display the video

import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5) 
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[:height//2, width//2:] = smaller_frame 
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()






```
## Output

### i) Write the frame as JPG image
![JPG IMAGE](https://github.com/vishal21004/Image_Acqusition-_using_Web_Camera/assets/119560110/d932f953-58ff-4182-a5b9-5bc2264ecd27)

</br>
</br>


### ii) Display the video
![JPG IMAGE](https://github.com/vishal21004/Image_Acqusition-_using_Web_Camera/assets/119560110/9689df01-64d2-4ade-b13b-02ba2247988c)


</br>
</br>


### iii) Display the video by resizing the window
![RESIZEIG](https://github.com/vishal21004/Image_Acqusition-_using_Web_Camera/assets/119560110/c16b7bfa-5e8d-4c92-893b-8aaa2db30a99)



</br>
</br>



### iv) Rotate and display the video
![ROT](https://github.com/vishal21004/Image_Acqusition-_using_Web_Camera/assets/119560110/149d52ec-d50d-43e8-9051-6e74c067e728)


</br>
</br>





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
