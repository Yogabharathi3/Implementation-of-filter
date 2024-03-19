# Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
Import cv2, matplotlib.py libraries and read the saved images using cv2.imread().

### Step2
Convert the saved BGR image to RGB using cvtColor().

### Step3
By using the following filters for image smoothing:filter2D(src, ddepth, kernel), Box filter,Weighted Average filter,GaussianBlur(src, ksize, sigmaX[, dst[, sigmaY[, borderType]]]), medianBlur(src, ksize),and for image sharpening:Laplacian Kernel,Laplacian Operator.

### Step4
Apply the filters using cv2.filter2D() for each respective filters.

### Step5
Plot the images of the original one and the filtered one using plt.figure() and cv2.imshow(). 

## Program:
### Developed By   :Yogabharathi S
### Register Number:212222230179

### 1. Smoothing Filters

i) Using Averaging Filter
```Python
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("squil.jpeg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/121
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(8,8))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")
plt.show()
```
#### ii) Using Weighted Averaging Filter
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("squil.jpg")
original_image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
kernel2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
weighted_filter = cv2.filter2D(original_image,-1,kernel2)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(weighted_filter)
plt.title("Weighted Averaging Filter Image")
plt.axis("off")
```
#### iii) Using Gaussian Filter
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("squil.jpeg")
original_image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
gaussian_blur = cv2.GaussianBlur(src = original_image, ksize = (11,11), sigmaX=0, sigmaY=0)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Filter Image")
plt.axis("off")

```
#### iv) Using Median Filter
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("squil.jpeg")
original_image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
median = cv2.medianBlur(src=original_image,ksize = 11)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Median Filter Image")
plt.axis("off")
```

### 2. Sharpening Filters
#### i) Using Laplacian Kernal
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("squil.jpeg")
original_image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
kernel3 = np.array([[0,1,0],[1,-4,1],[0,1,0]])
laplacian_kernel = cv2.filter2D(original_image,-1,kernel3)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian_kernel)
plt.title("Laplacian kernelFiltered Image")
plt.axis("off")
```
#### ii) Using Laplacian Operator
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("squil.jpeg")
original_image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
laplacian_operator = cv2.Laplacian(original_image,cv2.CV_64F)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian_operator)
plt.title(" Laplacian operator Filtered Image")
plt.axis("off")
```

## OUTPUT:
### 1. Smoothing Filters
#### i) Using Averaging Filter
![Screenshot 2024-03-19 111822](https://github.com/Yogabharathi3/Implementation-of-filter/assets/118899387/89d065a7-4bcd-4f11-b713-4f2b1a3584a6)

#### ii) Using Weighted Averaging Filter
![Screenshot 2024-03-19 112029](https://github.com/Yogabharathi3/Implementation-of-filter/assets/118899387/51e7a3b9-e837-42cb-a607-119f880f34de)


#### iii) Using Gaussian Filter
![Screenshot 2024-03-19 112351](https://github.com/Yogabharathi3/Implementation-of-filter/assets/118899387/2eed3609-eade-47fa-9973-83c1a163260c)


#### iv) Using Median Filter
![Screenshot 2024-03-19 112617](https://github.com/Yogabharathi3/Implementation-of-filter/assets/118899387/df8f07b6-6c07-4841-95f3-b1a863f92b7a)


### 2. Sharpening Filters

#### i) Using Laplacian Kernal
![Screenshot 2024-03-19 112713](https://github.com/Yogabharathi3/Implementation-of-filter/assets/118899387/a854d240-0761-476b-a85f-812cedf119e2)

#### ii) Using Laplacian Operator
![image](https://github.com/Yogabharathi3/Implementation-of-filter/assets/118899387/1275b43d-fb94-4cda-9355-7dfab4b46fb6)


## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
