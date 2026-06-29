# Vault State

## Navigation
- [README](README.md)

---

This file is the central tracker for gaps, unverified claims, structural issues, cross-node dependencies, and staged work across the guide. Individual node Feedback sections handle issues scoped to a single node. Everything that touches multiple nodes or requires coordination lives here.

Paste this file (or the relevant section) at the start of any session where the area is being worked.

---

## Structural Issues

**Reference node stage splitting — not yet done.**
Runes, Talismans, Challenges, and Ants were drafted as flat files but contain content spanning start-here through endgame. These need to be split into `- Start Here` and `- Post Singularity` variants. Channel nodes should then link only to the stage-appropriate file. Blessings and Research are stage-agnostic and do not need splitting.
- Blocked on: drafting the split files and updating all channel node links accordingly.

**Scope bleed in existing reference nodes.**
Horseshoe rune content is currently in `Runes.md` (a start-here-facing node). Post-singularity ant content (Half-mind, One-mind, reborn elo) is in `Ants.md`. These belong in the Post Singularity variants once the split is done.

**Navigation links unaudited.**
Navigation links in all drafted nodes use assumed relative paths that have not been verified against the actual repo structure. Links to nodes not yet in the repo (e.g. `Progression Map.md`) will be dead until those nodes exist.
- Action: audit all Navigation blocks once files are committed to repo.

**Local checkpoint spines not yet added.**
Channel nodes do not yet have checkpoint spines in their Navigation blocks. These are short ordered milestone lists giving a reader instant orientation within the channel. Needs drafting per channel once the format is confirmed.
- Depends on: confirmation of checkpoint format (short bullets? numbered list? inline links to sections?).

**`Progression Map.md` not yet drafted.**
Global checkpoint spine covering the whole game top to bottom. Should link into each channel node. No content drafted yet.

**`1-p4x2/s` and `2-p4x2/s` loadouts in Corruption Glossary are identical.**
Both are listed as `10/13/13/13/12/11/12/9` in the PDF source. Likely a typo in the source. Needs community or source verification before correcting.

---

## Unverified Claims (by node)

### General Tips (PDF source)
- Exact N rolls per daily code in the free levels system — not stated in PDF.
- Wow! Square talisman Mythic requirement for hepteract runs — stated in PDF general tips; verify against v4.1+.

### Singularity - e1x1
- Free level N (number of rolls per daily code) — unverified. Verify against source code.
- Shop upgrade cost thresholds — drawn from PDF; may be outdated in current version.
- e1x1 time estimate (4–12 hours) — from PDF; varies significantly by stats.

### e1x1 - e6x1
- Half-mind anthill timer threshold stated as "below ~2 seconds" — verify against source code.
- Even More Quarks and skrauq scaling with current singularity noted as "not mentioned in game for some reason" in PDF — verify in source.

### e6x1 - s256
- DELTAvator e2 every-11-sings requirement after s175 — verify exact sings against source code.
- Red ambrosia bar decrease from e6 effects — verify mechanic in source.
- Ambrosia upgrade order (Multi/Accel/Oct) — from PDF; may shift with player stats.
- Qhept breakeven values — rough estimates from PDF; Re-Oct sheet is more accurate.
- e6 timer reduction values (20s until e6x25, 5s after) — from PDF; verify against current version.

### s256 - e7x10
- e3x26 as alternative entry point for T/s stats check — reason not explained in PDF; verify with community.
- e8x5 upgrade referenced in e6x25 stats table but not explained — may need a note or cross-reference.
- Community stat tables are pre-v4.0 submission; flag for ongoing community updates.
- Amb production vs cube production CEF values — rough estimates from PDF; Re-Oct sheet is more precise.

### e7x10 - End
- Horseshoe rune 27% max reduction — verify cap calculation against source code.
- e8x9 impossibility stated as "intentional game design" in PDF — verify this has not changed in v4.1+.
- PTR table transcribed from PDF image — verify values against source or community tools.
- Content wall milestones are from PDF (v4.1 era); some may have been achieved since.

### Runes (current flat file — pre-split)
- Salvage cost reduction formula — not documented in any available source.
- Full rune list and effects not documented — only early-progression and post-singularity runes noted.
- Rune level targets (Speed 500/560, Duplication 130/160) — from Discord pins; verify against current version.

### Talismans (current flat file — pre-split)
- Rarity threshold breakpoints (every 30 levels vs specific values like 1, 440) — needs in-game or source verification.
- Full talisman list beyond the three listed — only pre-singularity relevant talismans covered.
- Wow! Square talisman Mythic requirement for hepteract runs — from PDF general tips; verify against v4.1+.

### Blessings
- Blessing cost formula — source pin explicitly admits this is unverified.
- Full Blessing list and individual effects not documented.

### Challenges (current flat file — pre-split)
- Challenge progression targets — from Discord pins; verify against current version.
- Full challenge list and individual effects not documented.
- c15 RCM module recommendation — verify against current ambrosia module set.

### Research
- Full research tree and effects not documented — only key early researches listed.
- r5x19–r5x20 relevance — from Discord pin; verify against current version.

### Ants (current flat file — pre-split)
- Half-mind anthill timer threshold ("below ~2 seconds") — needs source code verification.
- Full ant upgrade list and Mortuus Est Formicidae unlock condition — verify against source.

---

## Staged Work

**Next priority: reference node splitting.**
Split Runes, Talismans, Challenges, and Ants into `- Start Here` and `- Post Singularity` files. Move scope-bleed content to the correct file. Update channel node links to point to stage-appropriate variants.

**After splitting: checkpoint spines.**
Draft local checkpoint spines for each channel node Navigation block. Confirm format first.

**After checkpoint spines: Progression Map.**
Draft `Progression Map.md` as global top-to-bottom checkpoint chain linking into channel nodes.

**Ongoing: community stat table updates.**
Several stat tables (e1x30, e2x25, e4x15, e5x20, e6x25) are from the PDF and may be outdated post-v4.0/v4.1. Flag for community PR submissions.

**Not yet started: post-singularity Google Doc content.**
The Post-Singularity Google Doc (linked in Discord pins) has not been incorporated. Channel nodes from Singularity - e1x1 onward were drafted from the PDF only. The GDoc may contain corrections or additions.

---

## Cross-Node Dependencies

- Obt/Off/Ants corruption loadouts appear in both `Corruption Glossary.md` and `Ants - Post Singularity.md` (future). Decide whether Ants cross-references Corruption Glossary or duplicates for lookup convenience.
- `Progression Map.md` will need to be kept in sync with channel node structure as nodes are added or renamed.
- Half-mind and One-mind content currently lives in `e1x1 - e6x1.md` and will also live in `Ants - Post Singularity.md` after the split. Ensure these don't contradict.
- Shop Upgrade Effects appendix (from PDF pp. 44–45) has not been drafted as a node. Content is referenced from `s256 - e7x10.md` and `e7x10 - End.md`. Decide whether this becomes a Reference node or stays as an appendix section in the relevant channel node.

---

## Format & Convention Flags

- Singularity numbers must always be lowercase: `s25`, `e1x1`, `s256`. Audit all drafted nodes for uppercase instances (e.g. `S25`, `E1x1`).
- Navigation must link to `README.md` — not `README Hub.md` or any variant.
- Section headers use title case: `## Beta - 1e15 Expo`, not `## beta - 1e15 Expo`.
- Corruption loadouts always noted as screen order, not import order.