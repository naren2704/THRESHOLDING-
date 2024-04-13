# THRESHOLDING
## Aim :
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required :
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm :
 
### Step1:
Load the necessary packages.

### Step2:
Read the Image and convert to grayscale.

### Step3:
Use Global thresholding to segment the image.

### Step4:
Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image and display the results.

## Program
### NAME : NARENDRAN.B
### REG NO : 212222240069
# Load the necessary packages
```
import numpy as np
import matplotlib.pyplot as plt
import cv2
```



# Read the Image and convert to grayscale
```
image = cv2.imread("BOY.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("BOY.jpg",0)
```


# Use Global thresholding to segment the image
```
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```

# Use Adaptive thresholding to segment the image
```
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```


# Use Otsu's method to segment the image 
```
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```

# Display the results
```
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()




```
## Output

### Original Image :


![image](https://github.com/Mamthaiyappaprabu/THRESHOLDING-/assets/119393563/60648559-d414-4a27-bd64-74e1257bbb2a)


### Global Thresholding :





***BINARY:***


![image](https://github.com/Mamthaiyappaprabu/THRESHOLDING-/assets/119393563/1822f08a-3607-4ea5-917d-11e5331674a4)



  
***BINARY INVERSE:***


![image](https://github.com/Mamthaiyappaprabu/THRESHOLDING-/assets/119393563/c638b91b-aa0c-4474-aac8-311a1a7cf50e)




***ZERO:***




![image](https://github.com/Mamthaiyappaprabu/THRESHOLDING-/assets/119393563/d3803175-0a2c-438d-934d-bbe83c10c2dd)






***ZERO INVERSE:***


![image](https://github.com/Mamthaiyappaprabu/THRESHOLDING-/assets/119393563/7d770b11-3d84-4b67-825e-6d2ab1a62529)






***TRUNCATE:***



![image](https://github.com/Mamthaiyappaprabu/THRESHOLDING-/assets/119393563/852d9c6e-73cf-4451-ade8-1f3413e7fa90)






### Adaptive Thresholding :






***MEAN:***




![image](https://github.com/Mamthaiyappaprabu/THRESHOLDING-/assets/119393563/d0bf6c25-f367-41ba-8f18-254e3f0366f5)





***GAUSSIAN:***




![image](https://github.com/Mamthaiyappaprabu/THRESHOLDING-/assets/119393563/4f0fdff2-8344-4090-9ede-9a4ec3150389)




### Optimum Global Thesholding using Otsu's Method :




![image](https://github.com/Mamthaiyappaprabu/THRESHOLDING-/assets/119393563/c0f0e550-1759-43b6-af1e-510d6c7429d6)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
