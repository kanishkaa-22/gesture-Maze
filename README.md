# 🖐 GestureMaze — Webcam-Controlled Maze Game

Control a glowing ball through neon mazes using only your hand gestures via webcam.

---

## 🚀 Quick Start

**Just open `index.html` in Chrome or Edge** — no build step, no server needed.

> ⚠️ Camera access requires a browser that supports `getUserMedia`. Chrome/Edge recommended.

---

## 🎮 Controls

### Hand Gestures (primary)
| Gesture | Action |
|---|---|
| **Hand Tilt** | Tilt your palm left/right/up/down → ball rolls in that direction |
| **Pinch** (thumb + index) | Confirm selection on menus / dismiss overlays |
| **Open Palm** (5 fingers spread) | Pause / Resume the game |
| **Two-Hand Zoom** | Spread both hands apart → zoom in · bring together → zoom out |

### Keyboard (fallback)
| Key | Action |
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
