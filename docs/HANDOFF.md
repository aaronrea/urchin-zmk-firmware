# Urchin firmware — handoff (2026-11-25)

Goal: get the Urchin firmware tuned for travel use with the iPad (now in a shared case).
This file is a pickup point for the next session. Delete it once the items below are done.

## Where things stand

- `main` is at `32803bd` (merge of PR #3). CI is green, and the build to flash is the
  `firmware-hybrid` artifact. Aaron flashed it and checked it on hardware in September.
- The only keymap that gets built is `config/urchin-hybrid.keymap`. `config/urchin.keymap` is
  kept for reference and isn't built.
- Layers: Base, Mods (EXT), Settings, Globe. The Sym layer was removed.
- `docs/keymap.html` is the up-to-date visual keymap.

### Pairing (current layout)

1. Hold the left inner thumb (Mods). Hold it; a tap locks Mods on.
2. Press 5+6 together (positions 4+5, the T/Y keys). Settings stays on after you release.
3. Slots: left T/G/B = BT0/1/2, right Y/H/N = BT3/4/5. Clear the slot (BT_CLR) is on **V**.
4. Any thumb goes back to Base.

Known slots: iPhone = G (BT1), tekto = B (BT2), work intended for T (BT0).
**iPad slot: not recorded yet. Ask Aaron.**

## Open items

### iPad (priority for travel)

1. **Dead Globe-layer keys.** ZMK can only send consumer usage `0x029D`, not Apple's real Fn
   modifier, so iPadOS ignores some of the Globe shortcuts. Aaron confirmed that some keys
   do nothing but hasn't said which. Likely dead: H home, C control centre, A dock,
   shift-A app library, N lock, M menu bar, F full screen, and the ctrl-Globe-arrow tiling.
   Likely working: E emoji, D dictation, plain GLOBE. Plan: get the list from Aaron, then
   put ⌘-based shortcuts that do work on the dead keys (for example ⌘H for Home).
2. **Tapping the left inner thumb locks EXT** (`&mo_tog EXT EXT`). Recommend switching it to plain `&mo EXT`.
3. **⌘ is only on the thumbs.** Decide whether to put ⌘ on F and J with `&hml LGUI F` / `&hmr RGUI J`
   (there's a comment about this in the Base layer) to make ⌘Tab and ⌘Space easier.
4. Idle sleep is 30 minutes (`config/urchin.conf`). Only change it if the reconnect lag bothers him.

### Repo cleanup

5. **Don't merge `claude/fix-keyboard-key-presses-8LMMY`.** Its keymap and build changes
   would undo PR #3. Its home-row tuning is already on main. Things worth salvaging:
   `CLAUDE.md` (a note to keep the cheat sheet in sync) and `docs/urchin-cheatsheet.md`
   (the Obsidian cheat sheet with Aaron's BT slot notes). The cheat sheet still describes
   the old Sym/combo layout and needs rewriting from main.
6. `claude/obsidian-layout-snippet-XPfLd` (`docs/keymap.md`) is out of date in the same way.
   Fold it into one rewritten cheat sheet, then delete both old branches.
   `claude/keymap-mobile-modifiers-tujc6z` is already merged and can be deleted.
7. `build.yaml` at the repo root is a leftover. The workflow only reads `build-hybrid.yaml`,
   so remove `build.yaml` and probably `build-standard.yaml` too.
8. Out-of-date comments in `config/urchin-hybrid.keymap`: the `mo_tog` note mentions
   "FN + left inner thumb", and the combo header says every combo is pinned to BASE
   (the Settings combo is pinned to EXT).
9. The fork is 3 commits behind upstream `duckyb:main`. Low priority.

## Suggested next session

Ask Aaron for (a) the dead Globe keys and (b) the iPad's BT slot. Then make one branch with
items 1–3 and 5–8, check that CI is green, open a PR, and have him flash both halves.
Keep `docs/keymap.html` and the cheat sheet in sync in the same PR.
