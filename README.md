# EXP-2-Record-Image Acquisition using Web Camera
# Name: B Charan Reddy
# Reg No: 212224240026
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
Use cv2.VideoCapture(0) to access web camera.
<br>

### Step 2:
Use cv2.imread to read the video or image.
<br>

### Step 3:
Use cv2.imwrite to save the image.
<br>

### Step 4:
Use cv2.imshow to show the video.

<br>

### Step 5:
End the program and close the output video window by pressing 'q'.
<br>

## Program:

## i) Write the frame as JPG file
```
import cv2
viedoCaptureObject=cv2.VideoCapture(0)

ret,frame=viedoCaptureObject.read()
cv2.imwrite("webcam_img.jpg",frame)

viedoCaptureObject.release()
cv2.destroyAllWindows()
```

## ii) Display the video
```
import numpy as np
import cv2

cap = cv2.VideoCapture(0)
ret, frame = cap.read()

cv2.imshow('captured_frame', frame)

cv2.waitKey(10000)


cap.release()
cv2.destroyAllWindows()
```
## iii) Display the video by resizing the window
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)

ret,frame=cap.read()
width=int(cap.get(3))
height=int(cap.get(4))
image=np.zeros(frame.shape,np.uint8)
smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
image[:height//2, :width//2]=smaller_frame
image[height//2:, :width//2]=smaller_frame
image[:height//2, width//2:]=smaller_frame
image[height//2:, width//2:]=smaller_frame

cv2.imshow('212224240026_Charan Reddy',image)

cv2.waitKey(5000)  

image_dict = {'captured_image1': image}
cv2.imwrite('captured_image1.jpg', image)

cap.release()
cv2.destroyAllWindows()
```
## iv) Rotate and display the video
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)

ret,frame=cap.read()
width=int(cap.get(3))
height=int(cap.get(4))
image=np.zeros(frame.shape,np.uint8)
smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
image[height//2:, :width//2]=smaller_frame
image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
image[height//2:, width//2:]=smaller_frame

cv2.imshow('212224240026',image)

cv2.waitKey(5000) 

image_dict = {'captured_image2': image}
cv2.imwrite('captured_image2.jpg', image)

cap.release()
cv2.destroyAllWindows()
```
## Output

### i) Write the frame as JPG image
<img width="1481" height="833" alt="image" src="https://github.com/user-attachments/assets/c45c56e1-4933-44eb-8075-db54e6521c25" />

</br>
</br>


### ii) Display the video
<img width="1481" height="833" alt="image" src="https://github.com/user-attachments/assets/312d08c0-1973-4b4b-b701-fff60d9e314c" />
</br>
</br>


### iii) Display the video by resizing the window
<img width="805" height="608" alt="image" src="https://github.com/user-attachments/assets/41c644e1-40c3-41c4-a86e-27ced9bfd590" />
</br>
</br>



### iv) Rotate and display the video
<img width="800" height="610" alt="image" src="https://github.com/user-attachments/assets/9293a1e2-84dd-481b-a9f0-ad11e9f53dca" />
</br>
</br>





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
