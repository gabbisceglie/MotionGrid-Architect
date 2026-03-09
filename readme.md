# MotionGrid Architect v1.0

Interactive web application that uses **webcam + MediaPipe Hands** to draw and manipulate a grid of squares in real-time with hand gestures.

## What the program does

- Shows the webcam feed as the background.
- Recognizes up to **2 hands** simultaneously.
- Displays a hand skeleton with an enhanced "cyber" style, improved with gradients and animated glows.
- Draws an overlaid luminous grid (mesh).
- Allows creating, moving, and deleting grid squares using gestures.
- Active squares have improved visual effects with pulsing glow and highlighted corners.
- Shows circular loading indicators when a gesture requires a long press.

## Gestures to use

Gestures are recognized based on the fingers detected by MediaPipe.

1. **Pinch (thumb + index grip)**
- Action: immediately adds a square in the grid cell under the index finger.

2. **Maintained Pinch (~1 second)**
- Action: activates continuous drawing mode.
- Result: while holding the pinch, squares are added along the movement of the finger.
- Visual feedback: light blue loading ring.

3. **Fist**
- Action: moves all previously created squares as a block.
- Result: squares move in cell "steps" following the movement of the palm.

4. **Deletion (2-hand combo)**
- Required gesture: one hand in a **fist** + the other in a **pinch** held together for ~1.2 seconds.
- After activation: move the pinch finger over squares to delete them.
- Visual feedback: red ring during loading and red UI state in deletion mode.

## Interface

- **Hide/Show grid**: toggles the visibility of the luminous mesh.
- **Clear squares**: shows a reminder of the correct deletion gesture (does not directly delete all squares).

## Requirements

- Modern browser with `getUserMedia` support.
- Internet connection to load MediaPipe libraries from CDN.
