# COLOR_CONVERSIONS_OF-IMAGE
## AIM
To write a python program using OpenCV to do the following image manipulations.

i) Read, display, and write an image.

ii) Access the rows and columns in an image.

iii) Cut and paste a small portion of the image.

iv)To perform the color conversion between RGB, BGR, HSV, and YCbCr color models.


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Choose an image and save it as a filename.jpg ,
### Step2:
Use imread(filename, flags) to read the file.
### Step3:
Use imshow(window_name, image) to display the image.
### Step4:
Use imwrite(filename, image) to write the image.
### Step5:
End the program and close the output image windows.
### Step6:
Convert BGR and RGB to HSV and GRAY
### Step7:
Convert HSV to RGB and BGR
### Step8:
Convert RGB and BGR to YCrCb
### Step9:
Split and Merge RGB Image
### Step10:
Split and merge HSV Image

##### Program:
### Developed By    : Sanjay S    
### Register Number : 212221243002


### i) Read and display the image
```
import cv2
import matplotlib.pyplot as plt

img=cv2.imread("nebula.jpg",1)
cv2.imshow("display window",img)
cv2.waitKey(0)
cv2.destroyAllWindows()
print(img.shape)
```
## Output:

![Screenshot 2024-02-15 165216](https://github.com/sanjay5656/COLOR_CONVERSIONS_OF-IMAGE/assets/115128955/d4e6f2e7-53d3-4ca0-b3da-836f1cc880f7)


### ii)Write the image
```
img1=cv2.imread("nebula.jpg",0)
cv2.imshow("display window",img1)
cv2.waitKey(0)
cv2.destroyAllWindows()
cv2.imwrite('greyscale.jpeg',img1)
```

## Output:

![Screenshot 2024-02-15 172649](https://github.com/sanjay5656/COLOR_CONVERSIONS_OF-IMAGE/assets/115128955/b5969d6f-a1db-4dae-bccd-4b2a7b7f491a)

### iii)Shape of the Image
```
import cv2
img1=cv2.imread("nebula.jpg",1)
print(img1.shape)
```

## Output:

![Screenshot 2024-02-15 172649](https://github.com/sanjay5656/COLOR_CONVERSIONS_OF-IMAGE/assets/115128955/b5969d6f-a1db-4dae-bccd-4b2a7b7f491a)

### iv)Access rows and columns
```
import random
import cv2
image=cv2.imread('nebula.jpg',1)
#image=cv2.resize(image,(400,400))
for i in range (150,200):
    for j in range(image.shape[1]):
        image[i][j]=[random.randint(0,255),
                    random.randint(0,255),
                    random.randint(0,255)] 
cv2.imshow('part image',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

## Output:

![Screenshot 2024-02-15 165248](https://github.com/sanjay5656/COLOR_CONVERSIONS_OF-IMAGE/assets/115128955/79f9e8aa-0c73-4e41-94fa-57bb9e235511)


### v)Cut and paste portion of image
```
import cv2
img2 = cv2.imread("nebula.jpg")
x = 0
y = 200
x1 = 160
y1 = 450
x2 = 0
y2 = 0
cropimg = img2[x:x1+x2, y:y1+y2]
cv2.imshow("Original Image", img2)
cv2.imshow("Cropped Image", cropimg)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

## Output:

![Screenshot 2024-02-15 165308](https://github.com/sanjay5656/COLOR_CONVERSIONS_OF-IMAGE/assets/115128955/50a255e0-ce64-471a-ae7d-0f5f914abc1f)
![Screenshot 2024-02-15 165320](https://github.com/sanjay5656/COLOR_CONVERSIONS_OF-IMAGE/assets/115128955/e7630202-3045-4b62-9d94-be8b0c517120)


### vi) BGR and RGB to HSV and GRAY
```
import cv2
img = cv2.imread('nebula.jpg',1)
img = cv2.resize(img,(300,200))
cv2.imshow('Original Image',img)

hsv1 = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('BGR2HSV',hsv1)

hsv2 = cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
cv2.imshow('RGB2HSV',hsv2)

gray1 = cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
cv2.imshow('BGR2GRAY',gray1)

gray2 = cv2.cvtColor(img,cv2.COLOR_RGB2GRAY)
cv2.imshow('RGB2GRAY',gray2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```

## Output:

![Screenshot 2024-02-15 165354](https://github.com/sanjay5656/COLOR_CONVERSIONS_OF-IMAGE/assets/115128955/9c6bf9bf-0370-4a06-ba03-23590b99a057)
![Screenshot 2024-02-15 165403](https://github.com/sanjay5656/COLOR_CONVERSIONS_OF-IMAGE/assets/115128955/4763d440-2b3c-4e03-9daa-cac962a2ac59)
![Screenshot 2024-02-15 165412](https://github.com/sanjay5656/COLOR_CONVERSIONS_OF-IMAGE/assets/115128955/1e266441-5a75-4cbf-815a-2d422d7ee1d9)
![Screenshot 2024-02-15 165422](https://github.com/sanjay5656/COLOR_CONVERSIONS_OF-IMAGE/assets/115128955/0c80db26-71fa-44d6-8df4-adbe4056f037)
![Screenshot 2024-02-15 165432](https://github.com/sanjay5656/COLOR_CONVERSIONS_OF-IMAGE/assets/115128955/366db048-8b73-4a99-a58b-2cca59d2d96f)


### vii) HSV to RGB and BGR
```
import cv2
img = cv2.imread('nebula.jpg')
img = cv2.resize(img,(300,200))

img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)

RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)

BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)

cv2.waitKey(0)
cv2.destroyAllWindows()
```

## Output:

![Screenshot 2024-02-15 165447](https://github.com/sanjay5656/COLOR_CONVERSIONS_OF-IMAGE/assets/115128955/ad30d758-c3b9-4fb2-a92e-26c462f562a2)
![Screenshot 2024-02-15 165459](https://github.com/sanjay5656/COLOR_CONVERSIONS_OF-IMAGE/assets/115128955/4e85acad-b8c3-4fbd-8c7d-0bd32a14116f)
![Screenshot 2024-02-15 165510](https://github.com/sanjay5656/COLOR_CONVERSIONS_OF-IMAGE/assets/115128955/4b755d9e-ff78-44fa-9b9e-ca2442a8dc06)

### viii) RGB and BGR to YCrCb
```
import cv2
img = cv2.imread('nebula.jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```

## Output:

![Screenshot 2024-02-15 165519](https://github.com/sanjay5656/COLOR_CONVERSIONS_OF-IMAGE/assets/115128955/b8bbf6f2-19fe-4396-9b58-bb0a1bf90e80)
![Screenshot 2024-02-15 165529](https://github.com/sanjay5656/COLOR_CONVERSIONS_OF-IMAGE/assets/115128955/3a5a7155-2ca6-4ae8-90d4-6780643057f6)
![Screenshot 2024-02-15 165540](https://github.com/sanjay5656/COLOR_CONVERSIONS_OF-IMAGE/assets/115128955/2dbfb8ca-39a1-495a-8262-09b74a9c775a)


### ix) Split and merge RGB Image
```
import cv2
img = cv2.imread('nebula.jpg',1)
img = cv2.resize(img,(300,200))

R = img[:,:,2]
G = img[:,:,1]
B = img[:,:,0]

cv2.imshow('R-Channel',R)
cv2.imshow('G-Channel',G)
cv2.imshow('B-Channel',B)

merged = cv2.merge((B,G,R))
cv2.imshow('Merged RGB image',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```

## Output:

![Screenshot 2024-02-15 165550](https://github.com/sanjay5656/COLOR_CONVERSIONS_OF-IMAGE/assets/115128955/5264daa8-85c5-425e-83bd-c6b050e0186b)
![Screenshot 2024-02-15 165558](https://github.com/sanjay5656/COLOR_CONVERSIONS_OF-IMAGE/assets/115128955/a930be83-7779-48ee-a29f-b7d2c0ad1e37)
![Screenshot 2024-02-15 165608](https://github.com/sanjay5656/COLOR_CONVERSIONS_OF-IMAGE/assets/115128955/08910bf8-9a80-445a-81f6-c592e38a5646)
![Screenshot 2024-02-15 165617](https://github.com/sanjay5656/COLOR_CONVERSIONS_OF-IMAGE/assets/115128955/76fca4a8-07f8-48d2-a50f-79d3aff68703)


### x) Split and merge HSV Image
```
import cv2
img = cv2.imread("nebula.jpg",1)
img = cv2.resize(img,(300,200))
img=cv2.cvtColor(img,cv2.COLOR_RGB2HSV)

H,S,V=cv2.split(img)

cv2.imshow('Hue',H)
cv2.imshow('Saturation',S)
cv2.imshow('Value',V)

merged = cv2.merge((H,S,V))
cv2.imshow('Merged',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```

## Output:

![Screenshot 2024-02-15 165626](https://github.com/sanjay5656/COLOR_CONVERSIONS_OF-IMAGE/assets/115128955/5b27640d-6cfb-4c02-8be7-08e148bffb97)
![Screenshot 2024-02-15 165633](https://github.com/sanjay5656/COLOR_CONVERSIONS_OF-IMAGE/assets/115128955/cc09ee82-1bfe-4a2b-9c7c-ded2f51cdf27)
![Screenshot 2024-02-15 165642](https://github.com/sanjay5656/COLOR_CONVERSIONS_OF-IMAGE/assets/115128955/0f4422fa-ddbe-427e-b606-b5ec11931475)
![Screenshot 2024-02-15 165649](https://github.com/sanjay5656/COLOR_CONVERSIONS_OF-IMAGE/assets/115128955/2398c13a-0aa7-4f11-99f0-d7b20aac9ea7)

## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







