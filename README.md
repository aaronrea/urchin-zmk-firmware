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
| Fn | hold both right thumb keys |

### iOS / iPadOS notes

- `GLOBE` sits on the Mods layer (right pinky, bottom row) and on the Fn layer.
  ZMK sends it as a consumer usage rather than a real Apple Fn modifier, so it
  works as a *tap* (switch keyboard / emoji / input source). The Fn layer also
  has `&sk GLOBE` (sticky) next to it for `Globe`+key attempts.
- The Fn layer's left bottom row has the shortcuts that do work reliably:
  `CMD+H` (home screen), `CMD+TAB` (app switcher), `CMD+SPACE` (Spotlight).
- `CMD` for arrow-key line navigation comes from the right thumb while the Mods
  layer is held (`CMD+LEFT` / `CMD+RIGHT` = start/end of line).

### Home-row mods

The home-row mods are positional (`hold-trigger-key-positions`) and use
`flavor = "balanced"` with `require-prior-idle-ms`, so a same-hand roll such as
`as` or `sd` can never resolve into `SHIFT+S` / `CTRL+D`. Tune
`require-prior-idle-ms` up if you still get accidental mods, or down if
shortcuts feel unresponsive right after typing.