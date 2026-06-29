# AI Instructions

## Navigation
- [README](README.md)

---

## Project Overview

A Synergism progression guide maintained in a GitHub repo (https://github.com/Blohrium/synergism-guide), hooked up to Obsidian locally. The guide is readable on GitHub, Obsidian, or Discord. A Discord bot is planned to handle posting and updating Discord messages automatically from the repo — not yet implemented, but the guide is written with that in mind.

Content sourced from Discord pins, a community Google Doc (Comprehensive Guide to Singularity, written by Ephen, AlethiaLumen, alonso, maintained by IcyDvorak), and the Not-so Comprehensive Guide through Singularity PDF (v4.1). Content may be slightly wrong or outdated — that is acceptable. Accuracy improves through contributor PRs over time.

The ground truth for all mechanics is the Synergism source repo: https://github.com/pseudo-corp/SynergismOfficial. If AI and source code disagree, source wins.

---

## Writing Principle

State each claim once, precisely. Connections between sections are load-bearing — state them explicitly. Everything else is cut: restatement in different words, elaboration of elaboration, headers that announce what the prose is about to say.

Failure modes to avoid:
- Restatement — the same claim in slightly different words
- Elaboration of elaboration — a clarification of a clarification
- Filler confidence — "X leads to Y" stated without verifying against code

---

## Node Format

Every node file follows this order:

1. **Navigation** — top of file, always. Contains: links to README, previous channel node, next channel node. Also contains the **local checkpoint spine** for channel nodes — a short ordered list of milestones for this channel, each ideally linking to the relevant section below. This lets a reader orient instantly without reading the full node.
2. **Content** — the guide, written as clean readable markdown. Prose over lists where possible.
3. **FAQ** — common Discord questions with Q+A paired in code blocks.
4. **Feedback** — known issues, unverified claims, structural questions scoped to this node only. Cross-node dependencies and propagation concerns go in Vault State, not here.

---

## Folder & File Structure

```
synergism-guide/
  README.md
  AI Instructions.md
  Vault State.md                          ← central gap/tension/dependency tracker
  Progression Map.md                      ← global checkpoint spine, whole game top to bottom
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
    Singularity - e1x1.md
  e1x1 - e6x1/
    e1x1 - e6x1.md
  e6x1 - s256/
    e6x1 - s256.md
  s256 - e7x10/
    s256 - e7x10.md
  e7x10 - End/
    e7x10 - End.md
  Reference/
    Corruption Glossary.md
    Acronyms.md
    Runes - Start Here.md               ← renamed/split from Runes.md
    Runes - Post Singularity.md         ← new
    Talismans - Start Here.md           ← renamed/split from Talismans.md
    Talismans - Post Singularity.md     ← new
    Blessings.md                        ← stage-agnostic, no split needed
    Challenges - Start Here.md          ← renamed/split from Challenges.md
    Challenges - Post Singularity.md    ← new
    Research.md                         ← stage-agnostic, no split needed
    Ants - Start Here.md                ← renamed/split from Ants.md
    Ants - Post Singularity.md          ← new
```

---

## Key Conventions

- `> ⚠ unverified` — marks claims needing source verification. These are logged in Vault State for triage.
- Singularity numbers always lowercase: `s25`, `e1x1`, `s256`, etc.
- Section headers use title case: `## Beta - 1e15 Expo`.
- Navigation links to `README.md`, not `README Hub.md` or any other variant.
- Corruption loadouts listed top to bottom as shown in the corruption screen — not import order. Always note this where loadouts appear.
- Spoiler text — not needed in the guide. Write plainly.
- Reference nodes split by stage where content differs meaningfully by stage. Channel nodes link only to the stage-appropriate reference file.

---

## What Claude Does

Claude operates as active builder. The human owns the vision. Claude handles structure, drafting, cross-referencing, and gap identification.

**The human answers:** vision questions — what something should feel like, whether a direction is right, what they want to exist in this guide.

**Claude handles:**
- Drafting nodes from available source material
- Cross-referencing pasted nodes against each other for contradictions
- Identifying scope bleed (e.g. endgame content in a start-here node)
- Flagging unverified claims with `> ⚠ unverified` and logging them in Vault State
- Proposing structural improvements
- Naming the next node or section to work on and why — one sentence

**On receiving pasted nodes or source material:**
1. Cross-reference all pasted content. Resolve anything resolvable from available context.
2. Identify contradictions. Surface as one sentence naming the conflict.
3. Check Vault State — act on resolvable entries for the area being worked.
4. Absorb all input in full before producing output.

**On producing output:**
5. Multiple node drafts per exchange are fine when mechanically similar or genuinely require touching together.
6. After each draft or batch, name the next node or section to pull and why.
7. After producing any file, surface it via present_files in the same turn.
8. Cross-node dependencies and propagation concerns go into Vault State, not onto individual nodes.

---

## What Claude Is Bad At Here

- **Scope bleed** — placing endgame content in start-here nodes or vice versa. Always check the channel context before adding reference content.
- **Hallucinated mechanics** — filling gaps from general Synergism knowledge rather than available source material. Mark gaps as `> ⚠ unverified`.
- **Drift** — each session starts fresh; README and Vault State are the anchors.
- **Navigation link errors** — generating links to nodes that don't exist yet, or wrong relative paths. Flag uncertain links in Vault State.
- **Stage-agnostic reference nodes** — Runes, Talismans, Challenges, Ants all have meaningfully different content by stage. Don't flatten them.
- **Writing a file without presenting it.**
- **Putting cross-node dependencies or open questions on individual nodes** — those live in Vault State.
- **Treating the PDF or pins as ground truth** — they are starting points. Source code is ground truth.

---

## Verification

Claims should trace to source code where possible. Mark anything unverified with `> ⚠ unverified`. Unverified claims are worse than gaps because they're invisible. AI fills gaps with plausible-sounding defaults when it doesn't know — those defaults go stale.

Point AI to the Synergism repo and ask it to verify specific mechanics before stating them.

---

## Planned Bot Behaviour

- Bot posts each guide message once and stores the message ID
- Updates to the repo automatically edit the existing Discord message in place
- No new pins needed — existing pins stay current automatically
- FAQ responses are command-triggered (e.g. /faq ants)
- Bot only reflects content approved via PR merge — mods retain control through repo permissions
- Not yet implemented — pending admin approval for bot permissions

---

## Contribution Flow

1. Find a gap, wrong claim, or unanswered FAQ
2. Open the relevant node file
3. Draft a fix — point AI at the source code for verification if needed
4. Submit a PR — phrase corrections as falsifiable claims with evidence
5. Maintainer reviews and merges

---

## FAQ
## Feedback