# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import necessary libraries such as OpenCV, NumPy, and Matplotlib for image processing and visualization.

### Step2:

Read the input image using cv2.imread() and store it in a variable for further processing.


### Step3:

Apply various transformations like translation, scaling, shearing, reflection, rotation, and cropping by defining corresponding functions:

1.Translation moves the image along the x or y-axis.
2.Scaling resizes the image by scaling factors.
3.Shearing distorts the image along one axis.
4.Reflection flips the image horizontally or vertically.
5.Rotation rotates the image by a given angle.

### Step4:
Display the transformed images using Matplotlib for visualization. Convert the BGR image to RGB format to ensure proper color representation.

### Step5:
Save or display the final transformed images for analysis and use plt.show() to display them inline in Jupyter or compatible environments.


## Program:
### Developed By:DEEPIKA R
### Register Number:212223230038
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Load the image
image = cv2.imread('/content/flower.jpg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)  # Convert BGR to RGB for Matplotlib

# 1. Image Translation
rows, cols, _ = image.shape
M_translate = np.float32([[1, 0, 50], [0, 1, 100]])  # Translate by (50, 100) pixels
translated_image = cv2.warpAffine(image_rgb, M_translate, (cols, rows))

# 2. Image Scaling
scaled_image = cv2.resize(image_rgb, None, fx=1.5, fy=1.5, interpolation=cv2.INTER_LINEAR)  # Scale by 1.5x

# 3. Image Shearing
M_shear = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  # Shear with factor 0.5
sheared_image = cv2.warpAffine(image_rgb, M_shear, (int(cols * 1.5), int(rows * 1.5)))

# 4. Image Reflection (Flip)
reflected_image = cv2.flip(image_rgb, 1)  # Horizontal reflection (flip along y-axis)

# 5. Image Rotation
M_rotate = cv2.getRotationMatrix2D((cols / 2, rows / 2), 45, 1)  # Rotate by 45 degrees
rotated_image = cv2.warpAffine(image_rgb, M_rotate, (cols, rows))

# 6. Image Cropping
cropped_image = image_rgb[50:300, 100:400]  # Crop a portion of the image

# Plot the original and transformed images
plt.figure(figsize=(12, 8))

plt.subplot(2, 3, 1)
plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis('off')

plt.subplot(2, 3, 2)
plt.imshow(translated_image)
plt.title("Translated Image")
plt.axis('off')

plt.subplot(2, 3, 3)
plt.imshow(scaled_image)
plt.title("Scaled Image")
plt.axis('off')

plt.subplot(2, 3, 4)
plt.imshow(sheared_image)
plt.title("Sheared Image")
plt.axis('off')

plt.subplot(2, 3, 5)
plt.imshow(reflected_image)
plt.title("Reflected Image")
plt.axis('off')

plt.subplot(2, 3, 6)
plt.imshow(rotated_image)
plt.title("Rotated Image")
plt.axis('off')

plt.tight_layout()
plt.show()

# Plot cropped image separately as its aspect ratio may be different
plt.figure(figsize=(4, 4))
plt.imshow(cropped_image)
plt.title("Cropped Image")
plt.axis('off')
plt.show()

```
## Output:
<img width="599" height="230" alt="Screenshot 2025-09-02 160621" src="https://github.com/user-attachments/assets/f5d7c2ca-e24a-48a8-b6f5-aecfafb0d93c" />
<img width="583" height="377" alt="Screenshot 2025-09-02 160611" src="https://github.com/user-attachments/assets/206a3416-a2e2-47cd-9bd8-8923144a4431" />
<img width="600" height="381" alt="Screenshot 2025-09-02 160551" src="https://github.com/user-attachments/assets/5d7ee83e-37c4-47ff-9e2f-c0241889e6d8" />
<img width="615" height="374" alt="Screenshot 2025-09-02 160537" src="https://github.com/user-attachments/assets/7ee6b676-8331-4311-b2a7-2c595c5b4610" />
<img width="590" height="178" alt="Screenshot 2025-09-02 160520" src="https://github.com/user-attachments/assets/1702df64-c113-418a-bf90-11205fbb0075" />
<img width="596" height="376" alt="Screenshot 2025-09-02 160507" src="https://github.com/user-attachments/assets/fc873891-756b-47cd-a49e-7b78c7daf4c3" />
<img width="585" height="372" alt="Screenshot 2025-09-02 160454" src="https://github.com/user-attachments/assets/a5345e5c-9952-46ef-b8f2-dfc306df810c" />
<img width="599" height="230" alt="Screenshot 2025-09-02 160621" src="https://github.com/user-attachments/assets/9ab7420e-186a-4245-8d5d-0d9324b6b9e6" />

## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
