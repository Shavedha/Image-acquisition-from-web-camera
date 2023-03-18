# Image-Acquisition-from-Web-Camera
## Aim
 
Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
```
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video
```

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Import cv2 and capture the video using cv2.VideoCapture(0)

### Step 2:
Write the captured image using cv2.imwrite("myimage.jpg",frame)

### Step 3:
Resize the image using cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)

### Step 4:
Display the image until the loop gets over

### Step 5:
Rotate the image using cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)

## Program:
``` 
Python
Developed By: Y SHAVEDHA
Register No: 212221230095
```

## i) Write the frame as JPG file
```
import cv2
vco = cv2.VideoCapture(0)
while(True):
    ret,frame = vco.read()
    cv2.imwrite('myimage.jpg',frame)
    img1=cv2.resize(frame,None,fx=0.5,fy=0.5)
    cv2.imshow('resisedimage',img1)
    if cv2.waitKey(1) == ord('q'):
        break
vco.release.release()
cv2.destroyAllWindows()

```

## ii) Display the video
```
import numpy as np
import cv2
image = cv2.VideoCapture(0)
while True:
    ret, frame = image.read()
    cv2.imshow('myimage', frame)
    img1=cv2.resize(frame,None,fx=0.5,fy=0.5)   #resizing the image
    cv2.imshow("tedimage",img1)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## iii) Display the video by resizing the window
```
import cv2
import numpy as np
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(2))
    height=int(cap.get(2))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,None,fx=0.5,fy=0.5)
    image[:height//2,:width//2]=smaller_frame
    image[height//2:,:width//2]=smaller_frame
    image[:height//2,width//2:]=smaller_frame
    image[height//2:,width//2:]=smaller_frame
    cv2.imshow('myimage',smaller_frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()   
```
## iv) Rotate and display the video
```
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
<img width="349" alt="cop1" src="https://user-images.githubusercontent.com/93427376/226089795-91a3c4a2-c9e5-4c57-9921-8b328b7fd908.png">

### ii) Display the video
<img width="351" alt="cop2" src="https://user-images.githubusercontent.com/93427376/226089919-2e296826-cf11-456e-a8df-bf72eaa0b7d1.png">

### iii) Display the video by resizing the window
<img width="641" alt="cop3" src="https://user-images.githubusercontent.com/93427376/226089931-fc51294c-7fec-4cee-aa8c-c7796246b0f8.png">

### iv) Rotate and Display the video
<img width="646" alt="cop4" src="https://user-images.githubusercontent.com/93427376/226089957-73727285-1de2-40e7-9c53-da78218eb972.png">

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
