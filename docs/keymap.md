# Urchin Keymap (Hybrid)

34-key split. 4 layers: **Base**, **Ext**, **Sym**, **Settings**.

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
- Left inner thumb: hold = momentary **Ext**, tap = toggle **Ext**
- Thumb `⌘`: hold = `LCMD`/`RCMD`, tap = Space

## Ext (Layer 1)

```
┌───┬───┬───┬───┬───┐   ┌───┬───┬───┬───┬───┐
│ 1 │ 2 │ 3 │ 4 │ 5 │   │ 6 │ 7 │ 8 │ 9 │ 0 │
├───┼───┼───┼───┼───┤   ├───┼───┼───┼───┼───┤
│ ⇧ │ ` │ [ │ ] │Tab│   │ ← │ ↓ │ ↑ │ → │ ⇧ │
├───┼───┼───┼───┼───┤   ├───┼───┼───┼───┼───┤
│ ⌥ │⌃ -│ ' │ = │ \ │   │Esc│Bsp│Del│ ⌃ │ ⌥ │
└───┴───┴───┴───┴───┘   └───┴───┴───┴───┴───┘
            ┌───┬───┐   ┌───┬───┐
            │ — │ — │   │ — │ — │
            └───┴───┘   └───┴───┘
```

## Sym (Layer 2)

Voyager-inspired symbols + nav.

```
┌───┬───┬───┬───┬───┐   ┌───┬───┬───┬───┬───┐
│ ! │ @ │ # │ $ │ % │   │ ^ │ & │ * │ - │ = │
├───┼───┼───┼───┼───┤   ├───┼───┼───┼───┼───┤
│ ~ │ ` │ { │ } │ | │   │ ← │ ↓ │ ↑ │ → │PgU│
├───┼───┼───┼───┼───┤   ├───┼───┼───┼───┼───┤
│ ⌥ │ _ │ ( │ ) │ \ │   │Esc│Bsp│Del│ ⌃ │PgD│
└───┴───┴───┴───┴───┘   └───┴───┴───┴───┴───┘
            ┌───┬───┐   ┌───┬───┐
            │tog│ — │   │ — │ — │
            └───┴───┘   └───┴───┘
```

Left inner thumb toggles **Sym** off.

## Settings (Layer 3)

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

| Combo    | Keys             | Positions | Action                 | Timeout |
| -------- | ---------------- | --------- | ---------------------- | ------- |
| settings | both left thumbs | `30 31`   | Momentary **Settings** | 200 ms  |
| tab      | R + T            | `3 4`     | Tab                    | 50 ms   |
| bspc     | Y + U            | `5 6`     | Backspace              | 50 ms   |
| esc      | F + G            | `13 14`   | Escape                 | 50 ms   |
| enter    | H + J            | `15 16`   | Enter                  | 50 ms   |

## Build Snippets

Zephyr snippets applied at build time (see `build.yaml`):

| Snippet               | Applied to                         | Purpose                                           |
| --------------------- | ---------------------------------- | ------------------------------------------------- |
| `studio-rpc-usb-uart` | All firmware builds (left + right) | Routes ZMK Studio RPC over the USB CDC ACM (UART) |

Paired with `-DCONFIG_ZMK_STUDIO=y` so the keyboard exposes its layout to ZMK Studio over USB.

## Custom Behaviors

- `qt` — hold-preferred mod-tap (200 ms term, 200 ms quick-tap)
- `mo_tog` — hold = `&mo`, tap = `&tog`
- `unstick` macro — taps all 8 modifiers to clear stuck-mod state
- `&sk` set to `ignore-modifiers`

## Source

`config/urchin-hybrid.keymap` in [`urchin-zmk-firmware`](https://github.com/aaronrea/urchin-zmk-firmware).
