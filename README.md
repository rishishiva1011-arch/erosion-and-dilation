# Implementation of Erosion and Dilation Using OpenCV

## Aim

To write a Python program using OpenCV to perform morphological
operations such as Erosion and Dilation on an image.

## Learning Objectives

-   Understand morphological operations in image processing.
-   Learn how erosion reduces the boundaries of foreground objects.
-   Learn how dilation expands the boundaries of foreground objects.
-   Compare the results of erosion and dilation.

## Software Used

-   Anaconda -- Python 3.7
-   Jupyter Notebook / VS Code
-   OpenCV (`cv2`)
-   NumPy
-   Matplotlib

## Algorithm and Explanation

### Step 1: Import Libraries

Import OpenCV, NumPy, and Matplotlib for image processing and displaying
the results.

``` python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

### Step 2: Create Image and Insert Text

Create a blank black image using NumPy and insert the text `OPENCV`
using OpenCV.

``` python
image = np.zeros((500, 500, 3), dtype=np.uint8)
font = cv2.FONT_HERSHEY_SIMPLEX
cv2.putText(image, 'Saveetha Engineering College', (50, 250), font, 1, (255, 255, 255), 2, cv2.LINE_AA)
```

### Step 3: Display the input image
Display the input image
``` python
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for displaying
plt.title("Input Image with Text")
plt.axis('off')
```

### Step 4: Create Kernel

Create a 5 × 5 structuring element (kernel) for the morphological
operations.

``` python
kernel = np.ones((5, 5), np.uint8)
```

### Step 5: Perform Erosion and Dilation

Erosion reduces the thickness of the foreground text, while dilation
increases its thickness.

**Erosion**

``` python
erosion = cv2.erode(image, kernel, iterations=1)
```

**Dilation**

``` python
dilation = cv2.dilate(image, kernel, iterations=1)
```

### Step 6: Display and Compare Results

Display the eroded, and dilated images together for
comparison.

``` python
plt.imshow(cv2.cvtColor(eroded_image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB
plt.title("Eroded Image")
plt.axis('off')

plt.imshow(cv2.cvtColor(dilated_image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB
plt.title("Dilated Image")
plt.axis('off')

```

##  Output

### Original Image

<img width="1641" height="1320" alt="image" src="https://github.com/user-attachments/assets/f444c07f-b22b-40e2-bbd5-c0fb4ca24b7d" />


### Eroded Image


<img width="1629" height="1305" alt="image" src="https://github.com/user-attachments/assets/2f301f17-3f28-4913-93aa-da1a5720ab17" />



### Dilated Image


<img width="1725" height="1323" alt="image" src="https://github.com/user-attachments/assets/f3c07a18-e6df-41de-851e-fd8801ae0baa" />



## Result

Thus, the morphological operations **Erosion** and **Dilation** are
successfully implemented using OpenCV.
