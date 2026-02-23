# Implementation of filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
Import the required libraries.


### Step2
Convert the image from BGR to RGB.

### Step3
Apply the required filters for the image separately.

### Step4
Plot the original and filtered image by using matplotlib.pyplot.

### Step5
End the program.

## Program:
### Developed By   : JANANI S
### Register Number: 212223230086
</br>

### 1. Smoothing Filters

```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('mammal.jpg', cv2.COLOR_BGR2RGB)
kernel = np.ones((5,5), dtype = np.float32) / 5**2
print (kernel)
```
i) Using Averaging Filter
```Python
image = cv2.imread('mammal.jpg')
dst = cv2.filter2D(image, ddepth = -1, kernel = kernel)
plt.figure(figsize = [20,10])
plt.subplot(121); plt.axis('off'); plt.imshow(image[:,:,::-1]); plt.title("Original Image")
plt.subplot(122); plt.axis('off'); plt.imshow(dst[:,:,::-1]);   plt.title("Convolution Result")
```
ii) Using Weighted Averaging Filter
```Python
average_filter = cv2.blur(image, (30,30))
plt.figure(figsize = (18, 6))
plt.subplot(121); plt.imshow(image [:, :, ::-1]); plt.title('Input Image')
plt.subplot(122); plt.imshow(average_filter[:, :, ::-1]); plt.title('Output Image ( Average Filter)')
```
iii) Using Gaussian Filter
```Python
gaussian_filter = cv2.GaussianBlur(image, (29,29), 0, 0)
plt.figure(figsize = (18, 6))
plt.subplot(121); plt.imshow(image [:, :, ::-1]); plt.title('Input Image')
plt.subplot(122); plt.imshow(gaussian_filter[:, :, ::-1]); plt.title('Output Image ( Gaussian Filter)')
```
iv)Using Median Filter
```Python
median_filter = cv2.medianBlur(image, 19)
plt.figure(figsize = (18, 6))
plt.subplot(121); plt.imshow(image [:, :, ::-1]); plt.title('Input Image')
plt.subplot(122); plt.imshow(median_filter[:, :, ::-1]); plt.title('Output Image ( Median_filter)')

```

### 2. Sharpening Filters
i) Using Laplacian Linear Kernal
```Python
laplacian_kernel = np.array([[0, -1, 0],[-1, 5, -1],[0, -1, 0]])
sharpened_laplacian_kernel = cv2.filter2D(image, -1, kernel = laplacian_kernel)
plt.figure(figsize = (18, 6))
plt.subplot(121); plt.imshow(image [:, :, ::-1]); plt.title('Input Image')
plt.subplot(122); plt.imshow(sharpened_laplacian_kernel[:, :, ::-1]); plt.title('Output Image ( Laplacian_filter)')
```
ii) Using Laplacian Operator
```Python
gray_image = cv2.cvtColor(image, cv2.COLOR_RGB2GRAY)
laplacian_operator = cv2.Laplacian(gray_image, cv2.CV_64F)
laplacian_operator = np.uint8(np.absolute(laplacian_operator))
plt.figure(figsize = (18, 6))
plt.subplot(131); plt.imshow(image [:, :, ::-1]); plt.title('Input Image')
plt.subplot(132); plt.imshow(gray_image, cmap='gray'); plt.title('Gray_image')
plt.subplot(133); plt.imshow(laplacian_operator,cmap='gray'); plt.title('Output Image ( Laplacian_filter)')
```

## OUTPUT:
### 1. Smoothing Filters
</br>

i) Using Averaging Filter
<img width="1233" height="459" alt="image" src="https://github.com/user-attachments/assets/6dbf0909-ed2c-46e0-a38b-6cd6a1de34c3" />


ii)Using Weighted Averaging Filter

<img width="1242" height="444" alt="image" src="https://github.com/user-attachments/assets/ca4925fc-04b6-45c3-89ff-832796c2d65c" />


iii)Using Gaussian Filter

<img width="1245" height="446" alt="image" src="https://github.com/user-attachments/assets/6755add8-cde5-44e2-868c-5f83d4d10062" />


iv) Using Median Filter

<img width="1239" height="459" alt="image" src="https://github.com/user-attachments/assets/8d706a4f-1c82-4c28-9dc7-35ad0fd27954" />


### 2. Sharpening Filters
</br>

i) Using Laplacian Kernal

<img width="1242" height="464" alt="image" src="https://github.com/user-attachments/assets/be293c3d-70de-48e1-a5fc-74cb776b8451" />


ii) Using Laplacian Operator

<img width="1243" height="333" alt="image" src="https://github.com/user-attachments/assets/376d25dc-21fd-416a-9d7d-91f8e9337ada" />


## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
