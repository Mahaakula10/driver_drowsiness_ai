Driver Drowsiness Detection System
📌 Overview

The Driver Drowsiness Detection System is a real-time computer vision project developed using Python and OpenCV. It detects driver fatigue by continuously monitoring the driver's eyes through a webcam.

The system uses facial landmark detection to calculate the Eye Aspect Ratio (EAR). When the driver's eyes remain closed for a specified number of consecutive frames, the system identifies possible drowsiness and triggers an audio alarm to alert the driver.

This project aims to help prevent road accidents caused by driver fatigue and lack of attention.

✨ Features
Real-time face detection using a webcam.
Detects facial landmarks using Dlib.
Identifies and tracks both eyes.
Calculates the Eye Aspect Ratio (EAR).
Detects prolonged eye closure.
Displays a visual warning on the screen.
Plays an alarm sound when drowsiness is detected.
Press q to exit the application.
🛠️ Technologies Used
Python – Main programming language.
OpenCV – Image processing and webcam access.
Dlib – Face detection and facial landmark prediction.
Imutils – Image processing utilities.
SciPy – Euclidean distance calculation.
Pygame – Audio alarm functionality.
📂 Project Structure
text
Driver-Drowsiness-Detection/
│
├── models/
│   └── shape_predictor_68_face_landmarks.dat
│
├── music.wav
├── drowsiness_detection.py
└── README.md

📦 Installation
1. Clone the Repository
bash
git clone https://github.com/Mahaakula10/driver_drowsiness_ai.git

2. Navigate to the Project Directory
bash
cd Driver-Drowsiness-Detection

3. Install Required Libraries
bash
pip install opencv-python
pip install dlib
pip install imutils
pip install scipy
pip install pygame

4. Download the Facial Landmark Predictor

Download the shape_predictor_68_face_landmarks.dat file.

You can obtain it from the official Dlib model collection:

http://dlib.net/files/shape_predictor_68_face_landmarks.dat.bz2

Extract the downloaded file and place it inside the models directory.

5. Add the Alarm Sound

Place an audio file named music.wav in the root project directory. This file will be played whenever drowsiness is detected.

▶️ How to Run

Execute the following command:

bash
python main.py


Make sure your webcam is connected and accessible.

Press q to close the application.

⚙️ Working Principle

The system works through the following steps:

Video Capture: Captures real-time video frames using the webcam.
Face Detection: Detects the driver's face using Dlib's frontal face detector.
Facial Landmark Detection: Identifies 68 facial landmarks, including the coordinates of both eyes.
Eye Detection: Extracts the left and right eye coordinates.
EAR Calculation: Calculates the Eye Aspect Ratio to determine whether the eyes are open or closed.
Drowsiness Detection: If the EAR value falls below the predefined threshold for 20 consecutive frames, the system detects possible drowsiness.
Alert Generation: Displays a warning message and plays an alarm sound to alert the driver.
📐 Eye Aspect Ratio (EAR)

The Eye Aspect Ratio is used to measure the degree of eye openness.

The formula is:

text
             ||P2 - P6|| + ||P3 - P5||
EAR =        -------------------------
                  2 * ||P1 - P4||


Where:

P1 to P6 represent the six facial landmark points around the eye.
The vertical distances indicate eye openness.
The horizontal distance represents eye width.

When the eyes are open, the EAR value is relatively high. When the eyes are closed, the EAR value decreases.

In this project:

EAR Threshold: 0.25
Frame Check: 20 consecutive frames

If the EAR remains below 0.25 for 20 consecutive frames, an alarm is triggered.

The application displays:

Live webcam video.
Green contours around the detected eyes.
A warning message when prolonged eye closure is detected.
An audio alarm when possible drowsiness is identified.

