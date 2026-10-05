# Dragonspear party status

Read-only viewer for the Dragonspear campaign. The campaign chat writes `party-status.json`. This page only reads it.

After GitHub Pages is on, the viewer is https://grjensen.github.io/dragonspear_campaign/

Pages: repo Settings, Pages, Deploy from branch `main`, folder `/ (root)`. First deploy takes a minute. Refresh on the page bypasses a short Pages cache.

## Files

- `index.html` — the viewer
- `party-status.json` — source of truth for the page
- `party-status.md` — the same facts, for the chat
- `img/armor/`, `img/weapons/` — cutouts, transparent PNG

A plain shield in the kit uses `shield`. The page looks for `img/armor/shield_medium.png`. That file is not in the repo yet, nor are `shield_large.png`, `shield_small.png`, `scale_mail.png`, `splint_mail.png`, or `studded_leather.png`. A missing image falls back to the label.

## Campaign rule

At the end of a scene, rewrite `party-status.json` and `party-status.md` from the same facts. Do not parse the markdown to make the JSON. Keep at most six characters. Armor and weapon `id` values must match the map in `index.html` (`leather` → `leather_armour.png`, `chain_mail` → `chainmail.png`, `warhammer` → `war_hammer.png`). Ammunition is `ammo` on the weapon. Gear and potions stay text.

Do not put secrets, unrevealed maps, or NPC tactics in this file. The repo is public.
