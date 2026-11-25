# Notes for Claude

## What gets built

Only `config/urchin-hybrid.keymap` is built (`build-hybrid.yaml`, artifact
`firmware-hybrid`). `config/urchin.keymap` is reference only; keep it in step
with the hybrid apart from the four Voyager combos.

## Keep the docs in sync with the keymap

Any change to `config/urchin-hybrid.keymap` updates these in the same PR:

- `docs/urchin-cheatsheet.md`: the cheat sheet Aaron copies into Obsidian.
- `docs/keymap.html`: the visual keymap.
- `README.md`, where it describes layers, thumbs or combos.

Re-check layer list and order, thumb bindings on every layer, home-row mods,
the combo list, the Settings layer BT block, and the Globe layer.

If the prose disagrees with the keymap, fix the prose to match the keymap.

Aaron's Bluetooth slot assignments (which device is on which slot) live in the
cheat sheet. Keep them as they are unless he changes them.

## Decisions to respect

- ⌘ stays on the space thumbs only, not on F/J, to match his other boards.
- The Mods thumb is hold-only (`&mo EXT`). Don't bring back tap-to-lock.
