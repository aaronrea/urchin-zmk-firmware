# Urchin cheat sheet

34-key split. Four layers: **Base**, **Mods**, **Settings**, **Globe**.
Source: `config/urchin-hybrid.keymap` in `aaronrea/urchin-zmk-firmware`.
Visual version: `docs/keymap.html`.

## Bluetooth

### My slots

| Key | Slot | Device |
| --- | --- | --- |
| `T` | BT 0 | work |
| `G` | BT 1 | iPhone |
| `B` | BT 2 | tekto |
| `Y` | BT 3 | |
| `H` | BT 4 | |
| `N` | BT 5 | |

### Get into Settings

1. Hold the **left outer thumb** (Mods).
2. Tap **5 and 6** together (the T and Y keys), then let go of everything.
   Settings stays on.
3. Press a slot key from the table above.
4. Press **any thumb** to go back to Base.

### Pair a new device

1. Get into Settings and pick an unused slot.
2. If that slot was used before, press **V** (`BT_CLR`) to wipe it.
   It only clears the slot you are on.
3. Connect from the device's Bluetooth settings.

Switching devices later is just: Settings, slot key, any thumb.

Other Settings keys: `Q`/`P` bootloader, `W`/`O` ZMK Studio unlock,
`I` unstick (taps every modifier to clear a stuck one).

## Base

```
┌───┬───┬───┬───┬───┐   ┌───┬───┬───┬───┬───┐
│ Q │ W │ E │ R │ T │   │ Y │ U │ I │ O │ P │
├───┼───┼───┼───┼───┤   ├───┼───┼───┼───┼───┤
│ A │ S │ D │ F │ G │   │ H │ J │ K │ L │ ; │
│ ⇧ │ ⌃ │ ⌥ │   │   │   │   │   │ ⌥ │ ⌃ │ ⇧ │
├───┼───┼───┼───┼───┤   ├───┼───┼───┼───┼───┤
│ Z │ X │ C │ V │ B │   │ N │ M │ , │ . │ / │
└───┴───┴───┴───┴───┘   └───┴───┴───┴───┴───┘
           ┌────┬────┐ ┌────┬─────┐
           │MODS│SPC │ │SPC │ ENT │
           │    │ ⌘  │ │ ⌘  │GLOBE│
           └────┴────┘ └────┴─────┘
```

- Home-row mods: hold `A S D` / `K L ;` for ⇧ ⌃ ⌥ / ⌥ ⌃ ⇧. They only fire
  when the next key is on the other hand or a thumb, so rolls stay letters.
- ⌘ is on the space thumbs only (hold = ⌘, tap = space).
- Left outer thumb: **hold** for Mods. Tapping it does nothing.
- Right outer thumb: hold for Globe, tap for Enter.

### Combos (Base only)

| Keys | Does |
| --- | --- |
| `R` + `T` | Tab |
| `Y` + `U` | Backspace |
| `F` + `G` | Escape |
| `H` + `J` | Enter |

## Mods (hold left outer thumb)

```
┌───┬───┬───┬───┬───┐   ┌───┬───┬───┬───┬───┐
│ 1 │ 2 │ 3 │ 4 │ 5 │   │ 6 │ 7 │ 8 │ 9 │ 0 │
├───┼───┼───┼───┼───┤   ├───┼───┼───┼───┼───┤
│ ⇧ │ ` │ [ │ ] │Tab│   │ ← │ ↓ │ ↑ │ → │ ⇧ │
├───┼───┼───┼───┼───┤   ├───┼───┼───┼───┼───┤
│ ⌥ │ - │ ' │ = │ \ │   │Esc│Bsp│Del│ ⌃ │ 🌐│
│   │ ⌃ │   │   │   │   │   │   │   │   │stk│
└───┴───┴───┴───┴───┘   └───┴───┴───┴───┴───┘
```

- Symbols are shift + these keys (e.g. ⇧1 = `!`, ⇧` = `~`, ⇧[ = `{`).
- Right space thumb still gives ⌘ here: ⌘← / ⌘→ = start / end of line.
- Bottom-right 🌐 is a sticky Globe: tap it, let go of Mods, tap a letter.
- Mods + `5` and `6` = Settings (see Bluetooth above).

## Globe (hold right outer thumb)

Hold the Globe thumb and press the letter you would on a Magic Keyboard.

| Key | Does | Key | Does |
| --- | --- | --- | --- |
| `E` | Emoji | `H` | Home Screen |
| `A` | Dock | `N` | Lock Screen |
| ⇧`A` | App Library | `M` | Menu bar |
| `D` | Dictation | `F` | Full screen |
| `C` | Control Center | `;` | plain Globe (switch keyboard) |

- `Y U I O` = ⌃Globe ← ↓ ↑ →, tile the window to that side.
- `J` / `K` = Page Down / Page Up. `L` / `.` = volume up / down, `,` = mute.

ZMK can't send Apple's real Fn key, only a stand-in Globe code, so iPadOS
ignores some of these. ⌘ shortcuts that always work on the iPad:
⌘H home, ⌘Tab app switcher, ⌘Space Spotlight, ⌘⇧3 / ⌘⇧4 screenshot.
