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

i)Image Translation
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
input_image=cv2.imread("flower.jpg")
input_image=cv2.cvtColor(input_image,cv2.COLOR_BGR2RGB)
plt.axis('off')
print("Input Image:")
plt.imshow(input_image)
plt.show()
rows,cols,dim=input_image.shape
M=np.float32([[1,0,100],[0,1,200],[0,0,1]])
translated_image=cv2.warpPerspective(input_image,M,(cols,rows))
plt.axis('off')
print("Image Translation:")
plt.imshow(translated_image)
plt.show()
```
ii) Image Scaling
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
input_image=cv2.imread('flower.jpg')
input_image=cv2.cvtColor(input_image,cv2.COLOR_BGR2RGB)
plt.axis('off')
print("Input Image:")
plt.imshow(input_image)
plt.show()
rows,cols,dim=input_image.shape
M=np.float32([[1.5,0,0],[0,1.8,0],[0,0,1]])
translated_image=cv2.warpPerspective(input_image,M,(cols*2,rows*2))
plt.axis('off')
print("Image Scaling:")
plt.imshow(translated_image)
plt.show()
```
iii)Image shearing
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
input_image=cv2.imread('flower.jpg')
input_image=cv2.cvtColor(input_image,cv2.COLOR_BGR2RGB)
plt.axis('off')
print("Input Image:")
plt.imshow(input_image)
plt.show()
rows,cols,dim=input_image.shape
M1=np.float32([[1,0.5,0],[0,1,0],[0,0,1]])
M2=np.float32([[1,0,0],[0.5,1,0],[0,0,1]])
translated_image1=cv2.warpPerspective(input_image,M1,(int(cols*1.5),int(rows*1.5)))
translated_image2=cv2.warpPerspective(input_image,M2,(int(cols*1.5),int(rows*1.5)))
plt.axis('off')
print("Image Shearing:")
plt.imshow(translated_image1)
plt.imshow(translated_image2)
plt.show()
```

iv)Image Reflection
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
input_image=cv2.imread('flower.jpg')
input_image=cv2.cvtColor(input_image,cv2.COLOR_BGR2RGB)
plt.axis('off')
print("Input Image:")
plt.imshow(input_image)
plt.show()
rows,cols,dim=input_image.shape
M1=np.float32([[1,0,0],[0,-1,rows],[0,0,1]])
M2=np.float32([[-1,0,cols],[0,1,0],[0,0,1]])
translated_image1=cv2.warpPerspective(input_image,M1,(int(cols),int(rows)))
translated_image2=cv2.warpPerspective(input_image,M2,(int(cols),int(rows)))
plt.axis('off')
print("Image Reflection:")
plt.imshow(translated_image1)
plt.imshow(translated_image2)
plt.show()
```

v)Image Rotation
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
input_image=cv2.imread('flower.jpg')
input_image=cv2.cvtColor(input_image,cv2.COLOR_BGR2RGB)
plt.axis('off')
print("Input Image:")
plt.imshow(input_image)
plt.show()
rows,cols,dim=input_image.shape
angle=np.radians(10)
M=np.float32([[np.cos(angle),-(np.sin(angle)),0],[np.sin(angle),np.cos(angle),0],[0,0,1]])
translated_image=cv2.warpPerspective(input_image,M,(int(cols),int(rows)))
plt.axis('off')
print("Image Rotation:")
plt.imshow(translated_image)
plt.show()
```

vi)Image Cropping
```
import cv2
import matplotlib.pyplot as plt
image = cv2.imread("flower.jpg")
h, w, _ = image.shape
cropped_face = image[int(h*0.2):int(h*0.8), int(w*0.3):int(w*0.7)]
cv2.imwrite("cropped_pigeon_face.jpg", cropped_face)
plt.imshow(cv2.cvtColor(cropped_face, cv2.COLOR_BGR2RGB))
plt.axis("off")
plt.show()
```

## Output:
### i)Image Translation
<img width="515" height="379" alt="download" src="https://github.com/user-attachments/assets/8d7396e8-76e4-46bf-8438-8f3c4d102872" />

### ii) Image Scaling
<img width="515" height="379" alt="download" src="https://github.com/user-attachments/assets/35abe1a7-211b-43a6-a336-0e64cd89af90" />

### iii)Image shearing
<img width="515" height="379" alt="download" src="https://github.com/user-attachments/assets/16adac71-8977-4a73-9f8f-e26cd4e1e3e9" />

### iv)Image Reflection
<img width="515" height="379" alt="download" src="https://github.com/user-attachments/assets/e856596d-0ea6-43f6-9618-fcd96aa1e663" />

### v)Image Rotation
<img width="515" height="379" alt="download" src="https://github.com/user-attachments/assets/f2e00038-1434-4b65-ad78-ed15c1672325" />

### vi)Image Cropping
<img width="356" height="389" alt="download" src="https://github.com/user-attachments/assets/89e48d2a-84a3-4f57-b55d-f4d5d61d74f7" />

## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
