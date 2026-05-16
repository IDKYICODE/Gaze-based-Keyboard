# Gaze-Based Keyboard (EyeType)

<!-- ADD SCREENSHOT HERE -->
<!-- ![EyeType Interface](path/to/screenshot.png) -->

A hands-free input system that lets users type and interact using only their eyes. No specialized hardware required — just a standard webcam. Uses MediaPipe FaceMesh to track eye position in real time, maps gaze to an on-screen virtual keyboard, and registers key presses through sustained gaze (dwell-click).

---

## How It Works

1. Webcam captures live video feed.
2. **MediaPipe FaceMesh** detects 468 facial landmarks per frame and extracts eye position/direction.
3. Landmark coordinates are mapped to screen space — a virtual cursor follows the user's gaze.
4. Hovering the cursor over a key for a set dwell duration triggers a selection — no click, no hands.
5. The selected character is registered as keyboard input.

Three separate interaction modes are available depending on the use case.

---

## Notebooks

| Notebook | Mode | Description |
|----------|------|-------------|
| `MPS/experiment.ipynb` | **Keyboard** | Core EyeType system — gaze-controlled virtual keyboard for text input |
| `MPS/game.ipynb` | **Game** | Game interface navigated entirely through gaze direction |
| `MPS/mcq.ipynb` | **MCQ** | Multiple choice question answering via gaze selection on options |

---

## Tech Stack

| Library | Purpose |
|---------|---------|
| `opencv-python` | Webcam capture, UI rendering, window management |
| `mediapipe` | Face mesh detection and facial landmark extraction |
| `numpy` | Cursor position calculations and coordinate mapping |
| `jupyter` | Notebook runtime |

---

## Requirements

Python 3.8+ and a working webcam.

```bash
pip install opencv-python mediapipe numpy jupyter
```

---

## Usage

```bash
jupyter notebook MPS/experiment.ipynb
```

1. Run all cells in the notebook
2. Position your face clearly in front of the webcam (good lighting recommended)
3. The EyeType interface window appears alongside the camera feed
4. Look at a key — the cursor follows your gaze
5. Hold gaze on a key to select it (dwell-click)
6. Press `ESC` or look at the Exit button to quit

---

## Interaction Modes

| Mode | Notebook | How to Use |
|------|----------|------------|
| Keyboard | `experiment.ipynb` | Gaze at character keys + dwell to type |
| Game | `game.ipynb` | Gaze direction maps to movement/action |
| MCQ | `mcq.ipynb` | Look at an answer option to select it |

---

## Notes

- No eye-tracking hardware needed — webcam-only
- Works best with consistent face position and stable lighting
- Dwell time threshold can be tuned in the notebook for faster/slower selection