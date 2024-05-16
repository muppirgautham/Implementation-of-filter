# Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
step1 :- Import the required modules.

Step2 :- Convert the image from BGR to RGB.

Step3:- Apply the required filters for the image separately.

Step4:- Plot the original and filtered image by using matplotlib.pyplot

Step5:- End the program.

## Program:
### Developed By   : M Gautham
### Register Number: 212221230027

### 1. Smoothing Filters

i) Using Averaging Filter
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("car.jpg")
original_image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)

kernel1 = np.ones((11,11),np.float32)/121
avg_filter = cv2.filter2D(original_image,-1,kernel1)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(avg_filter)
plt.title("Filtered")
plt.axis("off")

```
ii) Using Weighted Averaging Filter
```
kernel2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
weighted_filter = cv2.filter2D(original_image,-1,kernel2)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(weighted_filter)
plt.title("Filtered")
plt.axis("off")

```
iii) Using Gaussian Filter
```
gaussian_blur = cv2.GaussianBlur(src = original_image, ksize = (11,11), sigmaX=0, sigmaY=0)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Filtered")
plt.axis("off"

```

iv) Using Median Filter
```
median = cv2.medianBlur(src=original_image,ksize = 11)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Filtered")
plt.axis("off")


```

### 2. Sharpening Filters
i) Using Laplacian Kernal
```
kernel3 = np.array([[0,1,0],[1,-4,1],[0,1,0]])
laplacian_kernel = cv2.filter2D(original_image,-1,kernel3)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian_kernel)
plt.title("Filtered")
plt.axis("off")

```
ii) Using Laplacian Operator
```
laplacian_operator = cv2.Laplacian(original_image,cv2.CV_64F)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian_operator)
plt.title("Filtered")
plt.axis("off")

```

## OUTPUT:
### 1. Smoothing Filters


i) Using Averaging Filter

![image](https://github.com/muppirgautham/Implementation-of-filter/assets/94810884/e2b592c4-eb19-4347-8aba-3317fc03905f)


ii) Using Weighted Averaging Filter

![image](https://github.com/muppirgautham/Implementation-of-filter/assets/94810884/c3392453-42ee-4f9b-90d9-b795c3e6d702)


iii) Using Gaussian Filter

![image](https://github.com/muppirgautham/Implementation-of-filter/assets/94810884/ea49ebb1-298e-48df-b29c-b76b1c4b5d86)


iv) Using Median Filter

![image](https://github.com/muppirgautham/Implementation-of-filter/assets/94810884/08f5c043-9883-4284-a2b8-82058b14ddc1)


### 2. Sharpening Filters


i) Using Laplacian Kernal

![image](https://github.com/muppirgautham/Implementation-of-filter/assets/94810884/a19e703d-faf3-4ea4-b0f2-c9da2fd00750)

ii) Using Laplacian Operator

![image](https://github.com/muppirgautham/Implementation-of-filter/assets/94810884/d335e889-31a7-4941-bf60-1850846b6931)

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
