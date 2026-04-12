# Magic-Maze
"A web-based maze game controlled by hand gestures using a webcam, replacing traditional mouse and keyboard inputs."

A touchless, interactive maze game that uses **hand gestures captured through a webcam** to control gameplay. Instead of using a mouse or keyboard, players navigate a ball through the maze using intuitive gestures such as **hand tilt**, **pinch**, and **two-hand zoom**.

---

## 🌟 Features

- 🖐️ **Gesture-Based Controls**
  - **Hand Tilt** – Move the ball in the maze.
  - **Pinch Gesture** – Select levels and restart the game.
  - **Two-Hand Zoom** – Zoom in and out of the maze view.

- 🎮 **Interactive Gameplay**
  - Multiple maze levels with increasing difficulty.
  - Collision detection with maze walls.
  - Goal detection and level completion.
  - Score and timer display.

- 📷 **Webcam Integration**
  - Real-time hand tracking using **MediaPipe Hands**.
  - Optional webcam preview for user feedback.

- 💻 **Modern Web Technologies**
  - Built using **HTML**, **CSS**, and **JavaScript**.
  - Rendering with **HTML5 Canvas** (or Three.js for 3D).
  - Gesture recognition powered by **MediaPipe**.

---

## 🛠️ Technologies Used

| Technology | Purpose |
|------------|---------|
| HTML5 & CSS3 | User Interface |
| JavaScript | Game Logic |
| MediaPipe Hands | Hand Gesture Recognition |
| WebRTC (`getUserMedia`) | Webcam Access |
| HTML5 Canvas / Three.js | Graphics Rendering |

---

## 🎯 How It Works

1. The webcam captures real-time video using `getUserMedia`.
2. **MediaPipe Hands** detects hand landmarks.
3. Gestures are interpreted:
   - Tilt → Ball movement.
   - Pinch → Selection/Click.
   - Two-hand distance → Zoom in/out.
4. The game logic updates the ball’s position and checks for collisions.
5. The player completes the level by reaching the goal.

---

## 🚀 Getting Started

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/your-username/gesture-controlled-maze.git
cd gesture-controlled-maze
