
# Image-Capture-and-Video-Processing-Using-OpenCV
Aim
To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

Write the frame as a JPG file
Display the video
Display the video by resizing the window
Rotate and display the video
🛠️ Software Used
Anaconda – Python 3.7
Jupyter Notebook / VS Code
OpenCV (cv2)
⚙️ Algorithm
Step 1:
Import the required libraries and initialize the webcam using cv2.VideoCapture().

Step 2:
Capture frames continuously from the webcam.

Step 3:
Save a frame as a JPG image using cv2.imwrite().

Step 4:
Display the live video stream using cv2.imshow().

Step 5:
Resize the frame and rotate it using OpenCV functions, then display the processed frames.

💻 Program
Developed By:
Name: HARSHITHA D

Register No: 212224040110
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
Output
i) Write the frame as JPG image
Captured image is saved as captured_image.jpg
<img width="512" height="409" alt="7510f3d0-5dac-4497-bde7-d804fe0beae1" src="https://github.com/user-attachments/assets/272bcce1-f04c-46c3-89bb-38fda0fa50eb" />


image
ii) Display the video
Live webcam video is displayed
<img width="512" height="389" alt="b2127c76-ae11-496a-b2be-4fbb36c11b46" src="https://github.com/user-attachments/assets/8d840ab0-5ad7-4ddd-8ee9-1480086fc86e" />


image
iii) Display the video by resizing the window
Video is shown in resized resolution (640 × 480)
<img width="266" height="389" alt="b87688fe-b009-4141-926c-37ebce0c4853" src="https://github.com/user-attachments/assets/d1d685ac-7790-4d18-a171-8d4a8c85df50" />


image
Result
Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
