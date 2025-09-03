
# Day 01 - Drum Kit 🥁

## 📌 Project Overview
A simple drum kit where each keyboard key (A, S, D, F, etc.) plays a different drum sound.  
Pressing a key also adds a visual effect to show which key was triggered.

This project is part of my [JavaScript30](https://javascript30.com/) journey.

---

## 🗂 File Structure
Day01-DrumKit/
│
├── index.html # main HTML file
├── style.css # styles for the drum kit layout and effects
├── script.js # JavaScript logic for playing sounds & animations
└── README.md # this file
and other required files like sounds and images


---

## 🧑‍💻 Key Learnings
Using data-* attributes
In the drum kit, we need to link a key (like A, S, D) with an audio file.
HTML allows custom attributes starting with data-

display: flex → make children flexible boxes.
justify-content: center → horizontal centering.
align-items: center → vertical centering.
min-height: 100vh → take full screen height.

Template literals `audio[data-key="${e.keyCode}"]` let us dynamically select the matching audio.
audio.currentTime = 0 ensures fast replay.
key.classList.add("playing") applies the CSS animation.

Problem Discovered: “Stuck Keys”
If you hold a key down, .playing sometimes stays applied.
Why? Because:
keydown keeps firing.
.playing is already added → transition doesn’t restart.
transitionend never fires again → so removal doesn’t happen.

what i do:- window.addEventListener("keyup", removePlaying);

---

## 🎮 How to Run
1. Open `index.html` in your browser.  
2. Press the keys **A, S, D, F, G, H, J, K, L** on your keyboard.  
3. Each key will play a different drum sound and briefly highlight the button.

---
=======

