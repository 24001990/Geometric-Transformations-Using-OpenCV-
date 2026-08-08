## Geometric Transformations Using OpenCV
## Aim
To write a Python program using OpenCV to perform various geometric transformations on an image.

The program performs the following operations:

Image Translation
Image Scaling (Resizing)
Image Shearing
Image Reflection (Flipping)
Image Rotation
## Software Used
Anaconda – Python 3.7
Jupyter Notebook / VS Code
OpenCV (cv2)
NumPy
Matplotlib
## Algorithm
## Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

## Step 2:
Read the input image in color mode.

## Step 3: Image Translation
Create a translation matrix to shift the image
Move the image 50 pixels to the right and 80 pixels down
Apply transformation using cv2.warpAffine()
Display original and translated images
## Step 4: Image Scaling
Resize the image to 0.5× (downscale)
Resize the image to 2× (upscale)
Use cv2.resize()
Display original, downscaled, and upscaled images
## Step 5: Image Shearing
Create transformation matrices for:
Horizontal shearing
Vertical shearing
Apply transformations using cv2.warpAffine()
Display original and sheared images
## Step 6: Image Reflection
Perform flipping using cv2.flip():
Horizontal reflection
Vertical reflection
Both axes
Display all reflected images
## Step 7: Image Rotation
Create rotation matrices for:
45° rotation
90° rotation
Use cv2.getRotationMatrix2D() and cv2.warpAffine()
Display original and rotated images
## Program
```
Developed By:
Name: DODLA SUSMITHA

Register No:212224110016
```

```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image=cv2.imread("image.png")
image.shape
#Display the images.
plt.imshow(image[:,:,::-1])
plt.title("Original Image")
plt.show()
```
<img width="552" height="387" alt="15e79a4d-16c4-4d3a-aeee-652a5cb23217" src="https://github.com/user-attachments/assets/4bab6fac-abe0-446e-a61f-79a427db17cc" />


## i) Image Translation
```
tx,ty=100,200
M_translation=np.float32([[1,0,tx],[0,1,ty]])
translated_image=cv2.warpAffine(image,M_translation, (673,419))
plt.imshow(translated_image[:,:,::-1])
plt.title("Translated Image")
plt.axis("on")
plt.show()
```
<img width="552" height="373" alt="774fdb86-f9f2-4f40-a5e5-285ade11e456" src="https://github.com/user-attachments/assets/5e496af8-77f8-4ea9-9db7-75619652b619" />

## ii) Image Scaling
```
fx, fy = 5.0, 2.0  
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)

plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB))  
plt.title("Scaled Image")  # Set title
plt.axis('off')

```
<img width="515" height="170" alt="be7cecd6-7b70-4a81-927e-55e03e940f72" src="https://github.com/user-attachments/assets/60593ff1-1cf3-4f5a-a8b2-e4df7f5e8d4e" />


## iii) Image Shearing
```
shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]])
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))

plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB))  
plt.title("Sheared Image")  
plt.axis('off')

```
<img width="515" height="363" alt="e61d6784-af0d-4a32-87fc-5fed7daec3bf" src="https://github.com/user-attachments/assets/e68fc1a0-5c90-458c-beed-e3c180f121d3" />


## iv) Image Reflection
```
reflected_image = cv2.flip(image, 2)

plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB))  
plt.title("Reflected Image")  
plt.axis('off')

```
<img width="515" height="363" alt="e948bd33-d79b-4321-8e28-2782f76a54a4" src="https://github.com/user-attachments/assets/71359730-4856-4143-8ac2-ede95d5dc795" />


## v) Image Rotation
```
(height, width) = image.shape[:2] 
angle = 45 
center = (width // 2, height // 2)  
M_rotation = cv2.getRotationMatrix2D(center, angle, 1)
rotated_image = cv2.warpAffine(image, M_rotation, (width, height))

plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB)) 
plt.title("Rotated Image")  
plt.axis('off')

```
<img width="515" height="363" alt="5d272736-d1ce-4374-9836-538242b71f8c" src="https://github.com/user-attachments/assets/5a3422d4-0fe4-4a72-bde9-2153edd0f459" />


## vi) Image Cropping
```x, y, w, h = 100, 100, 200, 150 
cropped_image = image[y:y+h, x:x+w]

plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB)) 
plt.title("Cropped Image")  
plt.axis('off')
```

<img width="512" height="410" alt="57b46803-9130-4a3d-be34-7ee41172c583" src="https://github.com/user-attachments/assets/861734a5-e271-4011-a167-6903e7e9e3a6" />

## Result:
Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.


