
# What functions are used to read and display images &videos?
 - use `cv2.VideoCapture(src)` to create an instance of the video capturing to use further anywhere else in the code and `videoinstance.read()` is used to read a frame at a time so to read a whole video iterate through a while loop to read every frame.
- `cv2.imread(src)` -> for images.It returns a matrix of pixels.
- `cv2.imshow(window name, source)` to display an image or a frame of a video.
- `object.release()` where object can be a video capture object.
- `cv2.destroyAllWindows()` to destroy all the windows created to display the images and videos.
- `img.shape[1]`-> width and `img.shape[0]`-> height.
- To exit the video capturing window with keyboard use this code in while true loop :
```
if cv2.waitKey(20) & 0xFF==ord('q'):
    break
```
# How to resize an image or video?
- use `cv2.resize(frame, dimensions, interpolation)`  where dimensions are to which the frame needs to be resized. Interpolation refers to adding or removing pixels based on different methods like nearest neighbour or linear interpolation.
- For example, when increasing the scale of an image extra empty pixels are created to fill those empty pixels interpolation is used.
- `interpolation=cv.INTER_CUBIC`  results in a high quality image but rather a slow process compared to other methods for enlarging a image and `INTER_AREA` for shrinking an image.
- ![[Pasted image 20240511204306.png]]
- Linear Interpolation 
  ![[Pasted image 20240511204408.png]]
# How to draw shapes?
 - Rectangle use `cv2.rectangle(image,point1(start),point2(end),color,thickness)`
 - `thickness=-1` fills the shape with given color.
 - To create a blank image we can use `np.zeros((width, height,channels),dtype=uint8)`  where channels refer to number of channels to use while creating the blank image(black colour by default) 
 - Channel = 1->grey image,3->RGB image,4-> RGBA(a-alpha transparency)
 - Circle -> `cv2.circle(image,centre,radius,color.thickness`
 - Line-> `cv2.line(image,point1(start),point2(end),color,thickness)` 
 - Text -> `cv2.putText(image,text,origin(start position),font,size,color,thickness)`
