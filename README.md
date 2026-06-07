# 🌸 Interactive Flower — TouchDesigner

> *Inspired by Max Cooper's [Order from Chaos](https://www.youtube.com/watch?v=_2BE2e4oGLA), with visuals by Maxime Causeret.*

An interactive generative flower built in **TouchDesigner**, combining procedural L-system geometry with real-time **MediaPipe** hand tracking. The flower responds to your body — move your hands and watch it bloom.

---

## ✨ About the Project

I wanted to explore how something as mathematically rigid as an L-system can still feel organic and alive when it becomes responsive to the human body. There was a lot of trial and error in finding the right balance — mapping hand gestures to something expressive rather than mechanical.

The plants and flowers are modeled directly in TouchDesigner using SOPs, grown with the **L-Systems SOP**, and brought to life through **MediaPipe** hand tracking integration.

---

## 📁 File Structure

```
InteractiveFlower/
├── InteractiveFlower.gradientbg.toe   ← Main file (gradient background variant)
├── InteractiveFlower.normalcam.toe    ← Main file (normal camera variant)
├── toxes/
│   ├── MediaPipe.tox                  ← Core MediaPipe component (hand/face/pose tracking)
│   ├── hand_tracking.tox              ← Hand tracking module
│   ├── face_tracking.tox              ← Face tracking module
│   ├── face_detector.tox              ← Face detector
│   ├── face_filter_example.tox        ← Face filter example
│   ├── face_mapping_example.tox       ← Face mapping example
│   ├── pose_tracking.tox              ← Pose tracking module
│   ├── object_tracking.tox            ← Object tracking module
│   ├── image_classification.tox       ← Image classification module
│   └── image_embeddings.tox           ← Image embeddings module
└── Backup/
    ├── InteractiveFlower.2.toe
    ├── InteractiveFlower.3.toe
    └── InteractiveFlower.4.toe        ← Iteration backups
```

---

## 🚀 Getting Started

### Requirements

- **TouchDesigner** 2022.x or newer (free non-commercial license works)
  - Download: [derivative.ca/download](https://derivative.ca/download)
- A **webcam** (built-in or external) — used for hand tracking via MediaPipe
- Windows or macOS

### How to Open

1. Clone or download this repository.
2. Open either `.toe` file in TouchDesigner:
   - `InteractiveFlower.gradientbg.toe` — version with gradient background
   - `InteractiveFlower.normalcam.toe` — version with normal camera passthrough
3. Make sure your webcam is connected and accessible.
4. Press **F1** (or the Play button) to enter **Perform Mode** and see the full experience.

### Using the Toxes

The `toxes/` folder contains pre-built MediaPipe components. These are already referenced inside the `.toe` files. If TouchDesigner can't find them, use `File > Palette` to locate and drag them in, or re-link them via their parameters.

---

## 🤲 Interaction

| Gesture | Effect |
|---|---|
| Move hands toward camera | Flower blooms / expands |
| Move hands away | Flower retracts |
| Hand position (X/Y) | Controls direction and sway |
| Spread fingers | Affects branch density / spread |

> *Gestures may vary slightly depending on the specific `.toe` version. Explore the hand_tracking CHOP channels inside the file to see what's being tracked and how it maps.*

---

## 🛠 How It Works

### L-Systems SOP
TouchDesigner's built-in **L-Systems SOP** generates recursive, fractal-like plant geometry using string rewriting rules. By animating the parameters (angle, length, iterations), the plant appears to grow and respond organically.

### SOP Modeling
Additional flower and petal shapes are modeled using a chain of SOPs (geometry operators) — Sphere, Torus, Transform, Copy, and more — assembled to form petals, stems, and stamens.

### MediaPipe Hand Tracking
The **MediaPipe.tox** component runs a machine learning hand landmark model inside TouchDesigner. It outputs 21 hand joint positions as CHOP channels, which are then mapped to flower parameters like scale, rotation, and branch spread — making the flower react to your hands in real time.

---

## 📚 Tutorials That Helped

This project was shaped by a lot of learning from others. Highly recommend checking these out:

- 🌿 [Procedural Plants with L-Systems in TouchDesigner](https://www.youtube.com/@prismatic.visuals) — **@prismatic.visuals**
- 🌺 [Modeling Plants + Flowers in TouchDesigner](https://www.youtube.com/@aforestsociety) — **@aforestsociety**
- 🤚 [Hand Tracking in TouchDesigner](https://www.youtube.com/@blankensmithing) — **@blankensmithing**

And a huge thank you to **@blankensmithing** — my best TD teacher ♡♡♡

Special inspiration from **@peipeiatesouls** 💫

---

## 🎨 Inspiration

> *"Order from Chaos"* — Max Cooper ft. visuals by Maxime Causeret.
> The idea that rigid mathematical rules can produce something that feels alive, beautiful, and almost emotional is what drove this project.

---

## 📄 License

This project is shared freely for learning and creative exploration. Please credit if you build on it. ✨
