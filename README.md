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
Import OpenCV Package.

### Step 2:
Capture Video from Webcam. Use VideoCapture(0) to access the webcam and start capturing video.

### Step 3:
Read Video or Image. Utilize 'imread' to read a video frame or image from the webcam.

### Step 4:
Save Image to File. Employ 'imwrite' to save the captured image to a file.

### Step 5:
Display Video or Image. Use 'imshow' to display the captured video frame or image.

### Step 6:
End Program with 'q'. Allow the program to be terminated by pressing the 'q' key.




## Program:
``` Python
### Developed By: MAHESH RAJ PUROHIT J
### Register No:212222240058
'''
## i) Write the frame as JPG file
```Python
import cv2
viedoCaptureObject=cv2.VideoCapture(0)
while(True):
    ret,frame=viedoCaptureObject.read()
    cv2.imwrite("mahesh.jpg",frame)
    result=False
viedoCaptureObject.release()
cv2.destroyAllWindows()
```
## ii) Display the video
```Python
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('mahesh',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## iii) Display the video by resizing the window
```Python
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
    cv2.imshow('212222240058-mahesh',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## iv) Rotate and display the video
```Python
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
    cv2.imshow('212222240058-mahesh',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```



## Output

### i) Write the frame as JPG image
![Screenshot 2024-02-25 011543](https://github.com/maheshrajpurohit18/Image_Acqusition-_using_Web_Camera/assets/118749665/47b46131-e90d-4092-bcc3-e58abb59045f)



### ii) Display the video
![Screenshot 2024-02-25 010843](https://github.com/maheshrajpurohit18/Image_Acqusition-_using_Web_Camera/assets/118749665/29af1e6d-3a7b-44e7-9c15-31b2c7397461)



### iii) Display the video by resizing the window

![Screenshot 2024-02-25 011210](https://github.com/maheshrajpurohit18/Image_Acqusition-_using_Web_Camera/assets/118749665/fe917cb7-1369-44f2-b233-b46d62c598f2)



### iv) Rotate and display the video
![Screenshot 2024-02-25 011339](https://github.com/maheshrajpurohit18/Image_Acqusition-_using_Web_Camera/assets/118749665/26e39feb-d4ea-44c0-9248-61761f02f6f0)






## Result:
Thus the image is accessed from webcamera and displayed using openCV.
