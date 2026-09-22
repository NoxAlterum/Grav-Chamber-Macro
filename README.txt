# Grav Chamber Macro v2

Created by Chrissy

Plays the three training minigames for you by watching the screen:

| Preset           | Minigame      | What it does                                                   |
|------------------|---------------|----------------------------------------------------------------|
| Health           | Timing bar    | Presses F as the red cursor crosses the middle of the green zone |
| Physical/Agility | WASD letters  | Reads the letters (repeats included, e.g. W-W-D-A-S) and types them |
| Ki               | Circles       | Clicks each circle for a "Perfect!" as its white ring closes onto it |

Works in the Gravity Chamber and the Hyperbolic Time Chamber, at any screen resolution
(720p to 4K), any Windows display scaling (100%, 150%, 200%...), on any monitor, and with the
game at 30 or 60 fps. Health and Ki measure your PC's lag as they play and correct their own
timing. There's a dark mode too (button at the bottom right).

---

## Setup

Keep these together in one folder:

```
Grav Chamber Macro/
├── Grav Chamber Macro.exe   (or Grav_Chamber_Macro.py)
├── README.txt
└── templates/
    ├── w.png  a.png  s.png  d.png
    └── (variants like w2.png, d3.png)
```

The letter templates only need to show the letter's shape, so they work at every resolution.
You don't need to make your own.

Running the .py instead of the .exe needs Python 3.10+ and:

    pip install -r requirements.txt

---

## How to use

1. In Roblox, walk into the training so its UI is showing.
2. Click the preset for that training (Health, Physical/Agility or Ki).
3. Click **Select Region (Drag)** and drag a box:
   - **Health:** over the bar with the green zone and red cursor.
   - **Physical/Agility:** around the row where the letters appear, wide enough for 5 letters.
     Leave a little of the navy box around them.
   - **Ki:** around the whole square the circles appear in.
4. Check the preview. The line under it says what the macro sees ("Sees: W S A D A (white)",
   "Sees: bar | green zone yes | red cursor yes", "Sees: 1 circle(s), 1 with a ring").
   If it doesn't see the game, drag the region again.
5. Click back into Roblox and press **F6** to start. Press **F6** again to stop.

Each preset remembers its own region, and all settings are saved for next time.

---

## Settings

**Physical/Agility**
- *Letter match* (default 0.60): how closely a shape must match a letter. Real letters score
  0.8-1.0, so you should never need to change it.
- *Key gap* (default 30 ms): pause between letters. Raise it if the game drops letters.
- *Wait before typing* (default 40 ms): letters must hold still this long before typing,
  so a sequence is never typed while it's still appearing.

**Health**
- *Press lead* (default 35 ms): the starting guess for your lag. The macro watches where the
  cursor stops on every hit and corrects itself. The status line shows "lead now ... ms".
  If it keeps missing, it tries other timings until it hits again.

**Ki**
- *Click lead* (default 25 ms): the starting guess for your lag. After every click the macro
  sees exactly when the game took it and corrects itself within a few clicks. The status line
  shows "timing ... ms".

For both, the timing it learned is saved when you stop, so the next session starts calibrated.
You normally never need to touch these.

**Start/Stop hotkey:** type a key (f6, f8, ctrl+q...) and click Set.

---

## Troubleshooting

**The preview shows the wrong spot or "Sees: no ..."**
Drag the region again with the training UI on screen.

**Keys or clicks don't reach the game**
Make sure Roblox is the focused window. If Roblox was started as administrator, run the macro
as administrator too (right-click → Run as administrator).

**Health presses land early or late**
Give it a few presses to calibrate. If it's still off, change *Press lead* by 10-20 ms.

**Ki clicks get "Okay." instead of "Perfect!"**
Give it a few clicks to calibrate. If it's still off, change *Click lead* by 10 ms at a time.

**Physical/Agility types the wrong letter**
Check what the preview says it sees. If a letter is misread, the game's font may have changed.
Crop a screenshot tightly around that letter and save it in templates/ as w4.png, a4.png, etc.

---

## Notes

- Settings are saved in grav_config.json next to the program (or in
  %APPDATA%\GravChamberMacro if that folder can't be written to).
- Keys are sent with DirectInput, which Roblox accepts.

## Disclaimer

Automating gameplay may be against Roblox's or the game's rules and could get an account
punished. Use it at your own risk. The creator isn't responsible for what happens to accounts
that use it.
