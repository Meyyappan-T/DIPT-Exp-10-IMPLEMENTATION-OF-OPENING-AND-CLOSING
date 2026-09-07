# Exp-10 IMPLEMENTATION OF OPENING AND CLOSING

## Aim:
To implement Opening and Closing using Python and OpenCV.

Software Required
Anaconda - Python 3.7
OpenCV

## Algorithm:
### Step1:
Import the necessary packages

### Step2:
Give the input text using cv2.putText()

### Step3:
Perform opening operation and display the result

### Step4:
Similarly, perform closing operation and display the result

## Program:

#### NAME: MEYYAPPAN T
#### REG.NO: 212223240086

### Import the necessary python libraries
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

### Create a blank image
```
image = np.zeros((500, 500, 3), dtype=np.uint8)
```

### Add text on the image using cv2.putText
```
font = cv2.FONT_HERSHEY_SIMPLEX
cv2.putText(image, 'Open and Close', (100, 250), font, 1, (255, 255, 255), 2, cv2.LINE_AA)
```

### Create a simple square kernel (3x3)
```
kernel = np.ones((3, 3), np.uint8)
```

### Display the input image
```
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for displaying
plt.title("Input Image with Text")
plt.axis('off')
```
<img width="586" height="610" alt="image" src="https://github.com/user-attachments/assets/f75474a1-b27f-4735-8dff-4048d20412e5" />

### Opening is erosion followed by dilation
```
opened_image = cv2.morphologyEx(image, cv2.MORPH_OPEN, kernel)
```

### Display the result of Opening
```
plt.imshow(cv2.cvtColor(opened_image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB
plt.title("Opening Operation")
plt.axis('off')
```
<img width="577" height="600" alt="image" src="https://github.com/user-attachments/assets/8060e8a0-4918-43d1-8dc8-378e7658d557" />

### Closing is dilation followed by erosion
```
closed_image = cv2.morphologyEx(image, cv2.MORPH_CLOSE, kernel)
plt.imshow(closed_image, cmap='gray')
plt.title("Closing Operation")
plt.axis('off')
plt.show()
```
<img width="585" height="613" alt="image" src="https://github.com/user-attachments/assets/a8295029-bde1-4897-809c-2fd322d4ccd3" />

### Result
Thus the Opening and Closing operation is used in the image using python and OpenCV.
