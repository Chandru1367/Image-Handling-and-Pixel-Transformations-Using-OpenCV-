# Experiment 1: Image Handling and Pixel Transformations Using OpenCV

**Name:** Chandru M

**Register Number:** 212224230041  

**Experiment:** Image Handling and Pixel Transformations Using OpenCV

---

## AIM

To perform image handling and pixel transformations using Python and OpenCV, including reading and displaying images, drawing shapes, adding text, color space conversion, pixel manipulation, image resizing, cropping, flipping, and saving the modified image.

## SOFTWARE REQUIRED

- Python
- OpenCV
- Matplotlib
- Jupyter Notebook
- Anaconda (optional)

## INSTALLATION

Install the required libraries using the following command:

```bash
pip install opencv-contrib-python-headless matplotlib
```

## ALGORITHM

### Step 1: Read and Display an Image

1. Import OpenCV and Matplotlib libraries.
2. Read an image from the local directory using `cv2.imread()`.
3. Convert the image from BGR to RGB.
4. Display the original image using Matplotlib.

### Step 2: Draw Shapes and Add Text

1. Draw a line from the top-left to the bottom-right of the image.
2. Draw a circle at the center of the image.
3. Draw a rectangle around the image.
4. Add the text "OpenCV Drawing" at the top-left corner.

### Step 3: Color Space Conversion

1. Convert the RGB image to HSV and display it.
2. Convert the RGB image to grayscale and display it.
3. Convert the RGB image to YCrCb and display it.
4. Convert the HSV image back to RGB and display it.

### Step 4: Pixel Manipulation

1. Access and print the pixel value at coordinates `(100, 100)`.
2. Change the pixel at coordinates `(200, 200)` to white.
3. Modify a 300 × 300 region of the image to white.
4. Display the modified image.

### Step 5: Image Resizing

1. Read the original image.
2. Resize the image to half its original width and height.
3. Display the resized image.

### Step 6: Image Cropping

1. Read the original image.
2. Extract a 300 × 300 region of interest starting at `(50, 50)`.
3. Display the cropped image.

### Step 7: Image Flipping

1. Flip the original image horizontally.
2. Flip the original image vertically.
3. Display both flipped images.

### Step 8: Save the Final Modified Image

1. Save the modified image in the local directory using `cv2.imwrite()`.
2. Verify that the image has been saved successfully.

---

## PROGRAM

### Step 1: Read and Display an Image

```python
import cv2
import matplotlib.pyplot as plt

# Read the image using OpenCV
img = cv2.imread(r"E:\College\1746517967557.jpg", cv2.IMREAD_COLOR)

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

# Display the image using Matplotlib
plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()
```

### Step 2: Draw Shapes and Add Text

#### 2.1 Draw a Line

```python
# Load the image
image = cv2.imread(r"E:\College\1746517967557.jpg")

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

img_rgb.shape

# Draw a line from top-left to bottom-right
line_img = cv2.line(img_rgb, (0, 0), (768, 600), (255, 0, 0), 2) # cv2.line(image, start_point, end_point, color, thickness)

plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('off')  
plt.show()
```

#### 2.2 Draw a Circle

```python
# Load the image
image = cv2.imread(r"E:\College\1746517967557.jpg") 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

img_rgb.shape

circle_img = cv2.circle(img_rgb,(400,300),150,(255,0,0),10) # cv2.circle(image, center, radius, color, thickness)

plt.imshow(circle_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('off')  
plt.show()
```

#### 2.3 Draw a Rectangle

```python
# Load the image
image = cv2.imread(r"E:\College\1746517967557.jpg") 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

img.shape

# Draw a rectangle around the Whole image
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 0, 255), 10)  # cv2.rectangle(image, start_point, end_point, color, thickness)

plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()
```

#### 2.4 Add Text to the Image

```python
# Load the image
image = cv2.imread(r"E:\College\1746517967557.jpg") 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

# Add text to the image
text_img = cv2.putText(img_rgb, "CHANDRU", (100, 200), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 0, 255), 10)  ## cv2.putText(image, text, position, font, font_scale, color, thickness)

plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()
```

### Step 3: Color Space Conversion

```python
# Load the image
image = cv2.imread(r"E:\College\1746517967557.jpg")

image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

# Original RGB Image
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")

# Convert RGB to HSV
image = cv2.imread(r"E:\College\1746517967557.jpg") 
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)

# HSV Image
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")

# Convert RGB to GRAY
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)

# Grayscale Image
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")

# Convert RGB to YCrCb
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)

# YCrCb Image
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")

# Convert HSV back to RGB
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)

plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")


```

### Step 4: Pixel Manipulation

