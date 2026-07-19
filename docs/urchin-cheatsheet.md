# Urchin Keyboard Bluetooth Pairing

## Enter Settings Layer

Hold both **left thumb keys** simultaneously (layer/toggle + left CMD/Space).
No, I said both left thumb keys…
This is a 1 handed operation
Iphone is set to g (middle left)
tekto is set to b (bottom left) 
work should be set to t (top left\)

## Bluetooth Profile Keys

While holding the settings combo:

| Key | Action                                     |
| --- | ------------------------------------------ |
| `R` | `BT_CLR` — clear current profile's pairing |
| `T` | `BT_SEL 0`                                 |
| `G` | `BT_SEL 1` - iphone                        |
| `B` | `BT_SEL 2` ———xxx                          |
| `Y` | `BT_SEL 3`                                 |
| `H` | `BT_SEL 4`                                 |
| `N` | `BT_SEL 5`                                 |

## Pairing a New Device

1. Select an unused profile slot (e.g. `T` for BT_SEL 0)
2. If the slot was previously paired, press `R` (`BT_CLR`) to wipe it
3. On the device, open Bluetooth settings and connect to the keyboard
4. Done — the keyboard remembers the pairing on that slot

## Switching Between Devices

Enter the settings layer and press the `BT_SEL` key for the target device.

> Use a separate profile slot per device so you can switch without re-pairing.

# Urchin Keymap (Hybrid)

34-key split. 4 layers: **Base**, **Ext**, **Sym**, **Settings**.

## Base (Layer 0)

```
┌───┬───┬───┬───┬───┐   ┌───┬───┬───┬───┬───┐
│ Q │ W │ E │ R │ T │   │ Y │ U │ I │ O │ P │
├───┼───┼───┼───┼───┤   ├───┼───┼───┼───┼───┤
│ A │ S │ D │ F │ G │   │ H │ J │ K │ L │ ; │
│  ⇧│  ⌃│  ⌥│   │   │   │   │   │  ⌥│  ⌃│  ⇧│
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

| Combo    | Keys              | Positions | Action                 | Timeout |
| -------- | ----------------- | --------- | ---------------------- | ------- |
| settings | both left thumbs  | `30 31`   | Momentary **Settings** | 200 ms  |
| tab      | R + T             | `3 4`     | Tab                    | 50 ms   |
| bspc     | Y + U             | `5 6`     | Backspace              | 50 ms   |
| esc      | F + G             | `13 14`   | Escape                 | 50 ms   |
| enter    | H + J             | `15 16`   | Enter                  | 50 ms   |

## Build Snippets

| Snippet               | Applied to                         | Purpose                                           |
| --------------------- | ---------------------------------- | ------------------------------------------------- |
| `studio-rpc-usb-uart` | All firmware builds (left + right) | Routes ZMK Studio RPC over the USB CDC ACM (UART) |

Paired with `-DCONFIG_ZMK_STUDIO=y` for ZMK Studio over USB.

## Custom Behaviors

- `qt` — hold-preferred mod-tap (200 ms term, 200 ms quick-tap)
- `mo_tog` — hold = `&mo`, tap = `&tog`
- `unstick` macro — taps all 8 modifiers to clear stuck-mod state
- `&sk` set to `ignore-modifiers`

## Source

`config/urchin-hybrid.keymap` in [`urchin-zmk-firmware`](<https://github.com/aaronrea/urchin-zmk-firmware>).
