# EXP-1-Image-Handling-and-Pixel-Transformations-Using-OpenCV
# Aim:

To perform basic image handling and pixel transformation operations using OpenCV in Python, including loading an image, displaying it, drawing shapes, adding text, resizing, rotating, flipping, cropping, and saving the modified image.
# Software Required:
Anaconda - Python 3.7

Jupyter Notebook (for interactive development and execution)
# Algorithm:
Step1:

Load an image from your local directory and display it.

Step2:

o Draw a line from the top-left to the bottom-right of the image.

o Draw a circle at the center of the image. 

o Draw a rectangle around a specific region of interest in the image. 

o Add the text "OpenCV Drawing" at the top-left corner of the image.

Step3:

o Convert the image from RGB to HSV and display it.
    
o Convert the image from RGB to GRAY and display it. 

o Convert the image from RGB to YCrCb and display it. 
    
o Convert the HSV image back to RGB and display it.

Step4:

o Access and print the value of the pixel at coordinates (100, 100). 

o Modify the color of the pixel at (200, 200) to white.

Step5:

o Resize the original image to half its size and display it.

Step6:

o Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.

Step7:

o Flip the original image horizontally and display it. 

o Flip the original image vertically and display it.

Step8:

o Save the final modified image to your local directory.

# Program:
```
import cv2
import matplotlib.pyplot as plt
# Read the image using OpenCV
img = cv2.imread('mur.jpg', cv2.IMREAD_COLOR)
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
# Display the image using Matplotlib
plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('on')  # Removes axis ticks and labels
plt.show()
```
<img width="1347" height="802" alt="image" src="https://github.com/user-attachments/assets/838854c8-bcdf-483c-a144-f3fddc301c51" />



```
# Load the image
image = cv2.imread('mur.jpg')
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
# Draw a line from top-left to bottom-right
line_img = cv2.line(img_rgb, (0, 0), (800, 1085), (0, 255, 255), 10) # cv2.line(image, start_point, end_point, color, thickness)
plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('on')  
plt.show()
```
<img width="1338" height="867" alt="image" src="https://github.com/user-attachments/assets/4b596333-9e2d-446c-ba53-80df262e51a7" />



```
# Load the image
image = cv2.imread('mur.jpg') 
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
circle_img = cv2.circle(img_rgb,(200,200),150,(255,0,0),10) # cv2.circle(image, center, radius, color, thickness)
plt.imshow(circle_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('on')  
plt.show()
```
<img width="1325" height="842" alt="image" src="https://github.com/user-attachments/assets/8f622e7b-1fb2-464b-8a00-39b7753faaba" />



```
# Load the image
image = cv2.imread('mur.jpg') 
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img.shape
# Draw a rectangle around the Whole image
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (390,515), (0, 0, 255), 10)  # cv2.rectangle(image, start_point, end_point, color, thickness)
plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('on')  
plt.show()
```
<img width="1332" height="872" alt="image" src="https://github.com/user-attachments/assets/3e5685a4-371e-4e09-8e9c-ae813ba6ab47" />



```
# Load the image
image = cv2.imread('mur.jpg') 
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
# Add text to the image
text_img = cv2.putText(img_rgb, "PUGAZH", (10, 30), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 10)  ## cv2.putText(image, text, position, font, font_scale, color, thickness)
plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('on')  
plt.show()
```
<img width="1315" height="816" alt="image" src="https://github.com/user-attachments/assets/5605d948-6625-465c-845e-de30c8d27c49" />



```
# Load the image
image = cv2.imread('mur.jpg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
# Original RGB Image
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")
```
<img width="1348" height="705" alt="image" src="https://github.com/user-attachments/assets/cc9c8cb9-bf57-4539-9690-72bd8b190c91" />



```
# Convert RGB to HSV
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)
# HSV Image
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
```
<img width="1361" height="672" alt="image" src="https://github.com/user-attachments/assets/760534db-9caa-4037-9442-14c3cd1aa7b0" />



```
# Convert RGB to GRAY
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)
# Grayscale Image
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
```
<img width="1350" height="673" alt="image" src="https://github.com/user-attachments/assets/b9d72d25-f68b-4502-abc5-5fa405c7a9e1" />



```
# Convert RGB to YCrCb
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)
# YCrCb Image
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
```
<img width="1352" height="672" alt="image" src="https://github.com/user-attachments/assets/cd87a3bd-be02-4c38-bee6-cb1ac0be11c6" />



```
# Convert HSV back to RGB
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
```
<img width="1361" height="661" alt="image" src="https://github.com/user-attachments/assets/73de8c2c-f7f3-499d-aeb5-4e3aa2c813af" />



```
# Modify a block of pixels (300x300) to white, starting from (200, 200)
image[100:300, 100:300] = [255, 255, 255]  # Rows: 200-499, Columns: 200-499
# Convert BGR to RGB for displaying with Matplotlib
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
# Display the modified image
plt.imshow(image_rgb)
plt.title("Image with 100x100 White Block")
plt.axis("on")
plt.show()
```
<img width="1331" height="733" alt="image" src="https://github.com/user-attachments/assets/80696e42-eb63-4216-ad71-a1e8643df86c" />



```
# Load the image
image = cv2.imread('mur.jpg')
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
<img width="1340" height="937" alt="image" src="https://github.com/user-attachments/assets/07dddd0d-fc67-48a5-a671-854222e1772b" />



```
# Load the image
image = cv2.imread('mur.jpg')
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
<img width="1325" height="862" alt="image" src="https://github.com/user-attachments/assets/a4a58121-21a1-4533-bcf0-6641ab9258eb" />



```
# Load the image
image = cv2.imread('mur.jpg') 
# Flip the image horizontally (left-right)
flipped_horizontally = cv2.flip(image, 1)
# Convert BGR to RGB for displaying with Matplotlib
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)
# Horizontal flip
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
```
<img width="1332" height="791" alt="image" src="https://github.com/user-attachments/assets/05dc74d9-d6a4-4418-8dad-8f617fd0c927" />



```
# Flip the image vertically (up-down)
flipped_vertically = cv2.flip(image, 0)
# Convert BGR to RGB for displaying with Matplotlib
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)
# Vertical flip
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
```
<img width="1426" height="733" alt="image" src="https://github.com/user-attachments/assets/e2ab24fc-06e9-471d-bc13-480cd76fdcff" />

# Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.
