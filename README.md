# Hand Gesture Recognition using OpenCV and MediaPipe

## SkillCraft Technology - Machine Learning Internship
### Task 04

Real-time hand gesture recognition from a live webcam feed using a dual-engine approach - MediaPipe Hands for landmark-based detection and OpenCV contour + convex hull as an automatic fallback.

---

## Features

- Real-time webcam detection
- Multi-hand tracking (Left / Right identification)
- Finger counting (0 - 5)
- Named gesture recognition (9 gestures)
- 21-point landmark visualization
- Live FPS display
- Auto-fallback to OpenCV skin-segmentation when MediaPipe cannot detect a hand
- Gesture smoother (reduces flicker with rolling-window + hold timer)
- Interactive HUD overlay

---

## Technologies Used

| Tool                | Purpose                                       |
|---------------------|-----------------------------------------------|
| Python 3.9+         | Core language                                 |
| OpenCV              | Video capture, contour analysis, UI rendering |
| MediaPipe           | Hand landmark detection (21 keypoints)        |
| NumPy               | Numerical operations and angle computation    |
| Collections (deque) | Gesture smoothing buffer                      |

---

## Recognised Gestures

| Gesture    | Trigger Condition                           |
|------------|---------------------------------------------|
| Fist       | All fingers curled                          |
| Open Hand  | All 5 fingers extended                      |
| Thumbs Up  | Only thumb up, tip above wrist              |
| Peace      | Index + middle extended                     |
| OK Sign    | Thumb tip near index tip, rest extended     |
| Pointing   | Only index finger extended                  |
| Rock On    | Index + pinky extended                      |
| Spider-Man | Thumb + index + pinky extended              |
| Call Me    | Thumb + pinky extended                      |

---

## Architecture

```
Webcam Frame
     |
     |---> MediaPipe Hands ---> Landmark Detection ---> Gesture Classification
     |           |                                              |
     |    (if no hand detected)                                |
     |           |                                             |
     +---> OpenCV Fallback ---> Skin Mask ---> Convex Hull ---> Finger Count
                                                               |
                                                       Gesture Smoother
                                                               |
                                                          HUD Overlay
```

---

## How to Run

### 1. Clone the repository
```bash
git clone https://github.com/Sowmya-116/SCT_ML_4.git
cd SCT_ML_4
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Run the script
```bash
python hand_gesture_recognition.py
```

> Press **Q** or **ESC** to quit.

---

## Project Structure

```
SCT_ML_4/
|-- hand_gesture_recognition.py   # Main script
|-- requirements.txt              # Python dependencies
|-- README.md                     # Project documentation
```

---

## Requirements

```
opencv-python>=4.8.0
mediapipe>=0.10.0
numpy>=1.24.0
```

---

## Author

Sowmya - SkillCraft Technology ML Internship, Task 04

---

## License

This project is for educational purposes under the SkillCraft Technology ML Internship program.
