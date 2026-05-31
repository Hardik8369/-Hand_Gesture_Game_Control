🎮 Hand Gesture Controlled Subway Surfers (Webcam-Based)

This project lets you play Subway Surfers (or similar running games) using hand gestures detected through your webcam — no keyboard needed!

🖐 Left Hand Gesture → Move Left

🖐 Right Hand Gesture → Move Right

The system uses computer vision to track hand movements in real-time and map them to game controls.

            ┌─────────────────────────────┐
            │        Camera Input          │
            │   (Webcam / External Cam)    │
            └─────────────┬───────────────┘
                          │
                          ▼
            ┌─────────────────────────────┐
            │   Hand Detection (MediaPipe) │
            │   • Extract 21 landmarks     │
            │   • Normalize & preprocess   │
            └─────────────┬───────────────┘
                          │
                          ▼
    ┌──────────────────────────────────────────┐
    │      Gesture Recognition Module          │
    │                                          │
    │  1. **Rule-Based (Current)**             │
    │     • Track hand movement Δx, Δy         │
    │     • Threshold-based decisions          │
    │                                          │
    │  2. **ML Classifier (Upgrade)**          │
    │     • Features: 42 (x,y coords)          │
    │     • Model: SVM / Random Forest / NN    │
    │     • Output: "left", "right", "jump",   │
    │       "duck", "pause"                    │
    └───────────────────┬──────────────────────┘
                        │
                        ▼
    ┌──────────────────────────────────────────┐
    │  Command Mapping Layer                   │
    │                                          │
    │  Gesture → ADB Action                    │
    │  • Jump  → adb swipe up                  │
    │  • Left  → adb swipe left                │
    │  • Right → adb swipe right               │
    │  • Duck  → adb swipe down                │
    │  • Pause → adb keyevent "pause"          │
    └───────────────────┬──────────────────────┘
                        │
                        ▼
    ┌──────────────────────────────────────────┐
    │   ADB → BlueStacks (Subway Surfer)       │
    │   • Executes input events inside game    │
    │   • Real-time control                    │
    └───────────────────┬──────────────────────┘
                        │
                        ▼
    ┌──────────────────────────────────────────┐
    │    Analytics & Feedback Layer            │
    │                                          │
    │  • Track Gesture Accuracy (live %)       │
    │  • Display Move History Overlay          │
    │  • Scoreboard: Successful vs Failed      │
    │  • Store Training Data (for ML)          │
    │  • Improve model iteratively             │
    └──────────────────────────────────────────┘
✨ Features 🎥 Webcam-based gesture detection

🎯 Real-time hand tracking using OpenCV / MediaPipe

🎮 Compatible with running games (Subway Surfers, Temple Run, etc.)

⚡ Fast response time for smooth gameplay

🖥 Works without additional hardware — just your webcam

🛠 Tech Stack

Python

OpenCV for video processing

MediaPipe for hand gesture recognition

PyAutoGUI / Keyboard control libraries for key mapping

🚀 How to Run

Clone the repository

Install dependencies from requirements.txt

Run python main.py

Open your game and start playing using gestures!....
