# Margit Mushroom Adventures — Project Handoff

## What this is
A self-contained offline HTML5 Canvas snake game set on Margit Island.
Two snakes (Jay & Dani) compete to eat mushrooms while dodging Rita and befriending Chipy.
No build tools, no dependencies — everything is plain HTML/JS/CSS in a single file per version.

## Repo
- GitHub: `github.com/captiveeyeballs-code/Margit-Mushrooms`
- Live: `https://margitmushrooms.netlify.app` (deployed via Netlify drag-and-drop)
- SSH is configured — pushing from terminal works directly, no GitHub Desktop needed.

## Files
| File | Status | Notes |
|---|---|---|
| `index.html` | ✅ Live | Routes mobile vs desktop automatically |
| `desktop.html` | ✅ Live | Current desktop version — leave alone, it's good |
| `mobile.html` | ✅ Live | Active mobile version — this is what we're working on |
| `margit-snake.html` | 🗑 Legacy | Old monolith — ignore |
| `CLAUDE.md` | 📋 This file | Update at end of each session |

## Characters
| Character | Role | Controls |
|---|---|---|
| Jay | Blue snake | Arrow keys (desktop) / swipe right half (mobile) |
| Dani | Orange snake | WASD (desktop) / swipe left half (mobile) |
| Rita | Hazard — crosses screen every 15s, drops 💩 | N/A |
| Chipy | Helper — crosses screen occasionally, drops 🎂 cakes | N/A |

## Game rules
- Eating a mushroom: +1 score, +1 body segment
- Hitting a 💩 poop: shrink by 1 segment (if length 1, die)
- Eating a 🎂 cake (Chipy's): halves your body length but keeps your score
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

## What's been done (this session)
- Fixed git sync issues (local was behind GitHub, lock files cleared)
- SSH push configured — terminal can now push to GitHub directly
- **Mobile walls restored** — hitting any edge is fatal (was Pac-Man wrap-around)
- **AI pathfinding updated** to treat walls as deadly
- **Snake speed slowed ~15%** across all three settings
- **Rita slowed 25%**
- **Chipy made 15% smaller** (display size 240×160 → 204×136)
- **AI cake fairness fix** — AI prioritises mushrooms after eating its first cake per Chipy visit, giving human a fair shot at the second

## How to deploy
Drag the entire `Margit-Mushrooms` folder onto [app.netlify.com](https://app.netlify.com).

## How to push to GitHub
```bash
cd /Users/javadsahami/Documents/GitHub/Margit-Mushrooms
git add <file>
git commit -m "your message"
git push origin main
```

## End of session checklist
- [ ] All changes committed and pushed to GitHub
- [ ] CLAUDE.md updated with what changed
