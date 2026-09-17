Firmware for: [Urchin Keyboard](https://github.com/duckyb/urchin)

## Getting started

**Are you trying to make your own ZMK firmware?**  
[Here are the steps you need to take.](./GETTING_STARTED.md)

## Keymap
- QWERTY with hrm;  {layer2, cmd/spc, cmd/spc, enter}
- num, sym, vim arrow, esc, del, etc {-> l1 tap/hold}
- settings layer from duckyb (bt, fw, studio) {-> LH combo}
- fn layer: F1-F12, Apple Globe, media/brightness, home/end/pgup/pgdn {-> RH combo}

### Layer access

| Layer | How to reach it |
| --- | --- |
| Base | default |
| Mods / Ext | hold left outer thumb (tap it to lock the layer on) |
| Sym (hybrid only) | hold `V`+`B` |
| Settings | hold both left thumb keys |
| Fn (F1-F12, media, page nav) | hold left outer thumb, then right outer thumb |

### Globe / Fn

There is no Fn key to map. On Apple keyboards Fn and Globe are the same physical
key, and it is not a HID modifier: the real one is AppleVendor Top Case page
(`0xFF`) usage `0x03`, carried in the reserved byte of the keyboard report, and
macOS/iOS only honour it from a device reporting Apple's own vendor ID. ZMK has
no keycode for it and cannot send it.

What ZMK can send is `GLOBE` -- consumer usage `0x029D`
(`AC Next Keyboard Layout Select`), which Apple maps to the Globe key's
keyboard-switching function. Held-Globe + letter chords work on iPadOS for some
shortcuts and not others; `Fn`+F-key and `Fn`+arrow behaviours do not work at
all. Two ways to reach it:

- **Base layer, right outer thumb** (`&gt GLOBE ENTER`): hold for Globe, tap for
  Enter. Globe chords have to live on the base layer, because that is the only
  layer with letters on it. No combo sits on this key, so there is no
  timeout to wait out before the chord registers.
- **Mods layer, right pinky bottom row** (`&sk GLOBE`): sticky. Tap it, release
  the layer, then tap a letter on the base layer.

Needs `CONFIG_ZMK_HID_CONSUMER_REPORT_USAGES_FULL=y` (set in `urchin.conf`) --
the basic consumer range stops at `0xFF` and would drop `0x029D` silently.

### iOS / iPadOS notes

- The Fn layer's left bottom row has the shortcuts that work regardless of
  Globe: `CMD+H` (home screen), `CMD+TAB` (app switcher), `CMD+SPACE`
  (Spotlight). Bottom right adds `CMD+SHIFT+3` / `CMD+SHIFT+4` screenshots.
- `HOME`/`END`/`PG_UP`/`PG_DN` are real keys on the Fn layer because the Apple
  way of getting them (`Fn`+arrow) cannot be sent from ZMK.
- `CMD` for arrow-key line navigation comes from the right thumb while the Mods
  layer is held (`CMD+LEFT` / `CMD+RIGHT` = start/end of line).

### Home-row mods

The home-row mods are positional (`hold-trigger-key-positions`) and use
`flavor = "balanced"` with `require-prior-idle-ms`, so a same-hand roll such as
`as` or `sd` can never resolve into `SHIFT+S` / `CTRL+D`. Tune
`require-prior-idle-ms` up if you still get accidental mods, or down if
shortcuts feel unresponsive right after typing.