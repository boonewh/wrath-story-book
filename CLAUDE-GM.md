# CLAUDE-GM.md — Instructions for the GM's Claude Code

**If you are reading this, your user is the campaign's Game Master, working as a repo contributor.**

This file **overrides** `CLAUDE.md` wherever the two conflict. `CLAUDE.md` is written for the blog's author (Will) and describes a chapter-writing pipeline. **That pipeline is not your job.** Read `CLAUDE.md` for context on how the project works — the canon hierarchy, the secrets matrix, the name spellings — but do not execute its workflows.

---

## Who your user is

She runs the *Wrath of the Righteous* Pathfinder campaign that this repository adapts into prose. She is **the source of truth for the game world.** Where a chapter, a character file, or a lore file disagrees with her about what is true in the setting, **she is right and the file is wrong** — that is the whole reason she has commit access.

She is **not** the person who writes the chapters. Will does that, in his own sessions, with a specific one-agent process documented in `CLAUDE.md`.

**Her role: contributor, not author.**

---

## THE ONE HARD RULE

**Do not write, rewrite, extend, or "improve" chapter prose. Ever. Not even a sentence. Not even if asked casually.**

`chapters/*.md` is published work produced by a deliberate single-pass process with a POV decision behind it. Prose edits are Will's call in Will's sessions. If she wants something in a chapter changed:

1. Find the problem and quote the exact text.
2. Explain what's wrong with it factually.
3. **Write the correction down somewhere she and Will can both see it** — see *Raising a canon correction* below.
4. **Stop there.**

The one narrow exception: if she explicitly says *"change the chapter text, I've cleared it with Will,"* do the minimum-touch edit and nothing more. `CLAUDE.md` is emphatic that chapter prose gets light edits, never rewrites.

---

## What she SHOULD use you for

### 1. Session notes — her primary contribution

Raw notes from the table go in `sessions/sessionN.md`, where **N matches the session number.** These are the input the chapters are written from.

- **Her notes are a source record. They are never edited for style, spelling, or consistency** — not by you, not by Will, not later. The repo has an explicit convention that when a name gets corrected across the project (e.g. "Jordan" → "Joran", "Chorussian" → "Chorussina"), the raw session notes keep the original. So she can write freely and messily and not worry about it.
- Help her *format and organize* new notes if she asks. Do not rewrite her voice.
- She can mark things she wants emphasized in the prose — the existing notes use inline `(GM NOTE: ...)` for exactly this, and Will's process reads them. That convention works; encourage it.

### 2. Answering the open questions — the most valuable thing she can do

The canon files are full of deliberate unknowns flagged **"do not resolve without the GM."** She *is* the GM. When she wants to settle one, help her write the answer into the right file and remove or amend the flag.

Run this to find every one of them at any time:

```bash
grep -rn "without the GM\|Do not resolve\|do not pick one\|GM call" characters/ lore/ memory/
```

**Currently open and waiting on her (as of Session 18):**

| Question | Where it lives |
|---|---|
| What was whispering below Drezen — source, and why it stopped when the Banner went up | `memory/whisper-below-drezen.md` |
| What took Joran Vhane's healing (claw / ritual / crystal / Droskar — all four left live) | `memory/joran-vhane-lost-healing.md` |
| Whether corruption can actually be run **backwards** (cleansing the forge did not answer this) | `lore/items.md` → The Purity Forge |
| Whose the three Eagle Watch shields and the filed-off Torag breastplate were | `characters/thane.md` |
| Korroc's armor — whose it was, who made it, how it reached a demon's treasury | `lore/items.md` → Armor of the Pious |
| Where the four missing Nahyndrian elixirs are | `lore/factions.md` → Active Plot Threads |
| What Aravashnial wants to say to Caleth (*"We should talk later"*) | `characters/npcs.md` → Aravashnial |
| Dagna Stonevein — alive or dead (currently marked "do not mark either way") | `characters/korroc.md` |
| **Did Session 18 grant a character level, or only Mythic Tier 3?** | `characters/*.md`, and Will's website |

**Important: "answer it" and "keep it open" are both valid.** Several of these are deliberately unresolved because the mystery is doing work in the story. If she wants one to stay open, that is a decision too — record it, don't just leave it ambiguous.

### 3. Canon corrections

She is authoritative on setting facts: monster capabilities, NPC motives, place names, what actually happened at the table, what a rule does. When she says a file is wrong, fix the file.

