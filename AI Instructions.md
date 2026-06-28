# AI Instructions

## Navigation
- [README](README.md)

## Purpose
This node gives contributors enough context to use AI effectively when building or improving guide sections. The guide is verified against the [Synergism source code](https://github.com/pseudo-corp/SynergismOfficial) where possible — AI is a tool for drafting and cross-referencing, not a source of truth.

## Project Overview
A Synergism progression guide maintained in a GitHub repo (https://github.com/Blohrium/synergism-guide), hooked up to Obsidian locally. The guide is readable on GitHub, Obsidian, or Discord. A Discord bot is planned to handle posting and updating Discord messages automatically from the repo — this is not yet implemented but the guide is being written with that in mind.

The guide is populated from existing Discord pins and a community Google Doc (Comprehensive Guide to Singularity, written by Ephen, AlethiaLumen, alonso, maintained by IcyDvorak). Content may be slightly wrong or outdated as a starting point — that is acceptable. Accuracy improves through contributor PRs over time.

## Writing Principle
State each claim once, precisely. Connect explicitly. Elaborate nothing.

Connections between sections are load-bearing. Everything else is cut: restatement in different words, elaboration of elaboration, headers that announce what the prose is about to say.

Failure modes to avoid:
- Restatement — the same claim in slightly different words
- Elaboration of elaboration — a clarification of a clarification
- Filler confidence — "X leads to Y" stated without verifying against code

## Node Structure
Every node file follows this order:

1. Navigation (top, always)
2. Content (the guide, written as clean readable markdown)
3. FAQ (common Discord questions with Q+A paired in code blocks)
4. Feedback (known issues, unverified claims, structural questions)

No separate "Discord layer" vs "exhaustive layer" — it is all one guide. The bot handles chunking content into Discord messages when that is implemented. For now focus is on Obsidian and GitHub only.

## Folder Structure
Only channel-level nodes get folders. Reference nodes and mechanic nodes are flat files. Current structure:

```
synergism-guide/
  README Hub.md
  AI Instructions.md
  Start Here - c10x1/
    Start Here - c10x1.md
    Transcension.md
    Reincarnation.md
    Ascension.md
  c10x1 - w5x10/
    c10x1 - w5x10.md
  w5x10 - 1e15 Expo/
    w5x10 - 1e15 Expo.md
  1e15 Expo - Singularity/
    1e15 Expo - Singularity.md
  Singularity - e1x1/
    Singularity - e1x1.md        ← needs post-sing Google Doc
  e1x1 - e6x1/
    e1x1 - e6x1.md               ← needs post-sing Google Doc
  e6x1 - s256/
    e6x1 - s256.md               ← needs post-sing Google Doc
  s256 - e7x10/
    s256 - e7x10.md              ← needs post-sing Google Doc
  e7x10 - End/
    e7x10 - End.md               ← needs post-sing Google Doc
  Reference/
    Corruption Glossary.md       ← needs drafting, content in PDF pages 29-30
    Acronyms.md                  ← needs drafting, content in PDF pages 34-35
    Runes.md                     ← needs drafting
    Talismans.md                 ← needs drafting
    Blessings.md                 ← needs drafting
    Challenges.md                ← needs drafting
    Research.md                  ← needs drafting
    Ants.md                      ← needs drafting
```

## Nodes Drafted So Far
All of the following have been drafted and contain Navigation, Content, FAQ, and Feedback sections:

- **README Hub** — index of all channel nodes, Discord links
- **AI Instructions** — this file
- **Start Here - c10x1** — guide index, abbreviations, hotkeys, codes, quark mechanisms
- **Transcension** — full progression from first prestige to first transcend
- **Reincarnation** — full progression from first transcend to first reincarnate
- **Ascension** — when to ascend, quark shop, codes, WoW Pass v1
- **c10x1 - w5x10** — post-first-ascension, c11-c14, corruptions, shop upgrades, offering runs
- **w5x10 - 1e15 Expo** — c15, run cycle, r8x25, Platonics, Alpha, p2x1, p3x1, Beta
- **1e15 Expo - Singularity** — Beta raised caps, p3x2/p3x3, Hepteracts, Omega, p4x1-p4x4, Singularity checklist, formulae

## Content Sources Available
- Original Discord pins (absorbed into Start Here channel nodes)
- Comprehensive Guide to Singularity PDF (absorbed into c10x1 through 1e15 Expo - Singularity nodes)
- Post-Singularity Google Doc — not yet provided, needed for Singularity - e1x1 through e7x10 - End
- Synergism source repo: https://github.com/pseudo-corp/SynergismOfficial — for verification

## Key Conventions
- `> ⚠ unverified` — marks claims that need source verification
- Feedback section — running log of known issues, structural questions, unverified claims
- FAQ entries — Q and A paired inside a single code block, self-contained
- Corruption loadouts — currently in visual order (top to bottom in corruption screen); import order differs and should be noted in Corruption Glossary
- Spoiler text — low priority, Discord uses `||spoiler||`, not yet addressed for GitHub/Obsidian

## Verification
Claims should trace to source code where possible. Mark anything unverified with `> ⚠ unverified`. AI fills gaps with plausible-sounding defaults when it doesn't know — those defaults go stale. Unverified claims are worse than gaps because they're invisible.

Point AI to the Synergism repo and ask it to verify specific mechanics before stating them.

## Planned Bot Behaviour
- Bot posts each guide message once and stores the message ID
- Updates to the repo automatically edit the existing Discord message in place
- No new pins needed — existing pins stay current automatically
- FAQ responses are command-triggered (e.g. /faq ants)
- Bot only reflects content approved via PR merge — mods retain control through repo permissions
- Not yet implemented — pending admin approval for bot permissions

## Contribution Flow
1. Find a gap, wrong claim, or unanswered FAQ
2. Open the relevant node file
3. Draft a fix — point AI at the source code for verification if needed
4. Submit a PR — phrase corrections as falsifiable claims with evidence so approving is as simple as confirming it is true
5. Maintainer reviews and merges

Anyone with AI access can contribute. Source code is the authority — if AI and code disagree, code wins.

## FAQ
## Feedback