# How to convert img to grey,blur,edge cascade,dilate,erode,crop?
- Grey scale image ->`cv2.cvtColor(img,cv2.COLOR_BGR2GRAY`
- Blur -> `cv2.GaussianBlur(img,kernelsize(should be odd number),sigmaX)` greater the kernel size greater the blur of the image.Generally `sigmaX=cv2.BORDER_DEFAULT
- *sigmaX:* Standard deviation of the Gaussian kernel in the X direction. If sigmaX is zero, it is calculated from the kernel size as sigmaX = 0.3 * ((ksize[0]-1) * 0.5 - 1) + 0.8.
- Gaussian blur is a low-pass filter, which means it removes high-frequency components from the image.
* The kernel size and standard deviation determine the amount of blurring applied. Larger kernel sizes and higher standard deviations result in more blurring.
* Gaussian blur is a computationally expensive operation, so it is not suitable for real-time applications.
- Edge cascade / canny -> `cv.canny(img,threshold1,threshold2)`  
  #Description:
	The function finds edges in an image using the Canny algorithm. The algorithm uses a multi-stage algorithm to detect a wide range of edges in images.

	The first stage of the algorithm computes the intensity gradients of the image in both the x and y directions using a Sobel operator. The Sobel operator is a 3x3 convolution kernel that is used to compute the gradient of an image. The gradient of an image is a vector that points in the direction of the greatest change in intensity.
	
	The second stage of the algorithm applies a threshold to the gradient image to identify strong and weak edges. Strong edges are those that have a gradient magnitude greater than the first threshold. Weak edges are those that have a gradient magnitude less than the first threshold but greater than the second threshold.
	
	The third stage of the algorithm uses a hysteresis procedure to connect strong edges and weak edges. The hysteresis procedure starts by finding all of the strong edges in the image. Then, for each strong edge, the procedure follows the edge in both directions until it reaches a weak edge. If the weak edge has a gradient magnitude greater than the second threshold, then the procedure continues to follow the edge. Otherwise, the procedure stops.
	
	The output of the Canny algorithm is a binary image that contains the edges of the input image. The edges are represented as white pixels on a black background

  
- `cv2.dilate(image,kernel,iterations)` it performs an operation to increase the saturation of white pixels in image.Iterations refers to number of times dilation need to performed on the image.
- `cv2.erode(img,kernel,iterations)` -> erosion is a operation that erodes away the boundaries of foreground objects. It is useful for removing noise and small objects from an image.
- `img[start:end(height),start:end(width)` results in cropping an image to the specified dimensions.

# How to translate,rotate,flip an image?
- Translate(moving an image)-> 
  code:
  `def translate(img,x,y):
    transMat = np.float32([[1,0,x],[0,1,y]])
    dimensions = (img.shape[1],img.shape[0])
    return cv.warpAffine(img, transMat, dimensions)`
	 -x -> left
	 x->right
	 y->down
	 -y->up
- Rotation -> to rotate an image we first need to get the required transformation matrix which we can get by `cv2.getRotationMatrix2D(rotation point,angle,scale)`.Then apply the  resultant transformation matrix on the image using `cv2.warpAffine(image,transformation Matrix,dimensions)`
- Flip -> `cv2.flip(source,flipcode)` 
  #flipcode:
  0 -> flipping the image vertically
  1 -> flipping the image horizontally
  -1 -> flipping the image in both planes.
# How to detect contours?
- To detect contours/edges-> `cv2.findContours(image,mode,method)` it returns two values the contours -> list of the coordinates of contours that has been detected and hierarchies of the detected contours.
- `cv2.threshold(image,threshold1,threshold2)` converts an image to binary image i.e any pixel gradient intensity less than threshold1 -> (0)black & any pixel gradient intensity is greater than threshold2->(1)white.
- `cv2.drawContours(image,contours,contouridx,color,thickness)` -> draws the contour on the image.To draw all the contours set `contouridx=-1` 

# How to split,merge channels of an image?
- Split -> `cv2.split(img)` returns three images in three channels i.e blue , green , red.This converts the specific color channel to white and the rest of colors to black.
- Merge -> `cv2.merge([3channels])` to merge three different channels of an image.
- To get an image in completely a single channel use a **blank image** as channels for the remaining two channels.
# What are different types of blur and kernels used?
- *Kernel Types:*
	cv2.blur() supports different kernel types, which determine the type of blur applied to the image:
	•	**Average Blur**: Each pixel in the output image is the average of all pixels within the kernel area.
	
	•	**Gaussian Blur**: Similar to average blur, but the kernel is weighted with a Gaussian distribution, resulting in a smoother blur.
	•	**Median Blur**: Each pixel in the output image is the median value of all pixels within the kernel area. This filter is effective in removing salt-and-pepper noise.
	•	**Bilateral Filter**: Combines average blur with edge-preserving smoothing. It helps preserve edges while blurring the image.
-   ***Example code***:
```
import cv2
import numpy as np

# Read an image
image = cv2.imread('image.jpg')

# Gaussian blur
gaussian_blur = cv2.GaussianBlur(image, (5, 5), 0)

# Median blur
median_blur = cv2.medianBlur(image, 5)

# Bilateral filter
bilateral_filter = cv2.bilateralFilter(image, 9, 75, 75)

# Show the original and blurred images
cv2.imshow('Original Image', image)
cv2.imshow('Gaussian Blur', gaussian_blur)
cv2.imshow('Median Blur', median_blur)
cv2.imshow('Bilateral Filter', bilateral_filter)

cv2.waitKey(0)
cv2.destroyAllWindows()
```

# What are bitwise operations in opencv?
- `cv2.bitwise_and(img1,img2)` -> results in intersection parts of two images.
- `cv2.bitwise_or(img1,img2)` -> results in union parts of two images.
- `cv2.bitwise_XOR(img1,img2)` -> results in non intersection parts of the image.
- ![[Pasted image 20240512124318.png]]
- `cv2.bitwsie_not(src)` -> inverts the binary colors of the image i.e black -> white & white -> black.
# How to perform masking on image in opencv?
# How to do hand tracking in opencv?
-  **must include code**: 
```
import cv2
mpHands = mp.solutions.hands
hands = mpHands.hands(False,no.of hands)
mpDraw = mp.solutions.drawing_utils
```
- ![[Hand Tracking Python.png]] here the numbers represent the id returned by any landmark from handlandmark of b multi_hand_landmarks list.
- 