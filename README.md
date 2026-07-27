# 1-1-1 Dagan — Patintero

A digital reimagining of **Patintero**, the classic Filipino street game (also known as *Tubigan*, *Iring-iring*, *Silatong*, *Lawin-lawin*). A guarded grid of chalk lines stands between you and home free. Slip past the taya, dodge every line they patrol, and cross the yard three times before the clock — or your luck — runs out.

## Screens

### Home
- Branded hero with animated logo and eyebrow tag
- Role cards explaining Runner, Guards, and the stakes
- Info strip with key numbers (3–8 guards, 3 crossings, 3 tags, 7–11 yard size)
- Lore section explaining the game's cultural history
- Quick-action buttons: **Play Now** and **How It's Played**

### Setup
- **Face-off panel** choosing your runner avatar vs. the CPU guards
- Tap to open the **Avatar Picker Modal** (24 runner faces from `assets/sideA/`)
- **Surprise Me** button triggers the *Bahala Na!* random-avatar animation
- **Randomize Guards** assigns unique guard faces from `assets/sideB/`
- **Difficulty grid**: Palusot, Sige Tara!, Taya Ka Diyan!, Bahala Na! — each tuned with different guard speed, AI bias, and time bonuses
- **Court size toggle**: Munti (7×7), Katamtaman (9×9), Malaki (11×11)
- **Guard count stepper**: 3–8 guards
- **Court background gallery**: auto-detects images dropped into `assets/grounds/` (named `ground (1).png`, etc.)

### Game
- **HUD** showing Crossings (0/3), Tags (0/3), Heading (↑ Far Line / ↓ Home Line), and Time remaining
- **Timer bar** that shifts from gold to red under 20 seconds
- **Status line** that alerts on tags and confirms crossings
- **Game board** with chalk-line grid, home labels (FAR LINE / HOME LINE), and dashed guard lines
- **Guard legend** chips showing each guard's avatar and assigned line
- **On-screen D-pad** for touch devices
- **Control buttons**: Rules, New Round, Change Avatars

### Modals
- **Welcome / Intro**: quick 3-step onboarding with controls reminder
- **How to Play**: rules, controls (WASD / Arrow Keys / on-screen pad), and tips
- **About the Game**: history of Patintero, traditional setup, scoring, and cultural context
- **Win Modal**: confetti, finishing time, and Play Again
- **Lose Modal**: reason (tagged out or time ran out) and Try Again
- **Avatar Picker**: scrollable grid of runner faces; tap to select, auto-closes
- **Surprise Me**: spinning animation landing on a random runner

## Features

| Feature | Detail |
|---|---|
| **Player avatars** | 24 faces from `assets/sideA/sideA (1).png` … `sideA (24).png` |
| **Guard avatars** | 20 faces from `assets/sideB/sideB (1).png` … `sideB (20).png` |
| **Custom court grounds** | Drop any image into `assets/grounds/ground (1).png` (also supports `.jpg`, `.jpeg`, `.webp`) |
| **Theme** | Light / dark toggle with full color-token swap |
| **Responsive** | Hamburger nav below 860px; D-pad appears below 760px |
| **Difficulty** | Guard tick speed: 860ms → 340ms; AI bias: 0.42 → 0.90; time bonus: +20s → −20s |
| **Court sizes** | 7×7 (base 90s), 9×9 (115s), 11×11 (141s) |

## Controls

- **W / A / S / D** or **Arrow Keys** — move one tile at a time
- **Touch devices** — on-screen D-pad appears automatically
- **Esc** — close any open modal
- Click outside a modal to close it

## Game Rules

1. You are the **Runner (Tumatakbo)**. Start at HOME LINE.
2. CPU **Guards (Taya)** patrol their assigned chalk lines and cannot leave them.
3. Move tile-by-tile to the FAR LINE (up) and back to HOME LINE (down).
4. Each full crossing counts as **1**. Complete **3 crossings** to win.
5. Landing on the same tile as a guard counts as a **tag**.
   - 3 tags = eliminated.
6. The timer reaches zero before 3 crossings = time out.
7. Getting tagged resets you to your home line.

## Running the App

No build step or server is required. Open `index.html` directly in any modern browser.

```text
index.html
web_icon.png
assets/
  sideA/    (runner avatars)
  sideB/    (guard avatars)
  grounds/  (optional custom court backgrounds)
```

## Tech Stack

- Pure HTML / CSS / JavaScript (no framework, no dependencies)
- Google Fonts: *Baloo 2* and *Nunito Sans*
- CSS custom properties for theming
- CSS Grid and Flexbox for layout
- requestAnimationFrame-free tile movement using CSS transitions

## Browser Support

Chrome, Firefox, Safari, Edge (latest two versions).
