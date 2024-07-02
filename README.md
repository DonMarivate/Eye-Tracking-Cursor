# Eye-Tracking-Cursor

Eye Tracking Cursor Project

# Overview
This project uses computer vision techniques to track eye movements and control the cursor on the screen accordingly. It leverages the Mediapipe library for face mesh detection and OpenCV for image processing. The cursor movement is facilitated using the PyAutoGUI library, which allows for interaction with the screen based on the detected eye movements.

# Requirements
Python 3.x
OpenCV (cv2)
Mediapipe (mediapipe)
PyAutoGUI (pyautogui)

# Installation
Clone the repository:
bash
Copy code
git clone <repository-url>

# Install the required libraries:
Copy code
pip install opencv-python mediapipe pyautogui

# Usage
Connect a webcam to your computer.
Run the script eye_tracking_cursor.py.
Copy code
python eye_tracking_cursor.py
Position your face in front of the camera so that your eyes are visible.
The script will track your eye movements and move the cursor on the screen accordingly.
Blinking both eyes or specific eye movements can trigger actions such as clicking.
Code Explanation
Initialization: The script initializes the webcam (cv2.VideoCapture(0)) and sets up the FaceMesh model from Mediapipe (mp.solutions.face_mesh.FaceMesh).
Video Processing: It captures frames from the webcam, flips them horizontally (cv2.flip(frame, 1)), and converts them to RGB format (cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)).
Face Mesh Detection: Using Mediapipe, it detects landmarks on the face, specifically focusing on landmarks around the eyes.
Cursor Control: Based on the detected eye landmarks, it calculates the position of the cursor on the screen using PyAutoGUI (pyautogui.moveTo(screen_x, screen_y)).
Interaction: It monitors eye movements to perform actions such as clicking (pyautogui.click()) based on predefined conditions.

# Notes
Ensure proper lighting and positioning for accurate eye tracking.
Adjust parameters and thresholds (if (left[0].y - left[1].y) < 0.004) based on your setup and requirements.
This project serves as a basic prototype and can be extended for more complex interactions and applications.
