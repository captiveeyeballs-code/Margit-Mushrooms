# 🐍 Margit Island Snake

A chaotic two-snake game with mushrooms, poop trails, and Rita the hazard character. Fully offline, no dependencies, single static HTML file.

## What Is This

Two snakes — **Jay** and **Dani** — compete to eat mushrooms on Margit Island. Every 15 seconds, **Rita** storms across the screen dropping poop behind her. Eat mushrooms to grow, dodge Rita and her trail, and outlast your opponent.

**Characters:**
- 🐍 **Jay** — Blue snake, Arrow key controls (or swipe on mobile)
- 🐍 **Dani** — Orange snake, WASD controls
- 👧 **Rita** — Pixel-art animated hazard, always "Psycho" speed, drops multiple 💩 per pass

## How to Run Locally

Just open `index.html` in any modern browser — Chrome, Firefox, Safari, Edge.

```
double-click index.html
```

No server required. No build step. No internet needed after download.

## How to Host Online

### Netlify (easiest — drag & drop)
1. Go to [app.netlify.com](https://app.netlify.com)
2. Drag the entire project folder onto the deploy zone
3. Done — get a shareable link instantly

### GitHub Pages
1. Push this folder to a GitHub repo
2. Go to **Settings → Pages**
3. Set source to `main` branch, root `/`
4. Your game is live at `https://yourusername.github.io/repo-name/`

### Vercel
1. Install Vercel CLI: `npm i -g vercel`
2. Run `vercel` inside this folder
3. Follow prompts — it'll deploy as a static site

### Any Static Host
Upload the folder contents as-is. The entry point is `index.html`.

## Folder Structure

```
/
├── index.html          ← Main game (everything self-contained)
├── img/
│   ├── margit-map.jpg  ← Background map image
│   ├── jay.jpg         ← Jay's face (used as snake head)
│   └── dani.jpg        ← Dani's face (used as snake head)
└── README.md
```

## Controls

| Action | Jay | Dani |
|--------|-----|------|
| Move | Arrow Keys | WASD |
| Mobile | Swipe / D-pad | — |
| Pause | P | P |
| Restart | R | R |
| Start | Space / Enter | — |

## Game Rules

- **Mushroom** 🍄 → +1 score, snake grows by 1
- **Hit wall** → game over (you lose)
- **Hit yourself** → game over
- **Hit other snake** → game over for the one who crashes
- **Head-on collision** → both lose (draw)
- **Hit Rita** → instant game over
- **Hit poop** 💩 → lose 1 body segment (if only 1 segment left = game over)
- **Rita** appears every 15 seconds, always fast (Psycho mode), drops multiple poops
- Poops linger on screen for 5 seconds after Rita leaves, then fade out
- High scores saved in browser localStorage

## Modes

- **Single Player: Jay** — You play Jay (arrows), Dani is competitive AI
- **Single Player: Dani** — You play Dani (WASD), Jay is competitive AI
- **Two Player** — Both human, keyboard only (swipe controls Jay on mobile)

## Speed Levels

| Level | Tick Rate |
|-------|-----------|
| Stoned | 7 Hz (slow) |
| High | 10 Hz (medium) |
| Super High | 14 Hz (fast) |

## What Changed in This Version

| Feature | Change |
|---------|--------|
| Rita visual | Replaced white box with animated pixel-art sprite (angry girl, 4-frame walk cycle) |
| Snake heads | Upgraded from 20px thumbnail to 60px cropped face portrait with glow |
| Snake body | Improved rendering with gradient alpha, shine, better outline |
| Audio | Added mushroom spawn chime, poop-hit splat sound, improved pickup sound |
| Mobile controls | Swipe on canvas + on-screen D-pad (auto-shown on touch devices) |
| Responsive | Canvas scales to fit any screen using CSS transform |
| Mushrooms | Increased to 2 simultaneous mushrooms + pop-in spawn animation |
| AI | Now also avoids known poop locations during pathfinding |
| Poop system | Drop interval tightened (0.15–0.28s), max poops raised to 150 |
| File structure | Images moved to `/img/` folder for clean project layout |

## Credits

Built as a self-contained HTML5 Canvas game. All audio synthesized via Web Audio API — no external files needed.
