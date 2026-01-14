# Virtual Mouse 🖱️

A Python-based virtual mouse controller that allows you to control your computer cursor using two different methods:
- **Eye-Controlled Mouse**: Control the cursor with your eye gaze
- **Gesture-Controlled Mouse**: Control the cursor with hand gestures

## Features

### Eye-Controlled Mouse
- Detects eye position using facial landmarks
- Moves the cursor based on eye gaze
- Click detection using eyelid proximity (blink detection)
- Real-time video feed with visual indicators

### Gesture-Controlled Mouse
- Detects hand landmarks using MediaPipe
- Controls cursor position using index finger position
- Click detection using thumb and index finger proximity
- Visual indicators for hand tracking

## Requirements

- Python 3.7+
- OpenCV (`cv2`)
- MediaPipe
- PyAutoGUI
- Webcam/Camera

## Installation

1. Clone the repository:
```bash
git clone https://github.com/SChethanSharma/Virtual-Mouse.git
cd Virtual-Mouse
```

2. Install the required packages:
```bash
pip install opencv-python mediapipe pyautogui
```

## Usage

### Eye-Controlled Mouse
Run the eye-controlled mouse:
```bash
python eye_mouse.py
```

**Controls:**
- **Move Cursor**: Your eye gaze controls the cursor position
- **Click**: Close your eyes (blink) to perform a click
- **Exit**: Press `q` or close the window

### Gesture-Controlled Mouse
Run the gesture-controlled mouse:
```bash
python gesture_mouse.py
```

**Controls:**
- **Move Cursor**: Point your index finger to move the cursor
- **Click**: Bring your thumb and index finger close together (within 100 pixels)
- **Exit**: Press `q` or close the window

## Technical Details

### Eye-Controlled Mouse (`eye_mouse.py`)
- Uses MediaPipe's FaceMesh for facial landmark detection
- Detects iris position (landmarks 474-477)
- Detects left eye for blink detection (landmarks 145, 159)
- Click triggered when eye closure distance is less than 0.004

### Gesture-Controlled Mouse (`gesture_mouse.py`)
- Uses MediaPipe's Hand detection
- Tracks index finger (landmark 8) for cursor position
- Tracks thumb (landmark 4) for click detection
- Click triggered when distance between thumb and index is less than 20 pixels
- Movement is enabled when thumb-index distance is less than 100 pixels

## Requirements Explanation

- **OpenCV**: Captures video from webcam and displays the live feed
- **MediaPipe**: Provides pre-trained models for face and hand detection
- **PyAutoGUI**: Controls mouse movements and clicks on the system
- **Python**: Core programming language

## Troubleshooting

- **Webcam not detected**: Ensure your webcam is connected and not being used by another application
- **Poor hand detection**: Ensure adequate lighting in your environment
- **Cursor not moving smoothly**: Try adjusting your camera position for better visibility

## Future Enhancements

- Support for multiple fingers/hand gestures
- Configurable sensitivity settings
- Smooth cursor acceleration
- Double-click and drag-and-drop support
- GUI configuration interface

## License

This project is open source and available on GitHub.

## Author

SChethanSharma
