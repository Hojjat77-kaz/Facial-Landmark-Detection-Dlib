# Facial Landmark Detection using Dlib and OpenCV

Detect human faces and extract **68 facial landmark points** using **Dlib** and **OpenCV**.

This project demonstrates how to locate important facial features such as the eyes, eyebrows, nose, mouth, and jawline by predicting 68 anatomical landmark points. These landmarks are widely used as the foundation for many computer vision applications including blink detection, face alignment, head pose estimation, facial expression analysis, and driver drowsiness detection.

---

## Features

* Detect human faces in images or videos
* Predict 68 facial landmark points
* Draw every landmark on the detected face
* Display landmark index numbers
* Real-time processing using OpenCV
* Easy-to-understand implementation for beginners

---

## Applications

Facial landmarks are used in many computer vision tasks, including:

* Blink Detection
* Eye Tracking
* Face Alignment
* Head Pose Estimation
* Driver Drowsiness Detection
* Facial Expression Recognition
* Emotion Analysis
* Augmented Reality Filters
* Face Animation

---

## Project Pipeline

```text
Input Video
      │
      ▼
Read Frame
      │
      ▼
Convert to Grayscale
      │
      ▼
Detect Face(s)
      │
      ▼
Predict 68 Facial Landmarks
      │
      ▼
Draw Landmarks
      │
      ▼
Display Output
```

---

## 68 Facial Landmark Layout

| Landmark Index | Facial Region |
| -------------- | ------------- |
| 0 – 16         | Jawline       |
| 17 – 21        | Left Eyebrow  |
| 22 – 26        | Right Eyebrow |
| 27 – 35        | Nose          |
| 36 – 41        | Left Eye      |
| 42 – 47        | Right Eye     |
| 48 – 67        | Mouth         |

---

## Project Structure

```text
Facial-Landmark-Detection-Dlib
│
├── images/
│   ├── demo.png
│   └── landmarks.png
│
├── videos/
│   └── faces.mp4
│
├── models/
│   └── shape_predictor_68_face_landmarks.dat
│
├── facial_landmark_detection.py
│
├── requirements.txt
│
└── README.md
```

---

## Requirements

* Python 3.x
* OpenCV
* Dlib
* NumPy

Install the required packages:

```bash
pip install opencv-python
pip install dlib
pip install numpy
```

Or install everything from:

```bash
pip install -r requirements.txt
```

---

## Download the Dlib Model

This project requires the pretrained Dlib landmark model:

```
shape_predictor_68_face_landmarks.dat
```

Download the model and place it inside the **models/** directory before running the program.

---

## How It Works

### Step 1

Read a frame from the input video.

### Step 2

Convert the frame to grayscale.

### Step 3

Detect all faces using Dlib's frontal face detector.

### Step 4

Predict the 68 facial landmark points for each detected face.

### Step 5

Draw the landmark points and their corresponding index numbers.

### Step 6

Display the processed frame.

---

## Example Code

```python
faces = detector(gray)

for face in faces:

    landmarks = predictor(gray, face)

    for i in range(68):

        x = landmarks.part(i).x
        y = landmarks.part(i).y

        cv.circle(frame, (x, y), 2, (0,255,0), -1)
```

---

## Output

The program displays:

* Detected face
* 68 facial landmarks
* Landmark index numbers

Example:

```
Left Eye      : 36 - 41
Right Eye     : 42 - 47
Nose          : 27 - 35
Mouth         : 48 - 67
Jawline       : 0 - 16
```

---

## Future Improvements

This project is the foundation for several advanced computer vision applications.

Possible future extensions include:

* Blink Detection (EAR)
* Mouth Aspect Ratio (MAR)
* Driver Drowsiness Detection
* Head Pose Estimation
* Face Alignment
* Face Recognition
* Emotion Recognition
* Eye Gaze Estimation

---

## Learning Objectives

After completing this project, you will understand:

* How Dlib detects facial landmarks
* How to use the pretrained 68-point landmark model
* How to access each landmark point
* How to visualize facial landmarks
* How landmark detection differs from face detection
* How facial landmarks are used in advanced vision applications

---

## License

This project is intended for educational purposes.

---

## Author

Developed as part of a Computer Vision learning journey using **OpenCV** and **Dlib**.
