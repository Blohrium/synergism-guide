# AI Instructions

## Navigation

Parent: [[README]] Hub

<!-- [[README]] -->

---

## Purpose

This node gives contributors enough context to use AI effectively when building or improving guide sections. The guide is verified against the [Synergism source code](https://github.com/pseudo-corp/SynergismOfficial) where possible — AI is a tool for drafting and cross-referencing, not a source of truth.

---

## Writing Principle

State each claim once, precisely. Connect explicitly. Elaborate nothing.

Connections between sections are load-bearing — they're non-recoverable from the core claim alone. Everything else is cut: restatement in different words, elaboration of elaboration, headers that announce what the prose is about to say.

**Failure modes to avoid:**

- Restatement — the same claim in slightly different words
- Elaboration of elaboration — a clarification of a clarification
- Filler confidence — "X leads to Y" stated without verifying against code

---

## Node Structure

Every section file follows this order:

1. Navigation (top, always)
2. Discord block (copy-paste ready, under 2,000 characters, in a code block)
3. Exhaustive content (everything else)
4. FAQ (common Discord questions with answers)
5. Feedback (perceived gaps or unclear sections)

---

## Discord Block Format

The Discord block is what gets copy-pasted as a pin. It lives inside triple backticks so GitHub doesn't try to render Discord-specific syntax. It should be self-contained and under 2,000 characters.

Navigation within Discord is via message links — placeholder until the message is posted, then filled in with the actual URL.

---

## Verification

Claims should trace to the source code. When giving AI the task of writing or improving a section:

- Point it to the [Synergism repo](https://github.com/pseudo-corp/SynergismOfficial)
- Ask it to verify specific mechanics before stating them
- Mark anything unverified with `> ⚠ unverified` so it's visible for review

AI fills gaps with plausible-sounding defaults when it doesn't know — the game changes frequently and those defaults go stale. Unverified claims are worse than gaps because they're invisible.

---

## Using FAQ and Feedback

**FAQ** — paste Discord questions here with answers. These are player-facing: things people actually ask in the progression channels. AI can use these as input to improve or expand section content.

**Feedback** — perceived gaps or unclear sections in the guide itself. Not player questions but contributor observations. Can overlap with FAQ when a repeated question signals a gap in the guide.

---

## Contribution Flow

1. Find a gap, wrong claim, or unanswered FAQ
2. Open the relevant section file
3. Use AI to draft a fix, pointed at the source code for verification
4. Submit a PR
5. Maintainer reviews and merges

Anyone with AI access can contribute. The source code is the authority — if AI and code disagree, code wins.

---

## FAQ

<!-- Paste common Discord questions here with answers -->

## Feedback

<!-- Perceived gaps or unclear sections in this node -->