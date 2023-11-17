# IMAGETRANSFORMATION

## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import the necessary libraries and read the original image and save it a image variable.

### Step2:
Write a code to translation of the image.

### Step3:
Write a code for scaling of the image.

### Step4:
Write a code for shearing of the image.


### Step5:
Write a code for reflection of the image.
### Step6:
Write a code to rotation of the image.

### Step7:
Write a code to cropping of the image.

### Step8:
Display all the Transformed images.

## Program:

Developed By: Adhithya.S

Register Number: 212222240003
### i)Image Translation
```
import numpy as np
import matplotlib.pyplot as plt 
import cv2 as cv
```
```
#plotting of an image :

image = cv.imread("tree.jpg")
image = cv.cvtColor(image, cv.COLOR_BGR2RGB)

plt.axis("off")
plt.imshow(image)
plt.show()

#translation of an image :

rows,cols,dim = image.shape

M = np.float32([[1,0,100], [0,1,50],[0,0,1]])
translated_image= cv.warpPerspective(image, M, (cols, rows))

plt.axis("off")
plt.imshow(translated_image)
plt.show()
```
### ii) Image Scaling
```
rows,cols,dim = image.shape

M_scale = np.float32([[1,0,0], [0,1.5,0],[0,0,1]])
scale_image= cv.warpPerspective(image, M_scale, (cols, rows))

plt.axis("off")
plt.imshow(scale_image)
plt.show()
```


### iii)Image shearing
```
M_x = np.float32([[1,1,0], [0,1,0],[0,0,1]])

M_y = np.float32([[1,0,0], [0.4,1,0],[0,0,1]])

shear_imagex= cv.warpPerspective(image, M_x, (cols, rows))
shear_imagey= cv.warpPerspective(image, M_y, (cols, rows))

plt.axis("off")
plt.imshow(shear_imagex)
plt.show()

plt.axis("off")
plt.imshow(shear_imagey)
plt.show()
```

### iv)Image Reflection
```
M_x = np.float32([[1,0,0],[0,-1,rows],[0,0,1]])

M_y = np.float32([[-1,0,cols], [0,1,0],[0,0,1]])

ref_imagex= cv.warpPerspective(image, M_x, (cols, rows))
ref_imagey= cv.warpPerspective(image, M_y, (cols, rows))

plt.axis("off")
plt.imshow(ref_imagex)
plt.show()

plt.axis("off")
plt.imshow(ref_imagey)
plt.show()
```


### v)Image Rotation
```
angle = 90 
height, width = image.shape[:2]
rotation_matrix = cv2.getRotationMatrix2D((width / 2, height / 2), angle, 1)
rotated_image = cv2.warpAffine(image, rotation_matrix, (width, height))
plt.figure(figsize=(10, 5))
plt.subplot(1, 2, 1)
plt.title('Original Image')
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.subplot(1, 2, 2)
plt.title('Rotated Image')
plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB))

plt.show()
```


### vi)Image Cropping
```
x1, y1 = 100, 100 
x2, y2 = 300, 300 
cropped_image = image[y1:y2, x1:x2]
plt.subplot(1, 2, 2)
plt.title('Cropped Image')
plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB))

plt.show()



```
## Output:
### i)Image Translation
![image](https://github.com/s-adhithya/IMAGETRANSFORMATION/assets/113497423/2733edbf-41fe-4022-926b-f923dc71dd40)
![image](https://github.com/s-adhithya/IMAGETRANSFORMATION/assets/113497423/0a0e03d2-196f-4da9-b0d2-d98aa834b51a)


### ii) Image Scaling
![image](https://github.com/s-adhithya/IMAGETRANSFORMATION/assets/113497423/ef68f8ef-eb99-4809-b056-e185a2a8189d)



### iii)Image shearing
![image](https://github.com/s-adhithya/IMAGETRANSFORMATION/assets/113497423/5d9d2d45-62b4-482e-99c1-3a49f31bcf7b)
![image](https://github.com/s-adhithya/IMAGETRANSFORMATION/assets/113497423/2cb9b991-ce76-4023-a060-23b6813ea87b)



### iv)Image Reflection
![image](https://github.com/s-adhithya/IMAGETRANSFORMATION/assets/113497423/6783d8a4-241e-4200-903b-7c3719da3c96)
![image](https://github.com/s-adhithya/IMAGETRANSFORMATION/assets/113497423/803ead07-db9a-48fc-b39a-03317af7283c)




### v)Image Rotation
![image](https://github.com/s-adhithya/IMAGETRANSFORMATION/assets/113497423/50f06b0d-abdb-4500-9a7e-b2b221c8eea3)




### vi)Image Cropping
![image](https://github.com/s-adhithya/IMAGETRANSFORMATION/assets/113497423/a4f7e189-19df-4e61-92ff-2ef04cb28c88)





## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
