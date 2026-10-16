# Grav Chamber Macro v2

Created by Chrissy

Plays the three training minigames for you by watching the screen:

| Preset           | Minigame      | What it does                                                         |
|------------------|---------------|----------------------------------------------------------------------|
| Health           | Timing bar    | Presses F as the white cursor crosses the middle of the gold zone     |
| Physical/Agility | WASD letters  | Types each letter as it turns white (repeats included, e.g. W-W-D-A)  |
| Ki               | Circles       | Clicks each circle for a "PERFECT" as its ring closes onto its edge   |

Works in the Gravity Chamber, the Hyperbolic Time Chamber (white or golden floor) and the
power-up mission's red-brown ground, at any screen resolution from 720p up, any Windows display
scaling (100%, 150%, 200%), on any monitor, and with the game at 30 or 60 fps. Health and Ki
measure your PC's lag as they play and correct their own timing. There's a dark mode too
(button at the bottom right).

Updated for the new training UI (October 2026).

---

## Setup

Keep these together in one folder:

```
Grav Chamber Macro/
├── Grav Chamber Macro.exe   (or Grav_Chamber_Macro.py)
├── README.txt
└── templates/
    └── w.png  a.png  s.png  d.png
```

The letter templates only hold each letter's shape, so the same four work at every resolution.
You don't need to make your own.

---

## How to use

1. In Roblox, walk into the training so its UI is showing.
2. Click the preset for that training (Health, Physical/Agility or Ki).
3. Set the region it watches:
   - **Health:** click **Find Bar**. It finds the timing bar on screen by itself and sets the
     region to fit it exactly. (Or drag a rough box around the bar - it snaps to the bar.)
     You can even skip this: started with no region, Health looks for the bar itself. And if
     the bar isn't where it used to be (the game window moved), it finds it again on its own.
   - **Physical/Agility:** click **Select Region (Drag)** and drag a box around the row where
     the letters appear - under "Progression", above "WASD or ARROW KEYS" - wide enough for
     5 letters.
   - **Ki:** click **Select Region (Drag)** and drag a box over the whole game. The circles
     can appear almost anywhere, so a box over the whole screen is the safe choice.
4. Check the preview. The line under it says what the macro sees ("Sees: S (white)",
   "Sees: bar | gold zone yes | white cursor yes", "Sees: 1 Ki circle(s)").
   If it doesn't see the game, set the region again.
5. Click back into Roblox and press **F6** to start. Press **F6** again to stop.

Each preset remembers its own region, and all settings are saved for next time.

---

## Settings

**Physical/Agility**
- *Letter match* (default 0.60): how closely a shape must match a letter. Real letters score
  0.8-1.0, so you should never need to change it.
- *Key gap* (default 30 ms): the shortest time between two letters.
- *Wait before typing* (default 40 ms): a letter must read the same for this long before it's
  typed, so a letter is never typed while it's still popping in.

A wrong key fails the round, so the macro only types the white letter, one at a time, and the
next one once the game has turned the last one green.

**Health**
- *Press lead* (default 35 ms): the starting guess for your lag. The macro watches where the
  cursor freezes on every hit and corrects itself. The status line shows "lead now ... ms".
  If it keeps missing, it tries other timings until it hits again.

**Ki**
- *Click lead* (default 25 ms): the starting guess for your lag. After every click the macro
  sees exactly when the game took it and corrects itself within a few clicks. The status line
  shows "timing ... ms".

The macro also reads the game's verdict after each click. If clicks keep coming out "GOOD"
instead of "PERFECT" (a floor that makes the circles hard to measure, say), it tries slightly
different timings until they're PERFECT again; the status line then shows "adjusted ... ms".
Every circle is clicked before it can time out, so there are no MISSes, and never so early
that it would be BAD. That includes a circle that appears right where the last one is still
fading out, one that's hidden for a moment by a popup or the LEVEL UP banner, and the moment
the screen darkens on a level up. The LEVEL UP banner's own numbers are never clicked.

For both, the timing it learned is saved when you stop, so the next session starts calibrated.
You normally never need to touch these.

**Start/Stop hotkey:** type a key (f6, f8, ctrl+q...) and click Set.

---

## Troubleshooting

**The preview shows the wrong spot or "Sees: no ..."**
Set the region again with the training UI on screen (for Health, just click Find Bar).

**Find Bar says it couldn't find the Health bar**
The bar has to be on screen when you click it: open the Health training first. If the
FAILED message is showing, wait for the bar to come back and click again.

**Keys or clicks don't reach the game**
Make sure Roblox is the focused window. If Roblox was started as administrator, run the macro
as administrator too (right-click → Run as administrator).

**Health presses land early or late**
Give it a few presses to calibrate. If it's still off, change *Press lead* by 10-20 ms.

**Ki clicks get "GOOD" instead of "PERFECT"**
Give it a few clicks: it calibrates itself. If it's still off after 10 or so, change
*Click lead* by 10 ms at a time.

**Physical/Agility types the wrong letter**
Check what the preview says it sees. If a letter is misread, the game's font may have changed.
Crop a screenshot tightly around that letter and save it in templates/ as w2.png, a2.png, etc.

---

## Notes

- Settings are saved in grav_config.json next to the program (or in
  %APPDATA%\GravChamberMacro if that folder can't be written to).
- Keys are sent with DirectInput, which Roblox accepts.

## Disclaimer

Automating gameplay may be against Roblox's or the game's rules and could get an account
punished. Use it at your own risk. The creator isn't responsible for what happens to accounts
that use it.
