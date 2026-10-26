# Experiment 2: Image Acquisition using Web Camera

## *Name:* JANANI D
## *Register Number:* 212225040142

## Aim

To write a Python program using OpenCV to capture images from a webcam and perform the following image manipulations:

1. Write the captured frame as a JPG file.
2. Display the video.
3. Display the video by resizing the frame.
4. Rotate and display the video.

## Software Used

- Anaconda
- Python 3.7
- OpenCV
- NumPy

## Algorithm

### Step 1
Import the `cv2` and `numpy` packages.

### Step 2
Read the video frame using `cv2.VideoCapture(0)`.

### Step 3
Write the captured image using `cv2.imwrite()`.

### Step 4
Display the video frame using `cv2.imshow()`.

### Step 5
Divide the frame into four parts, resize the frame, and assign the smaller frame to each part.

### Step 6
Rotate the frame using `cv2.rotate()` and display the output.

## Program

**Developed By:** SHRIVARSHAN P G

**Register Number:** 212225240146

## i) Write the Frame as a JPG File

```python
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("captured_frame.jpg", frame)
cap.release()

captured_image = cv2.imread('captured_frame.jpg')

plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()
```

## ii) Display the Video

```python
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```

## iii) Display the Video by Resizing the Frame

```python
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    resized_frame = cv2.resize(frame, (100, 150))  # Resize to 320x240
    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```

## iv) Rotate and Display the Video

```python
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```

## Output

### i) Write the Frame as a JPG Image

<img width="652" height="506" alt="image" src="https://github.com/user-attachments/assets/bf4d31b9-dc6a-4d8f-9420-fd343627e8ce" />


### ii) Display the Video

<img width="670" height="492" alt="image" src="https://github.com/user-attachments/assets/50aca9a9-5b47-4214-a28c-21eb7f616c64" />


### iii) Display the Video by Resizing the Frame

<img width="342" height="477" alt="image" src="https://github.com/user-attachments/assets/5a8e0bb8-1384-4515-b1b6-94fae8409432" />


### iv) Rotate and Display the Video

<img width="380" height="485" alt="image" src="https://github.com/user-attachments/assets/eb802172-83ea-4254-8608-bfa73ba5d8d9" />


## Result

Thus, images were captured from the webcam, saved as JPG files, and displayed using OpenCV. The video frames were resized and rotated successfully.
