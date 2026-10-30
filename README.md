
# EXP. 01 – IMAGE HANDLING AND PIXEL TRANSFORMATION USING OpenCV

## NAME: NIKILA D
## REG.NO: 212224230187

## AIM
Write a Python program using OpenCV that performs the following tasks:

1. Read and display an image.
2. Adjust the brightness of an image.
3. Modify the image contrast.
4. Generate a third image using bitwise operations.

## Software Required
- Anaconda - Python 3.7
- Jupyter Notebook

## Algorithm

# Step 1:
Load an image from your local directory and display it.

# Step 2:
Create a matrix of ones with data type `float64` to adjust brightness.

# Step 3:
Create brighter and darker images by adding and subtracting the matrix from the original image. Display all three images.

# Step 4:
Modify image contrast using scaling factors of 1.1 and 1.2. Display the original and contrast-adjusted images.

# Step 5:
Split the image (`Image.png`) into B, G, R components and display the channels.

---

## 1. Import the Required Libraries

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

## 2. Read and Display the Original Image

```python
img = cv2.imread('Image.png', cv2.IMREAD_COLOR)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

plt.imshow(img_rgb)
plt.title("Original Image")
plt.axis('off')
plt.show()
```


## OUTPUT:
<img width="757" height="562" alt="image" src="https://github.com/user-attachments/assets/cc6b8078-7fc3-4e16-a376-725879f48d30" />

## 3. Print Image Width, Height and Channels

```python
height, width, channels = img.shape

print("Image Width:", width)
print("Image Height:", height)
print("Image Channels:", channels)
print("Image Shape:", img.shape)
```

## 4. Draw a Line from Top-Left to Bottom-Right

```python
line_img = cv2.line(img_rgb.copy(), (0, 0), (768, 600), (255, 165, 0), 9)

plt.imshow(line_img)
plt.title("Image with Line")
plt.axis('off')
plt.show()
```

## OUTPUT:
<img width="527" height="585" alt="image" src="https://github.com/user-attachments/assets/6b5803c1-9588-45bb-a864-d0ba03b9086f" />


## 5. Draw a Circle on the Image

```python
circle_img = cv2.circle(img_rgb.copy(), (400, 300), 150, (255, 165, 0), 10)

plt.imshow(circle_img)
plt.title("Image with Circle")
plt.axis('off')
plt.show()
```

## OUTPUT:
<img width="802" height="570" alt="image" src="https://github.com/user-attachments/assets/486d5d65-c9f3-4213-ba61-930d31f885a8" />

## 6. Draw a Rectangle Around the Image

```python
rectangle_img = cv2.rectangle(img_rgb.copy(), (0, 0), (768, 600), (255, 165, 0), 10)

plt.imshow(rectangle_img)
plt.title("Image with Rectangle")
plt.axis('off')
plt.show()
```

##OUTPUT:
<img width="596" height="580" alt="image" src="https://github.com/user-attachments/assets/3ded8f81-a990-4cdd-bc8f-e2832fcf6f60" />

## 7. Add Text to the Image

```python
text_img = cv2.putText(
    img_rgb.copy(), "Nikila", (100, 100),
    cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 165, 0), 10
)

plt.imshow(text_img)
plt.title("Image with Text")
plt.axis('off')
plt.show()
```
## OUTPUT:
<img width="586" height="565" alt="image" src="https://github.com/user-attachments/assets/22310ded-44b8-47d5-b9c6-502da676654a" />

## 8. Save the Image as a PNG File

```python
cv2.imwrite('Output.png', img)
```

## 9. Read the Saved Image and Convert it to Grayscale

```python
image = cv2.imread('Output.png')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)

plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
plt.show()
```
## OUTPUT:
<img width="522" height="555" alt="image" src="https://github.com/user-attachments/assets/b2eeff27-6247-4f0f-9287-14da70f44395" />


## 10. Display the Original RGB Image

```python
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")
plt.show()
```

## OUTPUT:
<img width="720" height="565" alt="image" src="https://github.com/user-attachments/assets/8c13d220-5888-4098-904a-c0c67a2576e6" />


## 11. Convert RGB Image to HSV

```python
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)

plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
plt.show()
```
## OUTPUT:
<img width="485" height="562" alt="image" src="https://github.com/user-attachments/assets/3dde990f-a9e4-46fb-a058-a77ae7bf593a" />

## 12. Convert RGB Image to YCrCb

```python
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)

plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
plt.show()
```
## OUTPUT:
<img width="408" height="557" alt="image" src="https://github.com/user-attachments/assets/05d3562c-28ec-4f87-a04f-b81bdbfe0d66" />

## 13. Convert HSV Back to RGB

```python
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)

plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
plt.show()
```
## OUTPUT:
<img width="501" height="558" alt="image" src="https://github.com/user-attachments/assets/9a0cce78-b799-4b75-81ea-03543e37876f" />

## 14. Modify a Block of Pixels to White

```python
image = cv2.imread('Image.png')
image[200:500, 200:500] = [255, 255, 255]

image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()
```
## OUTPUT:
<img width="488" height="565" alt="image" src="https://github.com/user-attachments/assets/6c7177e6-08a7-4db9-b7ba-dd78ff7cc7f7" />

## 15. Resize the Image to Half its Size

```python
image = cv2.imread('Image.png')
resized_image = cv2.resize(image, (768 // 2, 600 // 2))

resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)

print("Resized Image Shape:", resized_image_rgb.shape)

plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()
```
## OUTPUT:
<img width="778" height="562" alt="image" src="https://github.com/user-attachments/assets/27981074-1c8e-4e63-9f77-f59f00f0ab4e" />

## 16. Crop a Specific Region of the Image

```python
image = cv2.imread('Image.png')
roi = image[50:350, 50:350]

roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)

plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()
```
## OUTPUT:
<img width="581" height="568" alt="image" src="https://github.com/user-attachments/assets/4d867ee0-17c1-49b7-b1ce-8d860f23ea3a" />

## 17. Flip the Image Horizontally

```python
image = cv2.imread('Image.png')
flipped_horizontally = cv2.flip(image, 1)

flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)

plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
plt.show()
```
## OUTPUT:
<img width="402" height="547" alt="image" src="https://github.com/user-attachments/assets/6a3d0e6f-b3b5-4368-8e6c-ce9d79317af7" />

## 18. Flip the Image Vertically

```python
flipped_vertically = cv2.flip(image, 0)

flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)

plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
plt.show()
```
## OUTPUT:
<img width="483" height="545" alt="image" src="https://github.com/user-attachments/assets/c7fbfff6-e1b4-4404-9d58-9586a4ec9a9f" />

## Result

Thus, the images were read and displayed, brightness and contrast adjustments were made, colour channels were split and merged, and bitwise operations were performed successfully using Python and OpenCV.
