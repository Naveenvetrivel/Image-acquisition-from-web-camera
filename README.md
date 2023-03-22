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
Write the captured image using cv2.imwrite("video_image.jpg",frame)

### Step 3:
Resize the image using cv2.resize() to get a four-split screen.

### Step 4:
Rotate the image using cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)

### Step 5:
Display the image until the key to close the window is pressed

## Program:
``` 
### Developed By:V NAVEENKUMAR
### Register No:212221230068

## i) Write the frame as JPG file
~~~
obj = cv2.VideoCapture(0)
while(True):
    cap,frame = obj.read()
    cv2.imshow('video_image.jpg',frame)
    cv2.imwrite("out.jpg",frame)
    if cv2.waitKey(1) == ord('q'):
        break
obj.release()
cv2.destroyAllWindows()
~~~



## ii) Display the video
~~~
obj=cv2.VideoCapture(0)
while(True):
    cap,frame=obj.read()
    cv2.imshow('vid_img',frame)
    if cv2.waitKey(1)==ord('m'):
        break
obj.release()
cv2.destroyAllWindows()
~~~



## iii) Display the video by resizing the window
~~~
import numpy as np
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    w=int(cap.get(3))
    h=int(cap.get(4))
    img=np.zeros(frame.shape,np.uint8)
    small_f=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    img[:h//2,:w//2]=small_f
    img[h//2:,:w//2]=small_f
    img[:h//2,w//2:]=small_f
    img[h//2:,w//2:]=small_f
    cv2.imshow('img',img)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
~~~




## iv) Rotate and display the video
~~~
import numpy as np
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    w=int(cap.get(3))
    h=int(cap.get(4))
    img=np.zeros(frame.shape,np.uint8)
    small_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    img[:h//2,:w//2]=cv2.rotate(small_frame,cv2.ROTATE_180)
    img[h//2:,:w//2]=cv2.rotate(small_frame,cv2.ROTATE_180)
    img[:h//2,w//2:]=small_frame
    img[h//2:,w//2:]=small_frame
    cv2.imshow('img',img)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
~~~









## Output

### i) Write the frame as JPG image
![image](https://user-images.githubusercontent.com/94165322/226807199-a8f1bb64-66ca-46f6-82eb-87caba726f8a.png)




### ii) Display the video
![image](https://user-images.githubusercontent.com/94165322/226807380-eb44cf8d-0460-4d0a-99c2-9d09b5addfb3.png)



### iii) Display the video by resizing the window
![image](https://user-images.githubusercontent.com/94165322/226807476-6e03a0ce-79f4-4ba9-bd9c-43cd4bfb7498.png)




### iv) Rotate and display the video
![image](https://user-images.githubusercontent.com/94165322/226807566-2f039037-7a2e-42ef-aab4-bfc953a5a049.png)





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
