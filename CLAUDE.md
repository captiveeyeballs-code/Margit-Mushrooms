# Margit Mushroom Adventures — Project Handoff

## What this is
A self-contained offline HTML5 Canvas snake game set on Margit Island.
Two snakes (Jay & Dani) compete to eat mushrooms while dodging Rita and befriending Chipy.
No build tools, no dependencies — everything is plain HTML/JS/CSS in a single file per version.

## Repo
- GitHub: `github.com/captiveeyeballs-code/Margit-Mushrooms`
- Live: `https://margitmushrooms.netlify.app` (deployed via Netlify drag-and-drop)

## Git / SSH setup
SSH is fully configured — terminal can push to GitHub directly, no GitHub Desktop needed.
If pushing fails after a reboot, run: `ssh-add ~/.ssh/id_ed25519` then try again.

```bash
cd /Users/javadsahami/Documents/GitHub/Margit-Mushrooms
git add <file>
git commit -m "your message"
git push origin main
```

## Files
| File | Status | Notes |
|---|---|---|
| `index.html` | ✅ Live | Routes mobile vs desktop automatically |
| `desktop.html` | ✅ Live | Current desktop version — leave alone, it's good |
| `mobile.html` | ✅ Live | Active mobile version — main focus of development |
| `CLAUDE.md` | 📋 This file | Update at end of each session |
| `margit-snake.html` | 🗑 Legacy | Old monolith — ignore |

## Characters
| Character | Role | Controls |
|---|---|---|
| Jay | Blue snake | Arrow keys (desktop) / swipe right half (mobile) |
| Dani | Orange snake | WASD (desktop) / swipe left half (mobile) |
| Rita | Hazard — crosses screen every 15s, drops 💩 poops | N/A |
| Chipy | Helper — crosses screen occasionally, drops 🎂 cakes | N/A |

## Game rules
- Eating a mushroom: +1 score, +1 body segment
- Hitting a 💩 poop: -1 score (min 0) + shrink by 1 segment (if length 1, die)
- Eating a 🎂 cake (Chipy's): halves body length, keeps score
- Hitting Rita directly: die
- Hitting a wall, yourself, or the other snake: die
- Winner = last snake standing (not highest score)

## Mobile speed settings (current)
| Setting | Tick rate |
|---|---|
| Stoned | 6 Hz |
| High (default) | 9 Hz |
| Super High | 12 Hz |

Rita speed: `(snakePxSpeed * 0.5) * 2.6 * 0.5625`
Chipy speed: `(snakePxSpeed * 0.5) * 1.3 * 0.75`

## What's been done
- SSH push configured — terminal pushes to GitHub directly, no GitHub Desktop needed
- CLAUDE.md created for session handoffs
- **Mobile walls restored** — hitting any edge is fatal (was Pac-Man wrap-around)
- **AI pathfinding updated** to treat walls as deadly
- **Snake speed slowed ~15%** across all three settings
- **Rita slowed 25%**
- **Chipy made 15% smaller** (display 240×160 → 204×136)
- **AI cake fairness** — AI prioritises mushrooms after eating first cake per Chipy visit
- **Poop hits now deduct 1 point** (min 0) — both mobile and desktop
- **Chipy alert text** set to "🧁 Chipy made cakes! 🧁" (fits mobile screen without wrapping)

## How to deploy
Drag the entire `Margit-Mushrooms` folder onto [app.netlify.com](https://app.netlify.com).

## End of session checklist
- [ ] All changes committed and pushed to GitHub
- [ ] CLAUDE.md updated with what changed
