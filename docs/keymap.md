# Urchin Keymap

34-key split. 3 layers: **Base**, **Mods**, **Settings**.

## Base (Layer 0)

```
┌───┬───┬───┬───┬───┐   ┌───┬───┬───┬───┬───┐
│ Q │ W │ E │ R │ T │   │ Y │ U │ I │ O │ P │
├───┼───┼───┼───┼───┤   ├───┼───┼───┼───┼───┤
│ A │ S │ D │ F │ G │   │ H │ J │ K │ L │ ; │
│ ⇧│ ⌃│ ⌥│   │   │   │   │   │ ⌥│ ⌃│ ⇧│
├───┼───┼───┼───┼───┤   ├───┼───┼───┼───┼───┤
│ Z │ X │ C │ V │ B │   │ N │ M │ , │ . │ / │
└───┴───┴───┴───┴───┘   └───┴───┴───┴───┴───┘
            ┌───┬───┐   ┌───┬───┐
            │EXT│ ⌘ │   │ ⌘ │ ⏎ │
            └───┴───┘   └───┴───┘
```

- Home-row mods on `ASDF` / `JKL;` (`LSHIFT LCTRL LALT` ↔ `RALT RCTRL RSHIFT`)
- Left inner thumb: hold = momentary **Mods**, tap = toggle **Mods**
- Thumb `⌘`: hold = `LCMD`/`RCMD`, tap = Space

## Mods (Layer 1)

```
┌───┬───┬───┬───┬───┐   ┌───┬───┬───┬───┬───┐
│ 1 │ 2 │ 3 │ 4 │ 5 │   │ 6 │ 7 │ 8 │ 9 │ 0 │
├───┼───┼───┼───┼───┤   ├───┼───┼───┼───┼───┤
│ ⇧ │ ` │ [ │ ] │Tab│   │ ← │ ↓ │ ↑ │ → │ ⇧ │
├───┼───┼───┼───┼───┤   ├───┼───┼───┼───┼───┤
│ ⌥ │⌃ -│ ~ │ = │ | │   │Esc│Bsp│Del│ ⌃ │ ⌥ │
└───┴───┴───┴───┴───┘   └───┴───┴───┴───┴───┘
            ┌───┬───┐   ┌───┬───┐
            │ — │ — │   │ — │ — │
            └───┴───┘   └───┴───┘
```

## Settings (Layer 2)

```
┌───┬───┬───┬───┬───┐   ┌───┬───┬───┬───┬───┐
│BLD│STU│ · │CLR│BT0│   │BT3│ · │USK│STU│BLD│
├───┼───┼───┼───┼───┤   ├───┼───┼───┼───┼───┤
│ · │ · │ · │ · │BT1│   │BT4│ · │ · │ · │ · │
├───┼───┼───┼───┼───┤   ├───┼───┼───┼───┼───┤
│ · │ · │ · │ · │BT2│   │BT5│ · │ · │ · │ · │
└───┴───┴───┴───┴───┘   └───┴───┴───┴───┴───┘
            ┌───┬───┐   ┌───┬───┐
            │ — │ — │   │ — │ — │
            └───┴───┘   └───┴───┘
```

Legend: `BLD` bootloader · `STU` studio_unlock · `CLR` BT_CLR · `USK` unstick · `BTn` BT_SEL n

## Combos

| Keys                           | Positions | Action                  |
| ------------------------------ | --------- | ----------------------- |
| Both left thumbs (inner+outer) | `30 31`   | Momentary **Settings** |

Combo timeout: 200 ms.

## Custom Behaviors

- `qt` — hold-preferred mod-tap (200 ms term, 200 ms quick-tap)
- `mo_tog` — hold = `&mo`, tap = `&tog`
- `unstick` macro — taps all 8 modifiers to clear stuck-mod state
- `&sk` set to `ignore-modifiers`

## Source

`config/urchin.keymap` in [`urchin-zmk-firmware`](https://github.com/aaronrea/urchin-zmk-firmware).
