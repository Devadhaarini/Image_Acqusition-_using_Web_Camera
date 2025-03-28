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
Use cv2.VideoCapture(0) to access web camera.

### Step 2:
Use cv2.imread to read the video or image.

### Step 3:
Use cv2.imwrite to save the image.

### Step 4:
Use cv2.imshow to show the video.

### Step 5:
End the program and close the output video window by pressing 'q'.

## Program:

### Developed By: DEVADHAARINI.D
### Register No: 212223230040

## i) Write the frame as JPG file
```
import cv2
viedoCaptureObject=cv2.VideoCapture(0)
ret,frame=viedoCaptureObject.read()
cv2.imwrite("jennie.jpg",frame)
viedoCaptureObject.release()
cv2.destroyAllWindows()
```

## ii) Display the video
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
ret,frame=cap.read()
cv2.imshow('captured_frame',frame)
cv2.waitKey(10000)
cap.release()
cv2.destroyAllWindows()
```

## iii) Display the video by resizing the window
```
import cv2
import numpy as np
cap  = cv2.VideoCapture(0)
ret,frame = cap.read()
width = int(cap.get(3))
height = int(cap.get(4))
image = np.zeros(frame.shape, np.uint8)
small_frame = cv2.resize(frame,(0,0),fx =0.5, fy = 0.5)
image[:height//2, :width//2]=small_frame
image[height//2:, :width//2]=small_frame
image[:height//2, width//2:]=small_frame
image[height//2:, width//2:]=small_frame
cv2.imshow('',image)
cv2.waitKey(5000)
image_dict={'captured_image1':image}
cv2.imwrite('captured_image1.jpg',image)
cap.release()
cv2.destroyAllWindows()
```

## iv) Rotate and display the video
```
import cv2
import numpy as np
cap  = cv2.VideoCapture(0)
while True:
    ret,frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8)
    small_frame = cv2.resize(frame,(0,0),fx =0.5, fy = 0.5)
    image[:height//2, :width//2]=cv2.rotate(small_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=small_frame
    image[:height//2, width//2:]=small_frame
    image[height//2:, width//2:]=cv2.rotate(small_frame,cv2.ROTATE_180)
    cv2.imshow('myimage',image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

## Output

### i) Write the frame as JPG image 
<br>
![Screenshot 2025-03-29 000147](https://github.com/user-attachments/assets/071c2ede-3028-4210-90c1-66eff22ecbdc)
<\br>

### ii) Display the video
![image](https://github.com/user-attachments/assets/18cdefe2-1ed8-4a80-8770-0dd83fd2310f)


### iii) Display the video by resizing the window
![Screenshot 2025-03-29 000216](https://github.com/user-attachments/assets/c15b9185-8b11-464e-9192-50d76c1286a4)


### iv) Rotate and display the video
![Screenshot 2025-03-28 234606](https://github.com/user-attachments/assets/9fc6b4d9-5f52-4d77-8dbf-174032af8e8e)


## Result:
Thus the image is accessed from webcamera and displayed using openCV.
