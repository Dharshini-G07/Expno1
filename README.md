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

# Load image
img = cv2.imread('Qno. 1.jpg')

if img is None:
    print("Image not found. Check the file name and folder.")
else:
    print("Original image shape:", img.shape)

    # Convert BGR to RGB
    img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

    # Display original image
    plt.figure()
    plt.imshow(img_rgb)
    plt.title("Original Image")
    plt.axis('off')
    plt.show()

    # Draw line
    line_img = img_rgb.copy()
    cv2.line(line_img, (0, 0), (min(768, img.shape[1]-1), min(600, img.shape[0]-1)), (255, 0, 0), 2)

    plt.figure()
    plt.imshow(line_img)
    plt.title("Image with Line")
    plt.axis('off')
    plt.show()

    # Draw circle
    circle_img = img_rgb.copy()
    center = (img.shape[1]//2, img.shape[0]//2)
    cv2.circle(circle_img, center, min(150, img.shape[1]//2, img.shape[0]//2), (255, 0, 0), 10)

    plt.figure()
    plt.imshow(circle_img)
    plt.title("Image with Circle")
    plt.axis('off')
    plt.show()

    # Draw rectangle
    rectangle_img = img_rgb.copy()
    cv2.rectangle(rectangle_img, (0, 0), (img.shape[1]-1, img.shape[0]-1), (0, 0, 255), 10)

    plt.figure()
    plt.imshow(rectangle_img)
    plt.title("Image with Rectangle")
    plt.axis('off')
    plt.show()

    # Add text
    text_img = img_rgb.copy()
    cv2.putText(text_img, "OpenCV Drawing", (10, 40),
                cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 2)

    plt.figure()
    plt.imshow(text_img)
    plt.title("Image with Text")
    plt.axis('off')
    plt.show()

    # HSV color space
    image_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
    plt.figure()
    plt.imshow(cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB))
    plt.title("HSV Image")
    plt.axis('off')
    plt.show()

    # Grayscale image
    image_gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
    plt.figure()
    plt.imshow(image_gray, cmap='gray')
    plt.title("Grayscale Image")
    plt.axis('off')
    plt.show()

    # YCrCb color space
    image_ycrcb = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
    plt.figure()
    plt.imshow(cv2.cvtColor(image_ycrcb, cv2.COLOR_YCrCb2RGB))
    plt.title("YCrCb Image")
    plt.axis('off')
    plt.show()

    # Add a white block
    white_img = img.copy()
    h, w = white_img.shape[:2]
    white_img[200:min(500, h), 200:min(500, w)] = [255, 255, 255]
    plt.figure()
    plt.imshow(cv2.cvtColor(white_img, cv2.COLOR_BGR2RGB))
    plt.title("Image with White Block")
    plt.axis('off')
    plt.show()

    # Resize image
    resized_image = cv2.resize(img, (img.shape[1]//2, img.shape[0]//2))
    plt.figure()
    plt.imshow(cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB))
    plt.title("Resized Image (Half Size)")
    plt.axis('off')
    plt.show()

    # Crop region of interest
    roi = img[50:min(350, img.shape[0]), 50:min(350, img.shape[1])]
    if roi.size > 0:
        plt.figure()
        plt.imshow(cv2.cvtColor(roi, cv2.COLOR_BGR2RGB))
        plt.title("Cropped Region of Interest (ROI)")
        plt.axis('off')
        plt.show()

    # Flip horizontally
    flipped_horizontally = cv2.flip(img, 1)
    plt.figure()
    plt.imshow(cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB))
    plt.title("Flipped Horizontally")
    plt.axis('off')
    plt.show()

    # Flip vertically
    flipped_vertically = cv2.flip(img, 0)
    plt.figure()
    plt.imshow(cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB))
    plt.title("Flipped Vertically")
    plt.axis('off')
    plt.show()

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
