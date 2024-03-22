# IMAGE-TRANSFORMATIONS

## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step 1: 
Import numpy module as np and pandas as pd.
### Step 2: 
Assign the values to variables in the program.
### Step 3: 
Get the values from the user appropriately.
### Step 4: 
Continue the program by implementing the codes of required topics.
### Step 5: 
Thus the program is executed in google colab.

## Program:

#### Developed By : YESHWANTH P
#### Register Number : 212222230178

### Installing OpenCV , importing necessary libraries and displaying images  

```py
# Install OpenCV library
!pip install opencv-python-headless

import cv2
import numpy as np
from matplotlib import pyplot as plt

# Function to display images 
def show_image(image):
    plt.figure(figsize=(6, 6))
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.axis('off')
    plt.show()

```

#### (i) Image Translation
```py
# Load an image from URL or file path
image_url = 'images (1).jpeg'  
image = cv2.imread(image_url)

# Define translation matrix
tx = 50  # Translation along x-axis
ty = 30  # Translation along y-axis
translation_matrix = np.float32([[1, 0, tx], [0, 1, ty]])  # Create translation matrix

# Apply translation to the image
translated_image = cv2.warpAffine(image, translation_matrix, (image.shape[1], image.shape[0]))

# Display original and translated images
print("Original Image:")
show_image(image)
print("Translated Image:")
show_image(translated_image)
```

#### (ii) Image Scaling
```py

# Load an image from URL or file path
image_url = 'images (2).jpeg'  # Replace with your image URL or file path
image = cv2.imread(image_url)


# Define scale factors
scale_x = 1.5  # Scaling factor along x-axis
scale_y = 1.5  # Scaling factor along y-axis


# Apply scaling to the image
scaled_image = cv2.resize(image, None, fx=scale_x, fy=scale_y, interpolation=cv2.INTER_LINEAR)

# Display original and scaled images
print("Original Image:")
show_image(image)
print("Scaled Image:")
show_image(scaled_image)

```




#### (iii) Image shearing
```py
# Load an image from URL or file path
image_url = 'images (3).jpeg'  # Replace with your image URL or file path
image = cv2.imread(image_url)

# Define shear parameters
shear_factor_x = 0.5  # Shear factor along x-axis
shear_factor_y = 0.2  # Shear factor along y-axis

# Define shear matrix
shear_matrix = np.float32([[1, shear_factor_x, 0], [shear_factor_y, 1, 0]])

# Apply shear to the image
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))

# Display original and sheared images
print("Original Image:")
show_image(image)
print("Sheared Image:")
show_image(sheared_image)

```



#### (iv) Image Reflection

```py
# Load an image from URL or file path
image_url = 'image (4).jpeg'  # Replace with your image URL or file path
image = cv2.imread(image_url)

# Reflect the image horizontally
reflected_image_horizontal = cv2.flip(image, 1)

# Reflect the image vertically
reflected_image_vertical = cv2.flip(image, 0)

# Reflect the image both horizontally and vertically
reflected_image_both = cv2.flip(image, -1)

```

##### (a) → Reflecting Horizontally

```py
# Display original and reflected images

show_image(image)
print("↑ Original Image")
show_image(reflected_image_horizontal)
print("↑ Reflected Horizontally")
```

##### (b) → Reflected Vertically

```py
show_image(image)
print("↑ Original Image")
show_image(reflected_image_vertical)
print("↑ Reflected Vertically")

```

##### (c) → Reflecting Horizontally & Vertically
```py

show_image(image)
print("↑ Original Image")
show_image(reflected_image_both)
print("↑ Reflected Both")

```

### (v) Image Rotation

```py
# Load an image from URL or file path
image_url = 'images (5).jpeg'  # Replace with your image URL or file path
image = cv2.imread(image_url)


# Define rotation angle in degrees
angle = 45

# Get image height and width
height, width = image.shape[:2]

# Calculate rotation matrix
rotation_matrix = cv2.getRotationMatrix2D((width / 2, height / 2), angle, 1)

# Perform image rotation
rotated_image = cv2.warpAffine(image, rotation_matrix, (width, height))

# Display original and rotated images
print("Original Image:")
show_image(image)
print("Rotated Image:")
show_image(rotated_image)

```



### (vi) Image Cropping

```py
# Load an image from URL or file path
image_url = 'images (6).jpeg'  # Replace with your image URL or file path
image = cv2.imread(image_url)

# Define cropping coordinates (x, y, width, height)
x = 100  # Starting x-coordinate
y = 50   # Starting y-coordinate
width = 200  # Width of the cropped region
height = 150  # Height of the cropped region

# Perform image cropping
cropped_image = image[y:y+height, x:x+width]

# Display original and cropped images
print("Original Image:")
show_image(image)
print("Cropped Image:")
show_image(cropped_image)

```


## Output:

### (i) Image Translation

![313988075-aec8ba8a-13bf-4ff1-b399-047811a404b7](https://github.com/Yeshwanthperumal/IMAGE-TRANSFORMATIONS/assets/119476088/83d02226-b152-4310-a5c3-e846f407ed10)


### (ii) Image Scaling

![313988326-4769271c-805c-415f-91ac-48727fbecf8e](https://github.com/Yeshwanthperumal/IMAGE-TRANSFORMATIONS/assets/119476088/b40318a0-25e4-46e8-9f27-1a5b3a06cba8)


### (iii) Image shearing

![313988584-a7d9b015-e485-4e34-b1ab-1bb6e58e1c3b](https://github.com/Yeshwanthperumal/IMAGE-TRANSFORMATIONS/assets/119476088/e894b5e7-1945-4830-919e-850117061411)

### (iv) Image Reflection

#### Reflecting Horizontally

![313989709-4895ae7b-4dc9-482a-9d4b-1f7a69ce4c40](https://github.com/Yeshwanthperumal/IMAGE-TRANSFORMATIONS/assets/119476088/b8a539b7-55ef-4f41-9c57-9b73eac1ed22)

#### Reflecting Vertically

![313989769-f7ab05df-68d3-464b-a130-98889897d881](https://github.com/Yeshwanthperumal/IMAGE-TRANSFORMATIONS/assets/119476088/89aa66a0-765f-4a5e-b12f-b34a4a9319a5)

#### Reflecting Horizontally & Vertically

![313989837-388608b9-ca3a-493f-a8ba-24c7df42cdc6](https://github.com/Yeshwanthperumal/IMAGE-TRANSFORMATIONS/assets/119476088/38378502-b261-439a-b70f-6b9087bd71c9)

### (v) Image Rotation

![313990104-65b5f08d-073a-4c6c-a52c-1c79ec26e374](https://github.com/Yeshwanthperumal/IMAGE-TRANSFORMATIONS/assets/119476088/72d5d55c-a692-4386-8eae-74fb2d48e5c2)

### (vi) Image Cropping

![313990145-e5cae6c1-1ab7-40e6-a3aa-4b25d05aea5d](https://github.com/Yeshwanthperumal/IMAGE-TRANSFORMATIONS/assets/119476088/a68a71c9-2758-4891-9329-a59a5dc8be02)

## Result: 


Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
