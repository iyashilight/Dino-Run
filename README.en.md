# Dino Run

> [中文](README.md) | **English**

A pixel-art endless runner inspired by Chrome's offline dinosaur, written entirely in the browser.

It is a **single HTML file** — no dependencies, no build step — and can be deployed straight to GitHub Pages.

🎮 **Play online**: <https://iyashilight.github.io/Dino-Run/>

---

## Features

- **Two game modes**
  - Runner: the classic endless run — dodge cacti and birds
  - Explore: side-scrolling exploration where you move left/right and fight shooting enemies; each mode tracks its own high score
- **Three difficulties**: Easy (3 lives), Normal (2 lives), Hard (1 life) — each with its own base speed, obstacle spacing and enemy strength
- **Invincible mode**: collision immunity and free flight, handy for practice
- **Speed control**: a slider scales overall speed from x0.5 to x2.0, and hotkeys can boost or slow it on the fly
- **Pixel HUD**: lives, score, high score (HI) and current speed
- **Local high scores**: stored per mode in `localStorage`
- **Keyboard + touch**: on-screen move/shoot buttons appear on mobile

## Controls

| Input | Action |
| --- | --- |
| `Space` / `↑` / `W` | Jump (double jump supported; hold to keep rising in invincible mode) |
| `←` `→` / `A` `D` | Move left / right (explore mode) |
| `J` / `F` / tap "Shoot" | Shoot (explore mode) |
| `Shift` / `Ctrl` | Temporary speed up / down |
| `CapsLock` | Fast fall |
| `P` | Pause / resume |
| `Space` / tap after game over | Restart |

## Running locally

No dependencies are required — just open `index.html` in a browser. Or serve it statically:

```bash
git clone git@github.com:iyashilight/Dino-Run.git
cd Dino-Run
python3 -m http.server 8000
# open http://localhost:8000
```

## Project layout

```text
.
├── index.html    # the whole game (HTML + CSS + JS in one file)
├── LICENSE       # GPL-3.0
└── README.md
```

## Implementation notes

- Vanilla **HTML5 Canvas 2D + JavaScript + CSS**, no third-party libraries
- `requestAnimationFrame` loop with delta-time stepping, so the game feels the same at any refresh rate
- Double jump with jump buffering and coyote time
- Jump impulse scales with the speed multiplier, keeping the jump arc consistent at any speed
- Procedurally generated obstacles and enemies, with difficulty ramping up as you progress
- Responsive canvas, works on desktop and touch devices

## License

Released under [GPL-3.0](LICENSE).
