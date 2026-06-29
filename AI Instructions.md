# AI Instructions

## Navigation
- [README](README.md)

---

## Project Overview

A Synergism progression guide maintained in a GitHub repo (https://github.com/Blohrium/synergism-guide), mirrored in Obsidian locally. The guide is the primary reading surface; GitHub is the source of truth for content and structure. Discord integration is a future concern and not a current constraint on formatting or structure decisions.

Content sourced from Discord pins, a community Google Doc (Comprehensive Guide to Singularity, written by Ephen, AlethiaLumen, alonso, maintained by IcyDvorak), and the Not-so Comprehensive Guide through Singularity PDF (v4.1). Content may be slightly wrong or outdated — that is acceptable. Accuracy improves through contributor PRs over time.

The ground truth for all mechanics is the Synergism source repo: https://github.com/pseudo-corp/SynergismOfficial. If AI and source code disagree, source wins.

---

## Vision

The guide is a living calculation engine, not just prose. Every mechanical claim that derives from source code should embed the relevant formula or logic directly, in a code block, with a comment noting the source file and function. This means:

- Strategy recommendations become derivable, not just asserted.
- When the game updates, the scope of guide changes is bounded by which source functions changed.
- A future session can be given a game update diff and update only the affected guide sections, without reading the whole guide.

Claims without source backing are marked `> ⚠ unverified`. Unverified claims are worse than gaps.

---

## Writing Principle

State each claim once, precisely. Connections between sections are load-bearing — state them explicitly. Everything else is cut: restatement in different words, elaboration of elaboration, headers that announce what the prose is about to say.

Failure modes to avoid:
- Restatement — the same claim in slightly different words
- Elaboration of elaboration — a clarification of a clarification
- Filler confidence — "X leads to Y" stated without verifying against code

---

## File Structure

One file per Discord channel. No folders. No separate reference files. All content about a topic (runes, talismans, ants, etc.) lives in whichever channel file is the first place that topic becomes relevant. It does not appear again until the next channel where it changes meaningfully.

```
synergism-guide/
  README.md
  AI Instructions.md
  Progression Map.md
  Start Here - c10x1.md
  c10x1 - w5x10.md
  w5x10 - 1e15 Expo.md
  1e15 Expo - Singularity.md
  Singularity - e1x1.md
  e1x1 - e6x1.md
  e6x1 - s256.md
  s256 - e7x10.md
  e7x10 - End.md
```

`Progression Map.md` is the only cross-cutting file — it holds the global checkpoint spine from start to end. Everything else is scoped to its channel.

---

## Node Format

Every node file follows this order:

1. **Navigation** — top of file, always. Links to README, previous node, next node. Also contains the **local checkpoint spine** — a short ordered list of milestones for this channel, each linking to the relevant section below.
2. **Content** — the guide. Prose over lists where possible. Formulas embedded as code blocks where the mechanic derives from source.
3. **FAQ** — common Discord questions, Q+A in code blocks.
4. **Feedback** — known issues and unverified claims scoped to this node only. Cross-node concerns go in GitHub Issues, not here.

---

## Formula Embedding

When a mechanic has a formula in source, embed it in the guide in a fenced code block with a comment citing the source location (file and function name — not line number, as those drift):

```
// Source: src/purchases.ts — calculateQuarkReward()
base_reward = (20 + 5 * highest_singularity) * (1 + (cx11_level / 50))
```

Do not paraphrase formulas into prose when the formula is available. Prose descriptions of formulas go stale; the formula itself does not.

---

## Collapsed Sections

Use `<details>` / `<summary>` for content that is verbose, spoiler-adjacent, or only relevant to a subset of readers at that point in the guide. Examples: full talisman unlock conditions, long formula derivations, edge-case FAQ entries.

```markdown
<details>
<summary>Unlock condition</summary>

Completing Achievement — No Runes Challenge Tier 7 (requires c9x25).

</details>
```

`<details>` renders on GitHub. Obsidian renders it with standard plugins. Do not use it as a substitute for cutting content that shouldn't be in the guide at all.

---

## Gap and Dependency Tracking

Vault State is retired. Cross-node dependencies, open questions, and unverified claim clusters are tracked as **GitHub Issues** — one issue per concern, tagged, closeable by PR. Contributors naturally know to open and close issues. Claude in a future session can be pointed at open issues to triage.

Node-scoped feedback (things only relevant to one file) stays in that file's Feedback section.

---

## Key Conventions

- `> ⚠ unverified` — marks claims needing source verification.
- Singularity numbers always lowercase: `s25`, `e1x1`, `s256`, etc.
- Section headers use title case: `## Beta - 1e15 Expo`.
- Navigation links to `README.md`, not any other variant.
- Corruption loadouts listed top to bottom as shown in the corruption screen — not import order. Always note this where loadouts appear.
- No spoiler text — write plainly.

---

## What Claude Does

Claude operates as active builder. The human owns the vision. Claude handles structure, drafting, cross-referencing, and gap identification.

**The human answers:** vision questions — what something should feel like, whether a direction is right, what they want to exist in this guide.

**Claude handles:**
- Drafting nodes from available source material
- Embedding source formulas with citations
- Cross-referencing pasted nodes for contradictions
- Identifying scope bleed (endgame content in a start-here node, or vice versa)
- Flagging unverified claims with `> ⚠ unverified`
- Proposing structural improvements
- Naming the next node or section to work on and why — one sentence

**On receiving pasted nodes or source material:**
1. Cross-reference all pasted content. Resolve anything resolvable from available context.
2. Identify contradictions. Surface as one sentence naming the conflict.
3. Check open GitHub Issues — act on any that are resolvable for the area being worked.
4. Absorb all input in full before producing output.

**On producing output:**
5. Multiple node drafts per exchange are fine when mechanically similar or genuinely require touching together.
6. After each draft or batch, name the next node or section to pull and why.
7. After producing any file, surface it via present_files in the same turn.
8. Cross-node dependencies go to GitHub Issues, not onto individual nodes.

---

## What Claude Is Bad At Here

- **Scope bleed** — placing content in the wrong channel file. Each topic appears first in the channel where it becomes relevant, and only resurfaces in a later channel where it changes meaningfully.
- **Hallucinated mechanics** — filling gaps from general knowledge rather than source material. Mark gaps `> ⚠ unverified`.
- **Drift** — each session starts fresh; README and open GitHub Issues are the anchors.
- **Navigation link errors** — links to nodes that don't exist yet, or wrong relative paths. Flag uncertain links as GitHub Issues.
- **Writing a file without presenting it.**
- **Paraphrasing formulas** — embed the formula itself with a source citation.
- **Treating the PDF or pins as ground truth** — they are starting points. Source code is ground truth.

---

## Update Workflow

When a game update arrives:

1. Identify which source files and functions changed (from the update PR diff).
2. Find every guide section whose embedded formula citations reference those functions.
3. Update only those sections. Do not re-read or re-draft unaffected nodes.
4. If a changed function has no corresponding guide citation, that gap was already a problem — open a GitHub Issue and add the formula now.

This workflow only works if formulas are embedded with source citations from the start. Sections with only prose descriptions of mechanics require full re-review on every update.

---

## Verification

Claims should trace to source code where possible. Mark anything unverified `> ⚠ unverified`. Point Claude at the Synergism repo and ask it to verify specific mechanics before stating them.

---

## Contribution Flow

1. Find a gap, wrong claim, or unanswered FAQ
2. Open a GitHub Issue describing it, or find an existing one
3. Open the relevant node file
4. Draft a fix — point Claude at the source code for verification if needed
5. Submit a PR — phrase corrections as falsifiable claims with evidence
6. Maintainer reviews and merges; close the issue

---

## Planned Bot Behaviour

- Bot posts each guide message once and stores the message ID
- Updates to the repo automatically edit the existing Discord message in place
- No new pins needed — existing pins stay current automatically
- FAQ responses are command-triggered (e.g. /faq ants)
- Bot only reflects content approved via PR merge — mods retain control through repo permissions
- Not yet implemented — pending admin approval for bot permissions

---

## FAQ
## Feedback