```python
# Modify a block of pixels (300x300) to white, starting from (200, 200)
image[200:500, 200:500] = [255, 255, 255]  # Rows: 200-499, Columns: 200-499

# Convert BGR to RGB for displaying with Matplotlib
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

# Display the modified image
plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()
```

### Step 5: Image Resizing

```python
# Load the image
image = cv2.imread(r"E:\College\1746517967557.jpg")

image.shape

# Resize the image to half its size
resized_image = cv2.resize(image, (768 // 2, 600 // 2))  # (new_width, new_height)

# Convert BGR to RGB for displaying with Matplotlib
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)

resized_image_rgb.shape

# Display the resized image
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()
```

### Step 6: Image Cropping

```python
# Load the image
image = cv2.imread(r"E:\College\1746517967557.jpg")

image.shape

# Crop a 300x300 region starting from (50, 50)
roi = image[50:350, 50:350]  # Rows: 50-349, Columns: 50-349

# Convert BGR to RGB for displaying with Matplotlib
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)

# Display the cropped region (ROI)
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()
```

### Step 7: Image Flipping

```python
# Load the image
image = cv2.imread(r"E:\College\1746517967557.jpg")

# Flip the image horizontally (left-right)
flipped_horizontally = cv2.flip(image, 1)

# Convert BGR to RGB for displaying with Matplotlib
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)

# Horizontal flip
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")

# Flip the image vertically (up-down)
flipped_vertically = cv2.flip(image, 0)

# Convert BGR to RGB for displaying with Matplotlib
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)

# Vertical flip
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
```


## OUTPUT

## The following outputs are obtained:

## 1. Original image displayed using OpenCV and Matplotlib.


<img width="268" height="410" alt="download" src="https://github.com/user-attachments/assets/17498e20-5339-4173-b2f1-b611b3c35581" />



## 2. Image with a line drawn from the top-left to the bottom-right.

<img width="268" height="410" alt="download" src="https://github.com/user-attachments/assets/6e335152-aa27-4ae1-8e87-414bfa5dd1e1" />



## 3. Image with a circle at the center.

<img width="268" height="410" alt="download" src="https://github.com/user-attachments/assets/288028d5-93d0-4d7f-b3e3-8df2bd88067b" />



## 4. Image with a rectangle around its boundary.

<img width="268" height="410" alt="download" src="https://github.com/user-attachments/assets/a6da6c35-1186-4cde-a695-6926163ac3a6" />


## 5. Image with the text "OpenCV Drawing".

<img width="268" height="410" alt="download" src="https://github.com/user-attachments/assets/53748a6c-b47d-4fd7-b83b-f73ccafeed0b" />



## 6. HSV, grayscale, and YCrCb color space conversions.


<img width="268" height="410" alt="download" src="https://github.com/user-attachments/assets/5e6e9b47-6517-4abb-a938-31a0ad0e2781" />


<img width="268" height="410" alt="download" src="https://github.com/user-attachments/assets/8c45267f-5e5f-459a-aabb-135743ed0583" />


<img width="268" height="410" alt="download" src="https://github.com/user-attachments/assets/001dd14a-f0c0-4928-975f-452a88ddd615" />

<img width="268" height="410" alt="download" src="https://github.com/user-attachments/assets/62c0a538-ba61-4054-b8d3-bd48917efa15" />


## 7. Image converted from HSV back to RGB.

<img width="268" height="410" alt="download" src="https://github.com/user-attachments/assets/ab9a0f14-3fd7-4236-b045-4f860af4bd48" />


## 8. Pixel value displayed and a white region added to the image.

<img width="302" height="410" alt="download" src="https://github.com/user-attachments/assets/5d1fbb87-1ad2-4679-8da6-0ac84a8cdd2e" />


## 9. Image resized to half its original dimensions.


<img width="493" height="410" alt="download" src="https://github.com/user-attachments/assets/cd539961-4bcc-4f07-867c-80d4adaf3dd5" />



## 10. Cropped region of interest displayed.

<img width="389" height="410" alt="download" src="https://github.com/user-attachments/assets/9dd3681a-03c7-4628-8718-862090a2e728" />



## 11. Horizontally flipped image displayed.

<img width="268" height="410" alt="download" src="https://github.com/user-attachments/assets/cc83839c-8eb1-483c-9e0c-f41bf572b7e2" />


## 12. Vertically flipped image displayed.

<img width="268" height="410" alt="download" src="https://github.com/user-attachments/assets/0c24b391-96fd-4644-94c2-d7d40ab14e59" />



## RESULT

Thus, image handling and pixel transformations were performed using Python, OpenCV, and Matplotlib. The experiment demonstrated image reading, shape drawing, text insertion, color space conversion, pixel manipulation, image resizing, cropping, flipping, and saving.

