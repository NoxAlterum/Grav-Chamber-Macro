# Gravity Chamber Macro

A screen-reading macro tool for automating WASD key sequences in the Gravity Chamber training minigame.

## Created by Chrissy

---

## How It Works

This tool watches a specific area of your screen for W, A, S, D letters and automatically presses the corresponding keys. It detects when the sequence turns green (correct) or red (incorrect) and resets for the next round.

---

## Setup

### 1. Download and Extract

Extract the zip file to any location on your computer. You should have:

```
Gravity Chamber Macro/
├── WASD Reader.exe
├── README.md
└── templates/
    ├── w.png
    ├── a.png
    ├── s.png
    └── d.png
```

### 2. Template Images

The `templates` folder contains images of each letter (W, A, S, D) that the program uses to recognize on-screen text.

**If detection isn't working well**, you may need to create your own templates:
1. Take a screenshot of the letters in your game
2. Crop each letter tightly
3. Save as `w.png`, `a.png`, `s.png`, `d.png` in the templates folder

**For different letter sizes**, you can add variants:
- `w2.png`, `w3.png`, `w4.png`
- `a2.png`, `a3.png`, `a4.png`
- etc.

---

## How to Use

1. **Run** `WASD Reader.exe`

2. **Check Templates** - Make sure it says "Loaded: A, D, S, W" in green

3. **Click "Show Selector"** - A blue box appears on screen

4. **Position the selector** over where the letters appear in the game
   - Drag from anywhere to move
   - Drag the corner to resize

5. **Click "Hide Selector"** when positioned (optional - it can stay visible)

6. **Select a Preset** based on what you're training:
   | Preset | Reset Time | Cooldown |
   |--------|------------|----------|
   | Default | 0.50s | 25ms |
   | Health | 0.90s | 25ms |
   | Agility | 0.80s | 25ms |
   | Ki Control | 0.75s | 25ms |
   | Physical Damage | 0.80s | 25ms |
   | Ki Damage | 1.15s | 1150ms |

7. **Press F6** to start the macro

8. **Press F6** again to stop

---

## Controls

- **F6** - Start/Stop the macro (can be changed in the app)
- **Show Selector** - Display the region selector
- **Hide Selector** - Hide the selector (Will not continue scanning if hidden)
- **Typing Cooldown** - Adjust delay between typing sequences

---

## Troubleshooting

### Allow Space for the Letters
- Sometimes the program will have issues detecting the letter D if the sizer is to tight to the letter.
- Allow some blue background, it won't hurt.

### "Templates missing!"
- Make sure the `templates` folder is in the same location as the .exe
- Make sure files are named exactly: `w.png`, `a.png`, `s.png`, `d.png` (lowercase)

### Letters not being detected
- Retake template screenshots from your actual game
- Crop the images tightly around each letter
- Try adding variant images (w2.png, etc.) for different sizes

### Wrong letters detected / duplicates
- Make sure template images only contain one letter each
- Crop more tightly around the letters

### Keys not working in game
- Run the .exe as Administrator (right-click → Run as administrator)
- Make sure the game window is focused when the macro is running

### Typing too fast / too slow
- Adjust the Typing Cooldown value
- Try a different preset

---

## Notes

- This tool uses DirectInput for key presses, which works with most games
- Some games with anti-cheat may block automated inputs
- The selector region is saved when hidden, so detection continues working

---

## Requirements

- Windows 10/11
- No installation required - just run the .exe

---

## Disclaimer

Use at your own risk. This tool is for personal use to assist with repetitive gameplay. The creator is not responsible for any consequences from using this software.

---

**Enjoy your training!** 💪
