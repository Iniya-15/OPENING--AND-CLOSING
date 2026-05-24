# Ex---10-OPENING--AND-CLOSING
# Name : Iniya E
# Reg No : 212224230096
## Aim
To implement Opening and Closing using Python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step1:
Import the necessary packages

### Step2:
Create the Text using cv2.putText

### Step3:
Create the structuring element

### Step4:
Use Opening operation

### Step5:
Use Closing Operation

 
## Program:

``` Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
def load_img():
    blank_img=np.zeros((600,600))
    font=cv2.FONT_HERSHEY_SIMPLEX
    cv2.putText(blank_img,text='HARINI',org=(50,300), fontFace=font, fontScale=5, color=(255,255,255), thickness=25, lineType=cv2.LINE_AA)
    return blank_img
def display_img(img):
    fig=plt.figure(figsize=(12,10))
    ax=fig.add_subplot(111)
    ax.imshow(img,cmap='gray')
    plt.show()
display_img(img)
white_noise=np.random.randint(low=0,high=2,size=(600,600))
white_noise=white_noise*255
noise_img=img+white_noise
display_img(noise_img)
kernel = np.ones((5,5), np.uint8)  # You can adjust the kernel size as needed (3,3), (5,5), (7,7), etc.

# Apply morphological opening (erosion followed by dilation)
opening = cv2.morphologyEx(noise_img, cv2.MORPH_OPEN, kernel)
display_img(opening)
img=load_img()
black_noise=np.random.randint(low=0,high=2,size=(600,600))
black_noise=black_noise*-255
black_noise_img=img+black_noise
black_noise_img[black_noise_img==-255]=0
display_img(black_noise_img)
closing_image = cv2.morphologyEx(black_noise_img, cv2.MORPH_CLOSE, kernel)
display_img(closing_image)


```
## Output:

<img width="766" height="589" alt="image" src="https://github.com/user-attachments/assets/a49106d3-b6a0-4a71-9b15-5661ef0e4fce" />

<img width="772" height="594" alt="image" src="https://github.com/user-attachments/assets/553d21b1-e027-4aaa-ba5a-15cebd060526" />



## Result
Thus the Opening and Closing operation is used in the image using python and OpenCV.
