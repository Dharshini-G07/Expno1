## Image-Handling-and-Pixel-Transformations-Using-OpenCV
## AIM:
Write a Python program using OpenCV that performs the following tasks:
```
 1.Read and Display an Image.
 2.Adjust the brightness of an image.
 3.Modify the image contrast.
 4.Generate a third image using bitwise operations.
```

## Software Required:
Anaconda - Python 3.7
Jupyter Notebook (for interactive development and execution)

## Algorithm:
Step 1:
Load an image from your local directory and display it.

Step 2:
Create a matrix of ones (with data type float64) to adjust brightness.

Step 3:
Create brighter and darker images by adding and subtracting the matrix from the original image.
Display the original, brighter, and darker images.

Step 4:
Modify the image contrast by creating two higher contrast images using scaling factors of 1.1 and 1.2 (without overflow fix).
Display the original, lower contrast, and higher contrast images.

Step 5:
Split the image (boy.jpg) into B, G, R components and display the channels

## Program Developed By:
Name: Priyadharshini G

Register Number: 212224230209

## Ex. No. 01

```
import cv2
import matplotlib.pyplot as plt
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()
image = cv2.imread('Qno. 1.jpg') 
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
line_img = cv2.line(img_rgb, (0, 0), (768, 600), (255, 0, 0), 2) # cv2.line(image, start_point, end_point, color, thickness)
plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('off')  
plt.show()

image = cv2.imread('Qno. 1.jpg') 

img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
circle_img = cv2.circle(img_rgb,(400,300),150,(255,0,0),10) # cv2.circle(image, center, radius, color, thickness)
plt.imshow(circle_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('off')  
plt.show()

image = cv2.imread('Qno. 1.jpg') 

img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img.shape

rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 0, 255), 10)  # cv2.rectangle(image, start_point, end_point, color, thickness)

plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()

image = cv2.imread('Qno. 1.jpg') 

img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB) 

text_img = cv2.putText(img_rgb, "OpenCV Drawing", (10, 30), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 10)  ## cv2.putText(image, text, position, font, font_scale, color, thickness)

plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()

image = cv2.imread('Qno. 1.jpg') 
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")

image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)

plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")

image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)

plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")

image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)

plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")

image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")

image[200:500, 200:500] = [255, 255, 255]  # Rows: 200-499, Columns: 200-499

image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()

image = cv2.imread('Qno. 1.jpg') 
image.shape

resized_image = cv2.resize(image, (768 // 2, 600 // 2))  # (new_width, new_height)

resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)
resized_image_rgb.shape

plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()

image = cv2.imread('Qno. 1.jpg') 
image.shape

roi = image[50:350, 50:350]  # Rows: 50-349, Columns: 50-349

roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)

plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()

image = cv2.imread('Qno. 1.jpg') 

flipped_horizontally = cv2.flip(image, 1)

flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)

plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")

flipped_vertically = cv2.flip(image, 0)

flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)

plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
```


## Output:
i) Read and Display an Image.
ii) Adjust Image Brightness.
iii) Modify Image Contrast.
iv) Generate Third Image Using Bitwise Operations.


<img width="233" height="417" alt="image" src="https://github.com/user-attachments/assets/136afd20-de47-4a90-b332-12370e6633d0" />

<img width="263" height="425" alt="image" src="https://github.com/user-attachments/assets/c48693c9-ad7d-4ec4-8234-036bed58371f" />

<img width="225" height="412" alt="image" src="https://github.com/user-attachments/assets/a9cefe2a-f727-436e-b114-ef8bdfdbf7ec" />

<img width="233" height="409" alt="image" src="https://github.com/user-attachments/assets/9362e29d-dced-4b70-a210-d9a8dddfd443" />

<img width="242" height="412" alt="image" src="https://github.com/user-attachments/assets/041174d8-9bcf-4973-bcd5-78cc666d517c" />

<img width="600" height="441" alt="image" src="https://github.com/user-attachments/assets/5580439e-ef7d-4ee3-9d40-60685c0e231c" />

<img width="585" height="438" alt="image" src="https://github.com/user-attachments/assets/7e451269-d44f-49f8-99cf-befa214605e8" />

<img width="605" height="438" alt="image" src="https://github.com/user-attachments/assets/1510aea7-e7a8-401d-90e1-51dc2358eaed" />

<img width="663" height="434" alt="image" src="https://github.com/user-attachments/assets/699b3134-9795-452f-bcf3-4a0b617619ae" />

<img width="543" height="428" alt="image" src="https://github.com/user-attachments/assets/1414e191-de29-4e71-93c6-6d43bb281601" />

<img width="322" height="397" alt="image" src="https://github.com/user-attachments/assets/80d3caea-7edc-4874-b3ce-80ed097eb378" />

<img width="509" height="418" alt="image" src="https://github.com/user-attachments/assets/69680a2e-63c1-412f-a392-100291d61e8a" />

<img width="404" height="416" alt="image" src="https://github.com/user-attachments/assets/15c374d8-a84c-46b1-9b91-b59815270d00" />

<img width="550" height="438" alt="image" src="https://github.com/user-attachments/assets/9321e8c4-7690-417f-be1f-367fe27c2dea" />

<img width="547" height="432" alt="image" src="https://github.com/user-attachments/assets/566c334e-c554-4423-88d1-92f91b1d4500" />




## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.
