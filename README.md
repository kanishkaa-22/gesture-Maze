# 🖐 GestureMaze — Webcam-Controlled Maze Game

**GestureMaze** is a futuristic, touchless maze game where players control movement using **hand gestures via webcam** instead of a mouse or keyboard.

Navigate through increasingly difficult mazes using natural hand motions like **tilt, pinch, and zoom** — creating a unique Human-Computer Interaction experience.

---

## 🎮 Demo

🔗 Live: https://magic-maze.vercel.app

---

## 🌟 Features

### 🖐️ Gesture Controls

* **Tilt Hand** → Move the ball
* **Pinch (🤏)** → Select / Confirm
* **Two-Hand Zoom (🤲)** → Zoom in/out
* **Open Palm (✋)** → Pause / Resume

### 🎮 Gameplay

* Multiple difficulty levels (Easy → Chaos 💀)
* Real-time physics-based movement
* Collision detection with walls
* Timer + Score system
* High score tracking (localStorage)

### 🎨 Visual Experience

* Neon cyberpunk UI design
* Particle effects & glow animations
* Smooth transitions and HUD
* Responsive canvas rendering

---

## 🧠 Technologies Used

| Technology      | Purpose              |
| --------------- | -------------------- |
| HTML5 Canvas    | Game rendering       |
| JavaScript      | Game logic           |
| MediaPipe Hands | Gesture detection    |
| WebRTC          | Webcam access        |
| CSS (Neon UI)   | Styling & animations |
| Web Audio API   | Sound effects        |

---

## 🕹️ How to Play

1. Click **"Grant Camera Access"**
2. Allow webcam permission
3. Select a level using:

   * 👆 Pinch gesture or mouse
4. Control the ball:

   * Tilt your hand to move
   * Avoid walls
   * Reach the glowing goal ⭐

---

## 🧩 Project Structure

```
magic-maze/
│
├── index.html        # Main game file
├── README.md         # Documentation
└── assets/           # (optional images/sounds)
```

---

## ⚠️ Requirements

* Modern browser (Chrome recommended)
* Webcam access enabled
* Internet (for MediaPipe CDN)

---

## 🎓 CGA Concepts Used

This project demonstrates key **Computer Graphics and Animation** concepts:

* 2D Rendering (Canvas)
* Real-time Animation (requestAnimationFrame)
* Transformations (translation, scaling/zoom)
* Collision Detection
* Procedural Maze Generation
* Interactive Graphics (gesture input)
* Particle Systems & Visual Effects

---

## 🔮 Future Improvements

* 🧊 3D Maze using Three.js
* 🤖 AI-based difficulty adaptation
* 🏆 Online leaderboard
* 📱 Mobile gesture support
* 🎭 Character/Theme switching

---

## 👩‍💻 Author

**Kanishkaa**
First-Year CSE Student
Passionate about AI, Graphics & Interactive Systems 🚀

---

## ⭐ Support

If you like this project:

⭐ Star this repo
🍴 Fork it
📢 Share it

---

## 📜 License

MIT License
|---|---|
| `←` `→` `↑` `↓` | Move ball |
| `P` | Pause / Resume |

---

## 📐 How Gesture Detection Works

- Uses **MediaPipe Hands** loaded from CDN (no install needed)
- Detects up to 2 hands with 21 landmarks each
- **Tilt**: Vector from wrist to average knuckle position mapped to velocity
- **Pinch**: Euclidean distance between thumb tip and index tip (threshold: 0.06)
- **Palm open**: Average finger spread from wrist (threshold: 0.25)
- **Zoom**: Distance between centers of both detected hands (delta → zoom factor)

---

## 🏗 Architecture

```
index.html          ← All-in-one (HTML + CSS + JS)
│
├── Gesture Engine  ← MediaPipe Hands, landmark drawing, gesture classifier
├── Game Loop       ← requestAnimationFrame, physics, collision detection
├── Maze Builder    ← Recursive backtracking algorithm (seeded per level)
├── Renderer        ← HTML5 Canvas with neon glow effects
├── Sound Engine    ← Web Audio API procedural sounds
└── Particle System ← Trail and celebration effects
```

---

## 🧩 Levels

| # | Name | Grid | Time | Difficulty |
|---|---|---|---|---|
| 1 | EASY | 9×9 | 120s | ⭐ |
| 2 | MEDIUM | 13×13 | 90s | ⭐⭐ |
| 3 | HARD | 17×17 | 70s | ⭐⭐⭐ |
| 4 | EXPERT | 21×21 | 55s | ⭐⭐⭐⭐ |
| 5 | MASTER | 25×25 | 40s | 💀 |

---

## ⚙️ Settings

- **Sensitivity slider** (top-right in game): Adjusts gesture-to-velocity mapping (1–10)
- **Hide/Show Cam** button: Toggle the webcam preview panel
- High scores are saved automatically in `localStorage`

---

## 🌐 Browser Compatibility

| Browser | Gesture | Keyboard |
|---|---|---|
| Chrome 90+ | ✅ | ✅ |
| Edge 90+ | ✅ | ✅ |
| Firefox | ⚠️ MediaPipe may be slower | ✅ |
| Safari | ❌ MediaPipe not supported | ✅ |

---

## 💡 Tips

- Keep your hand **clearly visible** and well-lit for best tracking
- Use **small, deliberate tilts** — the game uses smooth interpolation
- The **red timer** flashes when under 10 seconds
- Pinch is **cooldown-gated** (0.5s) to prevent accidental repeats
