# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
## Step 1:
Import necessary libraries such as OpenCV, NumPy, and Matplotlib for image processing and visualization.

## Step 2:
Read the input image using cv2.imread() and store it in a variable for further processing

## Step 3:
Apply various transformations like translation, scaling, shearing, reflection, rotation, and cropping by defining corresponding functions:

1.Translation moves the image along the x or y-axis.

2.Scaling resizes the image by scaling factors.

3.Shearing distorts the image along one axis.

4.Reflection flips the image horizontally or vertically.

5.Rotation rotates the image by a given angle.

## Step 4:
Display the transformed images using Matplotlib for visualization. Convert the BGR image to RGB format to ensure proper color representation.

## Program:
```python
Developed By:D.Raju
Register Number:212224240128
```
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image=cv2.imread("Image1.jpg")
image.shape
#Display the images.
plt.imshow(image[:,:,::-1])
plt.title("Original Image")
plt.show()
```
## Output:
<img width="578" height="556" alt="Screenshot 2025-09-06 100943" src="https://github.com/user-attachments/assets/414f34c0-cb30-44b9-b026-73e78eafc647" />

## i)Image Translation
```
tx,ty=100,200
M_translation=np.float32([[1,0,tx],[0,1,ty]])
translated_image=cv2.warpAffine(image,M_translation, (673,419))
plt.imshow(translated_image[:,:,::-1])
plt.title("Translated Image")
plt.axis("on")
plt.show()
```
## Output:
<img width="742" height="474" alt="Screenshot 2025-09-06 100949" src="https://github.com/user-attachments/assets/06a93907-20a5-4e49-8a62-ac3750e69329" />

## ii) Image Scaling
```
fx, fy = 5.0, 2.0  
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)

plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB))  
plt.title("Scaled Image")  # Set title
plt.axis('off')
```
## Output:
<img width="688" height="295" alt="Screenshot 2025-09-06 100955" src="https://github.com/user-attachments/assets/de51f321-3a0c-4634-8f94-6f8bca80dab3" />


## iii)Image shearing
```
shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]])
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))

plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB))  
plt.title("Sheared Image")  
plt.axis('off')
```
## Output:
<img width="538" height="520" alt="Screenshot 2025-09-06 101001" src="https://github.com/user-attachments/assets/c3fbe5a6-3e17-4496-8ced-055326b5ff21" />


## iv)Image Reflection
```
reflected_image = cv2.flip(image, 2)

plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB))  
plt.title("Reflected Image")  
plt.axis('off')
```
## Output:
<img width="522" height="511" alt="Screenshot 2025-09-06 101007" src="https://github.com/user-attachments/assets/4c52c748-01c2-464c-bfdb-9c23a8d9b452" />



## v)Image Rotation
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
## Output:
<img width="520" height="515" alt="Screenshot 2025-09-06 101013" src="https://github.com/user-attachments/assets/89a94797-f756-434e-9193-cb6d6f1e6689" />


## vi)Image Cropping
```
x, y, w, h = 100, 100, 200, 150 
cropped_image = image[y:y+h, x:x+w]

plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB)) 
plt.title("Cropped Image")  
plt.axis('off')
```
## Output:
<img width="684" height="510" alt="Screenshot 2025-09-06 101019" src="https://github.com/user-attachments/assets/c179cd2b-b635-4e6a-ab3d-dc59f92f21a9" />

## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
