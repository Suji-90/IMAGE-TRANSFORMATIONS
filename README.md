# IMAGE-TRANSFORMATIONS

## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import necessary libraries (cv2, numpy, matplotlib) and load the source image.

### Step2:
Create transformation matrices for translation, rotation, scaling, and shearing using functions like cv2.getRotationMatrix2D().

### Step3:
Apply the geometric transformations using cv2.warpAffine() for affine transformations and cv2.flip() for reflection.

### Step4:
Crop the image by selecting a specific rectangular region using NumPy array slicing.

### Step5:
Display the original and all transformed images with appropriate titles using matplotlib.pyplot.

## Program:
## Developed By: SUJITHRA K
## Register Number:212223040212
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('/content/flower.jpg')
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Original Image")
plt.axis('off')
```

i)Image Translation
```
tx, ty = 100, 50
M_translation = np.float32([[1, 0, tx], [0, 1, ty]])
# [1, 0, tx] - Horizontal shift by tx
# [0, 1, ty] - Vertical shift by ty
translated_image = cv2.warpAffine(image, M_translation, (image.shape[1], image.shape[0]))
plt.imshow(cv2.cvtColor(translated_image, cv2.COLOR_BGR2RGB))
plt.title("Translated Image")
plt.axis('off')
```
ii) Image Scaling
```
fx, fy = 5.0, 2.0 # Scaling factors (1.5x scaling for both width and height)
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)
plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB)) # Display the scaled image
plt.title("Scaled Image") # Set title
plt.axis('off')
```
iii)Image shearing
```
shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]]) # Shearing matrix
# The matrix shears the image by a factor of 0.5 in both x and y directions
# [1, 0.5, 0] - Shear along the x-axis (horizontal)
# [0.5, 1, 0] - Shear along the y-axis (vertical)
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))
plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB)) # Display the sheared image
plt.title("Sheared Image") # Set title
plt.axis('off')
```

iv)Image Reflection
```
reflected_image = cv2.flip(image, 2)
plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB)) # Display the reflected image
plt.title("Reflected Image") # Set title
plt.axis('off')
```

v)Image Rotation
```
(height, width) = image.shape[:2] # Get the image height and width
angle = 45 # Rotation angle in degrees (rotate by 45 degrees)
center = (width // 2, height // 2) # Set the center of rotation to the image center
M_rotation = cv2.getRotationMatrix2D(center, angle, 1) # Get the rotation matrix
# getRotationMatrix2D: Takes the center of rotation, angle, and scale factor (1 means no scaling
rotated_image = cv2.warpAffine(image, M_rotation, (width, height)) # Apply rotation
plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB)) # Display the rotated image
plt.title("Rotated Image") # Set title
plt.axis('off')
```

vi)Image Cropping
```
x, y, w, h = 100, 100, 200, 150 # Define the top-left corner (x, y) and the width (w) and heigh
# Cropping the image from coordinates (x, y) to (x+w, y+h)
cropped_image = image[y:y+h, x:x+w]
plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB)) # Display the cropped image
plt.title("Cropped Image") # Set title
plt.axis('off')
```

## Output:
### i)Image Translation
<img width="737" height="543" alt="image" src="https://github.com/user-attachments/assets/ecc3df2d-8b4c-4336-ab11-3a0236a19860" />


### ii) Image Scaling

<img width="756" height="456" alt="image" src="https://github.com/user-attachments/assets/1409f87b-b945-49d5-bc61-9fed77be1113" />


### iii)Image shearing

<img width="739" height="539" alt="image" src="https://github.com/user-attachments/assets/576f5a16-3458-4266-87c5-b7e2471fbae7" />

### iv)Image Reflection

<img width="748" height="541" alt="image" src="https://github.com/user-attachments/assets/83b52e47-fb92-4d79-be7e-2cbf4b4b69e3" />


### v)Image Rotation

<img width="740" height="541" alt="image" src="https://github.com/user-attachments/assets/37491230-072c-4cc1-adc6-76b1cfaacef4" />


### vi)Image Cropping

<img width="719" height="532" alt="image" src="https://github.com/user-attachments/assets/c304f720-2e91-4bae-886b-07ec866a239c" />


## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
