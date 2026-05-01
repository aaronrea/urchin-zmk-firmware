# Urchin Keymap

34-key split. 3 layers: **Base**, **Mods**, **Settings**.

## Base (Layer 0)

```
┌───┬───┬───┬───┬───┐                   ┌───┬───┬───┬───┬───┐
│ Q │ W │ E │ R │ T │                   │ Y │ U │ I │ O │ P │
├───┼───┼───┼───┼───┤                   ├───┼───┼───┼───┼───┤
│ A │ S │ D │ F │ G │                   │ H │ J │ K │ L │ ; │
│⇧ │⌃ │⌥ │   │   │                   │   │   │⌥ │⌃ │⇧ │
├───┼───┼───┼───┼───┤                   ├───┼───┼───┼───┼───┤
│ Z │ X │ C │ V │ B │                   │ N │ M │ , │ . │ / │
└───┴───┴───┴───┴───┘                   └───┴───┴───┴───┴───┘
              ┌─────────┬─────────┐ ┌─────────┬─────────┐
              │ EXT(tog)│ ⌘ / Spc │ │ ⌘ / Spc │  Enter  │
              └─────────┴─────────┘ └─────────┴─────────┘
```

- Home-row mods on `ASDF` / `JKL;` (`LSHIFT LCTRL LALT` ↔ `RALT RCTRL RSHIFT`)
- Left inner thumb: hold = momentary **Mods**, tap = toggle **Mods**
- Thumbs `⌘/Spc`: hold = `LCMD`/`RCMD`, tap = Space

## Mods (Layer 1)

```
┌───┬───┬───┬───┬───┐                   ┌───┬───┬───┬───┬───┐
│ 1 │ 2 │ 3 │ 4 │ 5 │                   │ 6 │ 7 │ 8 │ 9 │ 0 │
├───┼───┼───┼───┼───┤                   ├───┼───┼───┼───┼───┤
│ ⇧ │ ` │ [ │ ] │Tab│                   │ ← │ ↓ │ ↑ │ → │ ⇧ │
├───┼───┼───┼───┼───┤                   ├───┼───┼───┼───┼───┤
│ ⌥ │⌃ -│ ~ │ = │ | │                   │Esc│Bsp│Del│ ⌃ │ ⌥ │
└───┴───┴───┴───┴───┘                   └───┴───┴───┴───┴───┘
              ┌─────────┬─────────┐ ┌─────────┬─────────┐
              │  trans  │  trans  │ │  trans  │  trans  │
              └─────────┴─────────┘ └─────────┴─────────┘
```

## Settings (Layer 2)

Reached via combo on both left thumb keys (positions 30 + 31).

```
┌─────┬──────┬─────┬──────┬──────┐         ┌──────┬─────┬───────┬──────┬─────┐
│boot │studio│  ·  │BT CLR│BT 0  │         │BT 3  │  ·  │unstick│studio│boot │
├─────┼──────┼─────┼──────┼──────┤         ├──────┼─────┼───────┼──────┼─────┤
│  ·  │  ·   │  ·  │  ·   │BT 1  │         │BT 4  │  ·  │  ·    │  ·   │  ·  │
├─────┼──────┼─────┼──────┼──────┤         ├──────┼─────┼───────┼──────┼─────┤
│  ·  │  ·   │  ·  │  ·   │BT 2  │         │BT 5  │  ·  │  ·    │  ·   │  ·  │
└─────┴──────┴─────┴──────┴──────┘         └──────┴─────┴───────┴──────┴─────┘
```

## Custom Behaviors

- `qt` — hold-preferred mod-tap (200 ms term, 200 ms quick-tap)
- `mo_tog` — hold = `&mo`, tap = `&tog`
- `unstick` macro — taps all 8 modifiers to clear stuck-mod state
- `&sk` set to `ignore-modifiers`

## Source

`config/urchin.keymap` in [`urchin-zmk-firmware`](https://github.com/aaronrea/urchin-zmk-firmware).
