## Image-Acquisition-from-Web-Cameraa
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
Use VideoCapture(0) to access web camera

### Step 2:
Use imread to read the video or image

### Step 3:
Use imwrite to save the image

### Step 4:
Use imshow to show the video

### Step 5:
End the program and close the output video windows by pressing 'q'.

## Program:
``` 
Developed By: Rasika.M
Register No: 212222230117
```


## i) Write the frame as JPG file
```
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while (True):
    ret,frame = videoCaptureObject.read()
    cv2.imwrite("Rasika.jpeg",frame)
    result = False
videoCaptureObject.release()
cv2.destroyAllWindows()
```



## ii) Display the video
```
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imshow('myimage',frame)
    if cv2.waitKey(1) == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()
```



## iii) Display the video by resizing the window
```
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
```




## iv) Rotate and display the video
```
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
</br>!![Screenshot from 2023-11-04 09-28-05](https://github.com/rasika1206/Image-Acquisition-from-Web-Cameraa/assets/124434806/03cf48e7-cf47-4788-8559-8bc729951091)

</br>

### ii) Display the video
</br>![2](https://github.com/rasika1206/Image-Acquisition-from-Web-Cameraa/assets/124434806/a66665b8-cc95-41e5-95dd-bf108c60bce1)

</br>


### iii) Display the video by resizing the window
</br>![3](https://github.com/rasika1206/Image-Acquisition-from-Web-Cameraa/assets/124434806/7c0f7e57-189d-4db4-a48c-ccebf3385127)

</br>



### iv) Rotate and display the video
</br>![4](https://github.com/rasika1206/Image-Acquisition-from-Web-Cameraa/assets/124434806/99ee45b0-f7a0-4dbf-8aa9-595e93ed8454)

</br>





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
