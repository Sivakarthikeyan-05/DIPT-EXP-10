# Opening and Closing Operations Using OpenCV

## Aim

To write a Python program using OpenCV to perform morphological Opening and Closing operations on an image.

The program performs the following operations:

* Morphological Opening
* Morphological Closing

## Software Used

* Anaconda – Python 3.7
* Jupyter Notebook / VS Code
* OpenCV (cv2)
* NumPy
* Matplotlib

## Algorithm

### Step 1:

Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:

Create a blank image using NumPy and add the text **"Sivakarthikeyan"** using the `cv2.putText()` function.

### Step 3:

Display the original image.

### Step 4:

Create a structuring element (kernel) of suitable size using a 3×3 matrix.

### Step 5: Opening Operation

* Apply the Opening operation using the structuring element.
* Opening consists of Erosion followed by Dilation.
* Apply the operation using `cv2.MORPH_OPEN`.
* Display the opened image.

### Step 6: Closing Operation

* Apply the Closing operation using the structuring element.
* Closing consists of Dilation followed by Erosion.
* Apply the operation using `cv2.MORPH_CLOSE`.
* Display the closed image.

### Step 7:

Compare the original, opened, and closed images.

## Program

## Developed By

**Name:** Sivakarthikeyan V.

**Register No:** 212225220098

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Create a blank image
image = np.zeros((500, 500, 3), dtype=np.uint8)

# Add text on the image using cv2.putText
font = cv2.FONT_HERSHEY_SIMPLEX
cv2.putText(image, 'Sivakarthikeyan', (100, 250), font, 1, (255, 255, 255), 2, cv2.LINE_AA)

# Create a simple square kernel (3x3)
kernel = np.ones((3, 3), np.uint8)

# Display the input image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for displaying
plt.title("Input Image with Text")
plt.axis('off')


# Opening is erosion followed by dilation
opened_image = cv2.morphologyEx(image, cv2.MORPH_OPEN, kernel)

# Display the result of Opening
plt.imshow(cv2.cvtColor(opened_image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB
plt.title("Opening Operation")
plt.axis('off')

# Closing is dilation followed by erosion
closed_image = cv2.morphologyEx(image, cv2.MORPH_CLOSE, kernel)
```

## Output

### Original Image

<img width="349" height="378" alt="image" src="https://github.com/user-attachments/assets/3d9f1ddb-a706-439f-a352-247033e8e652" />

* The input image is displayed.
* The image contains the text **"Sivakarthikeyan"**.
* The image serves as the source for morphological processing.

### Opening Operation

<img width="353" height="383" alt="image" src="https://github.com/user-attachments/assets/23e8633f-f368-440c-97fc-675fc61d3698" />


* The original image is processed using the Opening operation.
* Opening is performed using Erosion followed by Dilation.
* The processed image is displayed with the title **"Opening Operation"**.

### Closing Operation

<img width="352" height="379" alt="image" src="https://github.com/user-attachments/assets/d4b549b0-b695-4e84-b07c-5d86a9cf04b2" />


* The original image is processed using the Closing operation.
* Closing is performed using Dilation followed by Erosion.
* The processed image is generated with the title **"Closing Operation"**.

## Applications

### Opening

* Noise removal in binary images.
* Separation of connected objects.
* Preprocessing for object detection.

### Closing

* Filling small holes in objects.
* Connecting nearby components.
* Enhancing segmented regions.

## Advantages

### Opening

* Removes unwanted foreground noise.
* Preserves major object structures.
* Improves segmentation quality.

### Closing

* Restores object continuity.
* Eliminates small background gaps.
* Improves object representation.

## Result

Thus, the morphological operations **Opening** and **Closing** are successfully implemented using OpenCV.