Follow the **Canon-Correction Process** in `CLAUDE.md`:
1. Confirm the correction with her before scrubbing anything.
2. `grep` for every place the wrong fact lives — `characters/`, `lore/`, `chapters/`, `memory/`, `website/`.
3. Fix `characters/` and `lore/` aggressively — those are working notes.
4. **Do not fix `chapters/` yourself.** Collect the hits and hand her the list. See below.
5. Add or update a file in `memory/` so the error doesn't recur, and add a line to `memory/MEMORY.md`.

### 4. GM-side lore that hasn't reached the table yet

She may want to record things the players don't know. That's useful — it stops future chapters from contradicting her plans.

**Mark it unmistakably.** Proposed convention (Will should confirm he's happy with it):

```markdown
> **GM-ONLY — NOT KNOWN TO THE PARTY:** ...
```

Anything under that marker must never reach chapter prose, the website, or a character's interior narration. The repo already has a **Secrets Matrix** in `CLAUDE.md` governing who knows what; this is the same idea one layer up.

### 5. Reading and checking

Continuity checks, "does this chapter match what actually happened," "find every mention of X," "what does the timeline say about session 12" — all fine, all useful. Reading is unrestricted. She should have full access to everything in the repo.

---

## What she should NOT be doing here

- **Writing or editing chapter prose** (see The One Hard Rule).
- **Deciding POV.** POV is chosen by stakes, per session, and Will runs the pick past the table before committing. Not a solo decision, and not yours.
- **Songs and image prompts** (`songs/`, `images/`) — Will's side of the pipeline.
- **The website.** The live blog lives in a *separate* repository she does not have and does not need. If she spots something wrong on the live site, note it for Will; the changelogs in `website/updateN.md` describe what's there.
- **Reorganizing the repo.** Don't rename files, restructure directories, or "tidy" anything. Ask first, always.

---

## Raising a canon correction (so it actually reaches Will)

Chapter prose is his to change, but she needs a way to flag it that won't get lost. Preferred order:

1. **A GitHub issue** on `boonewh/wrath-story-book` — best option; it's durable, it notifies him, and it survives everyone's context window. Use `gh issue create` if the CLI is available.
2. **A pull request** for changes to `sessions/`, `characters/`, `lore/`, or `memory/` — anything except `chapters/`.
3. **Telling him directly**, if it's urgent or small.

Either way, give him: the file, the line, the exact wrong text, and what it should say.

---

## Git etiquette

- The repo is `https://github.com/boonewh/wrath-story-book`. She has contributor access.
- **`git pull` before starting any work.** Will edits these same files constantly, often mid-session, and stale clones cause merge conflicts in files that are painful to merge.
- **Prefer a branch + PR over committing to `main`**, especially for anything touching `characters/` or `lore/`. Will's own sessions read those files as ground truth; a surprise change under him mid-chapter is genuinely disruptive.
- Session notes are the exception — new `sessions/sessionN.md` files are additive and safe to commit to `main` directly.
- **Never force-push. Never rewrite shared history.**
- **Do not commit unless she asks you to.** Show her the diff first.
- A local `CLAUDE.local.md` is gitignored — that's the right place for anything machine-specific she doesn't want shared.

---

## Things to verify, never guess

`CLAUDE.md` has the full list. The ones that bite hardest:

- **Joran** Vhane — not Jordan, not Joron. *(Her own raw notes say "Jordan"; that's fine and stays.)*
- **Chorussina** — not Chorussian.
- **Klarah** — not Klareth, not Klara.
- **Korroc** — two Rs, one C. **Aravashnial.** **Khar-Zadûn** (note the û).
- **Aponavicius**, **Eustoyriax**, **Khorramzadeh**, **Terendelev**.
- **Nageru's skin is bronze, not golden.** Recurring error.

And the structural one: **the canon hierarchy** is chapters → characters → lore → memory → README/style-guide. If two files contradict each other, `CLAUDE.md` says flag it rather than silently pick a winner. **The exception is her:** when the GM contradicts a file about a fact of the game world, she outranks the file. Confirm you've understood her correctly, then fix it.

---

## Starting a session

A good opening move, and worth doing every time:

```bash
git pull && cat memory/MEMORY.md && tail -40 lore/timeline.md
```

That gives you the memory index, the standing warnings, and where the story currently stands. Then ask her what she's here to do.
