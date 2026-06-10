# Robotic Hand Tracking Controller

A computer vision project that tracks hand movements and controls a robotic hand using servo motors.

![Python](https://img.shields.io/badge/Python-3.x-blue)
![OpenCV](https://img.shields.io/badge/OpenCV-Computer_Vision-green)
![MediaPipe](https://img.shields.io/badge/MediaPipe-Hand_Tracking-orange)
![NumPy](https://img.shields.io/badge/NumPy-Numerical_Computing-blue)
![LabVIEW](https://img.shields.io/badge/LabVIEW-Project-yellow)

---

## Overview

This project combines computer vision and robotics to control a physical robotic hand.

A webcam feed is processed using OpenCV and MediaPipe to detect hand landmarks in real time. Finger bending angles are calculated, filtered, and mapped to PWM values used to control servo motors through a PCA9685 controller.

The repository also includes LabVIEW project files and STL models used to build the robotic hand and forearm assembly.

---

## Features

* Real-time hand tracking
* Hand landmark detection
* Finger angle calculation
* Rotation-aware landmark processing
* Servo PWM mapping
* PCA9685 servo control
* Motion smoothing using EMA filtering
* Deadband filtering
* Idle and Tracking operating modes
* Automatic return-to-default position
* Calibration wave sequence
* Hardware fallback mode
* Included STL models
* Included LabVIEW assets

---

## Tech Stack

| Category               | Technology       |
| ---------------------- | ---------------- |
| Language               | Python           |
| Computer Vision        | OpenCV           |
| Hand Tracking          | MediaPipe        |
| Numerical Computing    | NumPy            |
| Servo Control          | Adafruit PCA9685 |
| Hardware Communication | board, busio     |
| Engineering Tools      | LabVIEW          |
| CAD Assets             | STL Models       |

---

## Architecture

```text
Camera
   ↓
OpenCV
   ↓
MediaPipe
   ↓
Hand Landmark Detection
   ↓
Finger Angle Calculation
   ↓
Signal Smoothing
   ↓
PWM Mapping
   ↓
PCA9685
   ↓
Servo Motors
   ↓
Robotic Hand
```

---

## Application Flow

1. Capture frames from a webcam.
2. Detect a hand using MediaPipe.
3. Extract hand landmarks.
4. Normalize landmarks relative to hand orientation.
5. Calculate finger bending angles.
6. Apply smoothing and deadband filtering.
7. Convert values to PWM ranges.
8. Send commands to PCA9685.
9. Move the robotic hand.

---

## Screenshots

### Hand Tracking

*Add screenshot*

### Robotic Hand

*Add screenshot*

### Mechanical Assembly

*Add screenshot*

---

## Demo

### Video Walkthrough

*Add video link*

---

## Installation

### Requirements

* Python 3
* Webcam
* PCA9685 controller (optional for hardware control)

### Install Dependencies

```bash
pip install opencv-python mediapipe numpy adafruit-circuitpython-pca9685
```

### Run

```bash
python Kod/script.py
```

---

## Configuration

Configuration values are defined directly inside:

```text
Kod/script.py
```

Examples include:

* finger smoothing factors,
* deadband thresholds,
* activation timings,
* timeout values,
* PWM ranges.

No environment variables were found in the repository.

---

## Technical Highlights

### Rotation-Aware Landmark Processing

Hand landmarks are normalized relative to hand orientation before angle calculations.

### Motion Smoothing

Servo commands are smoothed using Exponential Moving Average (EMA).

### Deadband Filtering

Small movements are ignored to reduce servo jitter.

### Per-Finger Calibration

Each finger uses independent PWM ranges.

### State Machine

The application operates using IDLE and TRACKING states.

### Hardware Fallback Mode

A DummyPCA implementation allows running the application without physical hardware.

---

## Project Structure

```text
ADAPTER/
├── Adapter STL models

Kod/
├── script.py
├── *.vi
├── *.ctl
└── *.ctt

Photo/
├── Project photos

PRZEDRAMIE/
├── Forearm STL models

REKA ROBOTA/
├── Hand STL models

video/
├── Demonstration video
```

---

## Testing

No automated tests were found in the repository.

---

## CI/CD

No CI/CD workflows were found in the repository.

---

## Future Improvements

* Complete wrist tracking functionality already present in commented sections
* Move configuration values to external configuration files
* Add diagnostics and logging
* Improve calibration workflow
* Support additional servo configurations

---

## What I Learned

This project helped me learn how computer vision can be combined with hardware control. I worked with MediaPipe hand tracking, geometric calculations, signal filtering, and servo motor control. It was also a good opportunity to connect software with a physical robotic system and work with custom-designed mechanical components.

---

## Source Code Availability

Source code is private due to commercial and intellectual property reasons.
