# Smile Detector

A real-time face, eye, and smile detection application using OpenCV and Haar Cascades.

## Overview

This project uses computer vision techniques to detect faces, eyes, and smiles in real-time through your webcam. The application draws rectangles around detected facial features:
- Blue rectangle: Face
- Green rectangle: Eyes
- Teal rectangle: Smile

## Prerequisites

- Python 3.x
- OpenCV (cv2)
- Haar Cascade XML files:
  - `haarcascade_frontalface_default.xml`
  - `haarcascade_eye.xml`
  - `haarcascade_smile.xml`

## Installation

1. Clone this repository or download the source code.
2. Install the required packages:
   ```
   pip install opencv-python
   ```
   or
   ```
   pip install -r requirements.txt
   ```

## Usage

1. Run the script:
   ```
   python smile_detector.py
   ```
2. The webcam will activate and display a window showing the video feed with detection rectangles.
3. Press 'q' to quit the application.

## How It Works

The application:
1. Captures video from your webcam
2. Converts each frame to grayscale for processing
3. Detects faces in the frame
4. For each detected face, it searches for eyes and smiles within the face region
5. Draws colored rectangles around each detected feature
6. Displays the processed frame in real-time

## Adjusting Detection Parameters

You can adjust the detection sensitivity by modifying these parameters in the `detect()` function:
- Scale factor: The value by which the image size is reduced at each scale
- Minimum neighbors: How many neighbors each candidate rectangle should have to retain it

For example:
```python
faces = face_cascade.detectMultiScale(gray, 1.3, 5)  # 1.3 is scale factor, 5 is minNeighbors
```

## Limitations

- Detection accuracy depends on lighting conditions
- May not work perfectly for all face angles and expressions
- Requires proper positioning in front of the camera
