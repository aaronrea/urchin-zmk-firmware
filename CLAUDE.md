# Notes for Claude

## Keep `docs/urchin-cheatsheet.md` in sync with the keymap

`docs/urchin-cheatsheet.md` is the source-of-truth cheat sheet the user copies into their Obsidian vault. It documents `config/urchin-hybrid.keymap` — layers, thumb behaviors, combos, and the Bluetooth pairing flow on the Settings layer.

**Whenever a change to `config/urchin-hybrid.keymap` (or `config/urchin.keymap` if they diverge in ways that matter) lands on `main`, refresh `docs/urchin-cheatsheet.md` in the same commit / PR.** Things to re-check:

- Layer count and order (BASE / EXT / SYM / SETTINGS).
- Base-layer homerow-mod assignments on `ASDF` / `JKL;`.
- Thumb bindings on every layer (Base thumbs currently `&mo EXT`, `SPACE`, `SPACE`, `ENTER` — not mod-taps).
- Combo list (keys, position numbers, timeout, action).
- Settings layer BT slot layout (`BT_SEL 0..5`, `BT_CLR`, bootloader, `studio_unlock`, `unstick`).
- Custom behaviors (`qt`, `mo_tog`, `hml`, `hmr`, `unstick` macro).

If the cheat sheet's prose no longer matches the keymap (e.g. it claims a thumb tap-toggles a layer but the binding is plain `&mo`), fix the prose to match the keymap, not the other way around.

The user's personal Bluetooth slot mappings (which device is on which slot) live in the cheat sheet and should be preserved verbatim across refreshes unless they explicitly change them.
