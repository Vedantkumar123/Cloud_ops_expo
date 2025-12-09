# ✋🎨 **Scribble Game – Hand Gesture Controlled Drawing App**

A computer-vision–based interactive **scribble/drawing application** where the user draws on the screen using **hand gestures** — no mouse, keyboard, or touch required.
This project uses **OpenCV**, **cvzone Hand Tracking**, and **gesture recognition** to enable natural drawing movements through your index finger.

---

## 🚀 **Features**

### ✔️ **Hand-Gesture Based Controls**

* **Point (Index finger up):** Move the cursor
* **Draw (Index + Middle finger up):** Start drawing on slides
* **Clear Screen (Only Pinky up):** Reset all strokes
* **Undo (Index + Middle + Ring up):** Remove last annotation
* **Redo (All fingers except thumb up):** Restore last removed annotation

### ✔️ **Live Webcam Tracking**

* Smooth and real-time hand landmark tracking
* Motion interpolation for stable drawing
* Gesture threshold line for activation

### ✔️ **Slide Integration**

* Load images from a folder
* Draw on top of the current slide
* Embedded webcam preview inside the slide

### ✔️ **Annotation Management**

* Multiple strokes stored separately
* Undo / Redo stack
* Dynamic stroke creation

---

## 🧠 **How It Works**

1. **Hand detection:**
   Uses `cvzone.HandTrackingModule.HandDetector` to detect fingers up/down.

2. **Gesture recognition:**
   Finger patterns (e.g., `[0,1,1,0,0]`) map to actions like drawing, undo, redo, pointing, clear.

3. **Coordinate mapping:**
   The fingertip position is normalized and mapped to screen coordinates using interpolation.

4. **Drawing loop:**
   Each stroke is appended to an annotation list and drawn using OpenCV.

---


## 🛠️ **Tech Stack**

* **Python**
* **OpenCV (cv2)**
* **cvzone Hand Tracking**
* **NumPy**
* **Webcam / IP Webcam support**

---

## ⚙️ **Requirements**

Install required packages:

```bash
pip install opencv-python cvzone numpy
```

---

## ▶️ **How to Run**

1. Place your background images in the `presentation/` folder.
2. Update the folder path in the code if needed.
3. Run the script:

```bash
python scribble_game.py
```

4. Ensure your webcam is connected.

---

## 🎮 **Gesture Controls Summary**

| Gesture (Finger Pattern) | Meaning | Action                     |
| ------------------------ | ------- | -------------------------- |
| `[0, 1, 0, 0, 0]`        | Point   | Move cursor                |
| `[0, 1, 1, 0, 0]`        | Draw    | Start drawing              |
| `[0, 0, 0, 0, 1]`        | Clear   | Erase all strokes          |
| `[0, 1, 1, 1, 0]`        | Undo    | Remove last stroke         |
| `[0, 1, 1, 1, 1]`        | Redo    | Restore last undone stroke |

---

## 🎯 **Future Improvements**

* Add color palette for drawing
* Save drawings as images
* Multi-hand gesture support
* Hand-free slide navigation
* Air-writing recognition


