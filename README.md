# Robotic Hand Tracking Controller

[![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)](https://github.com/MatysiakQ/Hand-Tracking-Control-System)
[![Python](https://img.shields.io/badge/Python-3.x-blue?style=for-the-badge&logo=python)](https://www.python.org/)
[![OpenCV](https://img.shields.io/badge/OpenCV-Computer%20Vision-red?style=for-the-badge&logo=opencv)](https://opencv.org/)
[![MediaPipe](https://img.shields.io/badge/MediaPipe-Hand%20Tracking-orange?style=for-the-badge)](https://developers.google.com/mediapipe)
[![LabVIEW](https://img.shields.io/badge/LabVIEW-2025-yellow?style=for-the-badge&logo=ni)](https://www.ni.com/labview/)
[![Raspberry Pi](https://img.shields.io/badge/Raspberry%20Pi-Middleware-C51A4A?style=for-the-badge&logo=raspberrypi)](https://www.raspberrypi.com/)

Developed by **Adam Jastrzębski** & **Łukasz Koszołko**

A computer vision project that tracks human hand movement and controls a physical robotic hand using servo motors, MediaPipe hand tracking, LabVIEW integration, and a custom Raspberry Pi middleware layer.

---

## Overview

This project combines computer vision, robotics, and embedded systems to control a physical robotic hand.

A webcam feed is processed using OpenCV and MediaPipe to detect hand landmarks in real time. Finger bending angles are calculated, filtered, and mapped to PWM values used to control servo motors through a PCA9685 controller.

The project also includes a custom middleware layer that enables LabVIEW-based control on Raspberry Pi devices, allowing LabVIEW components and Python-based vision processing to work together.

The repository contains Python control software, LabVIEW project files, STL models used to build the robotic hand and forearm assembly, project photos, and demonstration GIFs.


## Features

- Real-time hand tracking
- Hand landmark detection
- Finger angle calculation
- Rotation-aware landmark processing
- Servo PWM mapping
- PCA9685 servo control
- Motion smoothing using EMA filtering
- Deadband filtering
- Idle and Tracking operating modes
- Automatic return-to-default position
- Calibration wave sequence
- LabVIEW integration
- Raspberry Pi middleware support
- Hardware fallback mode
- Included STL models for the hand and forearm
- Included LabVIEW assets

---

## Tech Stack

| Category | Technology |
|----------|------------|
| Language | Python |
| Computer Vision | OpenCV |
| Hand Tracking | MediaPipe |
| Numerical Computing | NumPy |
| Servo Control | Adafruit PCA9685 |
| Hardware Communication | board, busio |
| Engineering Tools | LabVIEW |
| Embedded Platform | Raspberry Pi |
| CAD Assets | STL Models |

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
Python Control Layer
↓
LabVIEW Middleware
↓
Raspberry Pi
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
8. Send commands through the middleware layer.
9. Drive servos through the PCA9685 controller.
10. Replicate finger movement on the robotic hand.

---

## Project Gallery

### Internal Hand Mechanism

![Internal Mechanism](photos/Hand_Inside.jpg)

---

### Hardware Development Progress

The images below present hardware development stages from the most recent version to earlier iterations.

![Hardware Progress](photos/Work_in_Progres4.jpg)

![Hardware Progress 2](photos/Work_in_Progres3.jpg)

![Hardware Progress 3](photos/Work_in_Progres2.jpg)

![Hardware Progress 4](photos/Work_in_Progres1.jpg)

---

### Python Hand Tracking Development

![Python Tracking](photos/Work_in_Progres_py1.jpg)

![Python Tracking 2](photos/Work_in_Progres_py2.jpg)

---

## Demonstrations

### Full Robotic Hand Demonstration

![Robotic Hand Demo](video/Hand_Tracking.gif)

---

### Python Hand Tracking Demonstration

![Hand Tracking Demo](video/Hand_Tracking_Py.gif)

---

## Development Journey

### Hardware Development

- Mechanical hand design
- Tendon routing improvements
- Servo integration
- Electronics assembly
- Calibration and testing

### Software Development

- Hand landmark detection
- Finger angle calculations
- Motion filtering
- Servo mapping
- Raspberry Pi middleware integration
- LabVIEW communication layer

---

## Installation

### Requirements

- Python 3
- Webcam
- PCA9685 controller (optional for hardware control)

### Install Dependencies

```bash
pip install opencv-python mediapipe numpy adafruit-circuitpython-pca9685
```

## Configuration

Configuration values are defined directly

Examples include:

- finger smoothing factors
- deadband thresholds
- activation timings
- timeout values
- PWM ranges

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

### LabVIEW Middleware

A custom middleware layer enables communication between LabVIEW components and Raspberry Pi-based control hardware.

### Hardware Fallback Mode

A DummyPCA implementation allows running the application without physical hardware.

---

## Repository Contents

- Python source code
- LabVIEW project files
- Raspberry Pi middleware
- STL models
- Development photos
- Demonstration GIFs

---

---

## Testing

Tests are private due to commercial and intellectual property reasons.

---

---

## Source Code Availability

Source code is private due to commercial and intellectual property reasons.

---

## Authors

### Adam Jastrzębski

[![GitHub](https://img.shields.io/badge/GitHub-MatysiakQ-181717?style=for-the-badge&logo=github)](https://github.com/MatysiakQ)

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Adam_Jastrzębski-0A66C2?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/adamjastrzebski/)

[![Portfolio](https://img.shields.io/badge/Portfolio-adamjastrzebski.bio-4CAF50?style=for-the-badge&logo=googlechrome)](https://adamjastrzebski.bio/)

### Łukasz Koszołko

[![GitHub](https://img.shields.io/badge/GitHub-lKoszolko-181717?style=for-the-badge&logo=github)](https://github.com/lKoszolko)

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Łukasz_Koszołko-0A66C2?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/%C5%82ukasz-koszo%C5%82ko-069828355/)

---

## Acknowledgements

This project was developed collaboratively by Adam Jastrzębski and Łukasz Koszołko as part of a robotics and computer vision system integrating Python, MediaPipe, LabVIEW, Raspberry Pi, and custom-designed mechanical components.
