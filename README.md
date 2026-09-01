# Image Capture and Video Processing Using OpenCV

---

## Aim

To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

1. Write the frame as a JPG file.
2. Display the video.
3. Display the video by resizing the window.
4. Rotate and display the video.

---

## Software Used

- Anaconda – Python 3.7
- Jupyter Notebook
- OpenCV (`cv2`)
- Matplotlib

---

## Algorithm

### Step 1:
Import the required libraries and initialize the webcam using `cv2.VideoCapture()`.

### Step 2:
Capture a frame from the webcam and save it as a JPG image.

### Step 3:
Display the captured image using Matplotlib.

### Step 4:
Capture and display the live webcam video continuously.

### Step 5:
Resize the captured video frames and display them.

### Step 6:
Rotate the captured video frames by 90° clockwise and display them.

---

## Program

### Developed By:
**Name:** THARUN R

### Register No:
**212224240172**

---

### 1. Import the required libraries.

```python
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
```

---

### 2. Capture a frame from the webcam and save it as a JPG image.

```python
cap = cv2.VideoCapture(0)

ret, frame = cap.read()

if ret:
    cv2.imwrite("captured_frame.jpg", frame)

cap.release()
```

---

### 3. Read the captured image.

```python
captured_image = cv2.imread("captured_frame.jpg")
```

---

### 4. Display the captured image.

```python
plt.imshow(captured_image[:, :, ::-1])
plt.title("Captured Frame")
plt.axis("off")
plt.show()
```

---

### 5. Display the live webcam video.

```python
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis("off")
    plt.show()

    time.sleep(0.05)

cap.release()
```

---

### 6. Display the video after resizing.

```python
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    resized_frame = cv2.resize(frame, (100, 150))

    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis("off")
    plt.show()

    time.sleep(0.05)

cap.release()
```

---

### 7. Rotate the video by 90° clockwise and display it.

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
    plt.axis("off")
    plt.show()

    time.sleep(0.05)

cap.release()
```

---

## Output

### i) Write the frame as JPG image
The captured frame is saved as **captured_frame.jpg**.

<img width="662" height="497" alt="Screenshot 2026-07-28 155016" src="https://github.com/user-attachments/assets/afe1f6df-f6e2-4f0a-9527-d6735a6311ce" />



### ii) Display the video
The live webcam video is displayed.

<img width="662" height="497" alt="Screenshot 2026-07-28 155016" src="https://github.com/user-attachments/assets/e0e947a1-d18e-48ae-9fb5-e863e1907db7" />


### iii) Display the video by resizing the window
The webcam video is displayed after resizing the frame.

<img width="368" height="527" alt="Screenshot 2026-07-28 155147" src="https://github.com/user-attachments/assets/c7afa0f0-7607-4807-910c-42d670a6ba34" />


### iv) Rotate and display the video
The webcam video is displayed after rotating it by **90° clockwise**.

<img width="421" height="518" alt="Screenshot 2026-07-28 155050" src="https://github.com/user-attachments/assets/cd9804c4-9e84-4795-baeb-8c0b9b628c4f" />

## Result

Thus, the image was successfully captured from the webcam and various video processing operations such as image capture, live video display, resizing, and rotation were performed successfully using OpenCV.
