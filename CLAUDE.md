# CLAUDE.md — Wrath of the Righteous Campaign Blog

## Model Architecture Rule

**Sonnet is always the orchestrator. Opus is always the creative writer.**

- Sonnet handles all planning, file reads, note-taking, canon updates, continuity checks, and session scaffolding.
- When it is time to write a chapter, a song, an image prompt, or any other creative prose, Sonnet spawns an Opus sub-agent (using `model: "opus"` in the Agent tool) and passes it the full context: style guide, session notes, relevant character files, prior chapters, and any specific instructions.
- Opus returns the finished prose; Sonnet handles all follow-up (saving the file, updating canon, writing the per-session changelog).

This rule applies to every creative task, no exceptions. **Do not write story prose, songs, or image prompts as the Sonnet main agent.**

## Project Overview

Long-running creative writing project adapting weekly Pathfinder *Wrath of the Righteous* RPG sessions into novel-style fantasy prose. Each chapter is published as a blog entry on a separate web project (see Cross-Project Relationship below). Final length: approximately 60 chapters across the Wrath of the Righteous adventure path.

Party plays Saturdays. Blog gets written between sessions.

**Read [README.md](README.md) and [style-guide.md](style-guide.md) at the start of every session for the full project brief.**

## Repository Layout

```
wrath-story-book/
├── CLAUDE.md                    # This file
├── README.md                    # Project brief + chapter-writing process
├── style-guide.md               # Prose rules (READ BEFORE writing creative prose)
├── chapters/                    # Published chapters (NN-short-title.md)
├── characters/                  # PC + NPC reference files (canon source-of-truth)
├── lore/                        # factions.md, items.md, kenabres.md, worldwound.md
├── sessions/                    # Raw GM session notes (input to chapters)
├── songs/                       # Suno song lyrics per session
├── images/                      # Image generation prompts per session
├── website/                     # Per-session changelog of live-site updates
└── memory/                      # Claude memory system (persistent notes)
```

## Cross-Project Relationship

The live blog lives in a **separate repository** at `c:\Users\William Boone\Desktop\Websites\games\`. Built with Next.js + TipTap. The relevant page is `src/app/wrath/page.tsx` (route: `/wrath`). The page has a section labeled `{/* CAMPAIGN ARC STATUS — REPLACE-NOT-APPEND ... */}` that must be updated per session.

When the blog page is updated, a matching `website/updateN.md` changelog file is written in *this* repo. Pattern set by `website/update4.md` — top matter, what changed (grouped by file path), files NOT touched, verification steps, cross-references.

The Vanguard section on the same page (around line 125) displays Level/Mythic Tier; that line **must stay in sync** with the Status Box footer at the bottom of the Campaign Arc Status section. An inline code comment marks it.

## Canon Hierarchy

When facts conflict, this is the priority order:

1. **The latest chapter file in `chapters/`** — published prose is canon
2. **The character files in `characters/`** — source-of-truth for PC/NPC details
3. **The lore files in `lore/`** — factions, items, places, the Worldwound
4. **Memory files in `memory/`** — supplementary context and do-not-reveal flags
5. **README.md and style-guide.md** — project rules

If any of these contradict each other, **flag it to the user**; do not silently choose.

## Memory System

Memory files live at `C:\Users\William Boone\.claude\projects\c--Users-William-Boone-Desktop-Pathfinder-wrath-story-book\memory\` and are auto-loaded into context via the index file `MEMORY.md`. **Always check `memory/MEMORY.md` early in a session.**

Key memory files at time of writing:
- `aravashniel-riftwarden.md` — SECRET: Aravashnial is a Riftwarden elder; Caleth knows as of Ch 4
- `korroc-stonelord.md` — Korroc's Stonelord paladin archetype + literal stone-in-veins
- `nageru-not-golden-skin.md` — Nageru's skin is bronze, NOT golden (recurring image-prompt error)
- `stonevein-family-question.md` — Korroc/Thane share Stonevein surname? OPEN
- `chapter-1-origin.md` — Ch 1 predates the POV-by-stakes system; quirks are intentional
- `webpage-session-section.md` — Design pattern for the live blog Campaign Arc Status section
- `session-4-prep.md` — Notes from the May 2026 character-file canon-correction pass

## Critical Continuity (Do Not Forget)

### POV-by-Stakes

Each chapter uses **Joe Abercrombie's POV-by-stakes structure** — written in deep third-person limited from whichever character has the most at stake in a given session. NOT strict rotation. POV decisions live in chapter craft, not in a calendar.

Established POVs so far:
- Chapter 1: **Korroc** (accidental — predates the POV system)
- Chapter 2: **Caleth**
- Chapter 3: **Thane**
- Chapter 4: **Korroc** (his first true mythic awakening — the Life Oracle fire-elemental form)
- Chapter 5: **Nageru** (*The Patient Thunder / The Open Fist* — his first POV, the Gwerm Manor defense / reunion)
- Chapter 6: **Caleth** (*The Blade That Chooses* — Radiance chooses him)
- Chapter 7: **Thane** (*The Threshold and the Bar / No Honest Tenants* — the Gray Garrison breach)

**Nageru has had his first POV (Chapter 5).** POV remains a stakes decision, not a rotation — choose whoever has the most at stake in a given session.

### Secrets Matrix

Who knows what. The POV character can only narrate what they know — never let a POV character's interior reveal a secret they don't share.

| Secret | Who Knows | Who Doesn't |
|---|---|---|
| Caleth's Spireborn lineage | Caleth, Aravashnial | The party reads it as background, not as identity |
| Caleth's Riftwarden Orphan status / Seeker's Spiral on his shoulder | Caleth, Aravashnial | Korroc, Thane, Nageru, Anevia, Horgus, Klarah |
| **Aravashnial is a Riftwarden elder** | Caleth (as of Ch 4), Aravashnial | Korroc, Thane, Nageru, others |
| The fate of Caleth's biological parents | No one in the party knows | Caleth seeks it |
| Caleth's Terendelev recognition / dream | Caleth | The rest of the party |
| Thane + Anevia's Eagle Watch contract | Thane, Anevia, Caleth (Ch 3 reveal), Korroc (partial) | Nageru |
| Anevia + Irabeth are married | Party learned in Ch 4 (Anevia knew always) | Public NPCs |
| Nageru's Lawbringer / Sunken Fist origin | Mostly internal to Nageru | Party doesn't have the full shape |

### Name Spellings (verify against `characters/` before writing)

- **Klarah** (orphaned child rescued in Ch 4) — NOT Klareth, NOT Klara
- **Aravashnial** — elder wizard / Riftwarden
- **Korroc** — two Rs, one C (Korroc, not Karroc or Korac)
- **Khorramzadeh** — the Balor Lord / Storm King
- **Khar-Zadûn** — the lost Dwarven Sky City (note the û accent)
- **Terendelev** — the silver dragon
- **Nageru** — the aasimar; **bronze skin** (NOT golden), amber eyes, subtle golden *aura* only

### Party State at End of Chapter 4

The party is **SPLIT**:
- **Strike team in the Blackwing Library:** Korroc, Caleth, Thane, Anevia, Aravashnial + 4 rescued librarians
- **At Gwerm Manor:** Horgus, Klarah, Nageru
- They have **NOT yet reunited**. Reconnection is a Session 5 beat.

## Workflow Patterns

### Per-Session Chapter Writing Process

1. **Read** the new session notes in `sessions/`
2. **Decide POV** based on stakes (or use the one the user specified)
3. **Read** the previous chapter for voice continuity
4. **Read** the POV character's file in `characters/`
5. **Skim** relevant lore (factions, items, places mentioned in the session)
6. **Check** `memory/MEMORY.md` for secrets, open questions, and any "previous-Claude fabrication" warnings
7. **Spawn ONE Opus sub-agent** with the full briefing to write the chapter
8. **Save** the result as `chapters/NN-short-title.md` (chapter number matches session number)
9. **Canon-update pass:** update character files (Established Moments + Current State), lore files, npcs.md as needed
10. **Web-update pass:** update `games/src/app/wrath/page.tsx` Campaign Arc Status section + write `website/updateN.md`
11. **Song:** spawn Opus to write `songs/sessionN.md`
12. **Image prompt:** spawn Opus to write `images/sessionN.md`

**The user often wants steps 8-12 spread across multiple turns, not done all at once.** Check before bundling.

### Canon-Correction Process

When the user identifies that something in canon is wrong (a previous Claude invented a fact, a player corrected a detail, the GM updated lore):

1. **Confirm the correction with the user** before scrubbing canon
2. **Find all places the wrong fact lives** — grep across `characters/`, `lore/`, `chapters/`, `memory/`
3. **Fix character/lore files aggressively** — those are private notes; clean cuts are fine
4. **Fix chapter prose LIGHTLY** — chapters are published; the user prefers minimum-touch edits
5. **Add a memory file** so future Claude doesn't repeat the error
6. **Flag the correction** in any lore-entry notes (`> NOTE (file pass, date): ...`)

Past canon corrections worth knowing:
- Caleth wears traveling clothes + crusader tabard, NOT scholarly wizard robes
- Caleth does not display Shelyn's sigil (private faith)
- Nageru has bronze skin, NOT golden (golden aura is separate, subtle)
- Aravashnial is a Riftwarden (Ch 4 reveal — secret from rest of party)
- Klarah's name — was briefly typo'd as Klareth in earlier drafts

## Sub-Agent Roles

When spawning sub-agents, give each a clear role and full briefing. Suggested roles for this project:

- **chapter-writer (Opus)** — given session notes + POV character + style guide + recent chapter for voice + relevant canon, writes the full chapter in one sustained session. **Do NOT split a chapter across multiple agents — voice fractures.** One Opus per chapter.
- **song-writer (Opus)** — given the chapter (or a character/theme brief), writes a Suno song. **THE ONE HARD LIMIT IS THE STYLE BOX: ~1,000 characters MAX, spaces included — Suno rejects anything over (tested: 1,054 was over).** The **lyrics box is NOT capped at 1,000** — that old rule was wrong. Suno accepts full-length lyrics (3,000+ chars confirmed in testing), so write the song to its proper length and do not truncate. Keep section tags short and put instrumentation/voice/tempo in the style box — but a *short* performance cue inside a tag (e.g. `[Verse - double time]`) is fine when it's needed to force a specific delivery. Single-register beats a four-stage build (Suno can't handle genre transitions). **No hard runtime cap** — let the song run its natural length; only ask for "no instrumental padding" if you actually want it tight. See `style-guide.md` "Song Writing Rules (Suno)" and memory `suno-song-constraints.md`.
- **image-prompt-writer (Opus)** — given the chapter, writes a cinematic image generation prompt. Follow the format set by `images/session3.md` and `images/session4.md`.
- **web-updater (Opus)** — given the chapter, updates the `wrath/page.tsx` Campaign Arc Status section + writes `website/updateN.md`. Follow `memory/webpage-session-section.md`.
- **canon-keeper (Sonnet)** — after a chapter lands, updates affected character files, lore files, and `npcs.md` with new canon. Targeted Edits; no creative prose.
- **continuity-checker (Sonnet)** — given a chapter draft, verifies against existing canon files. Flags contradictions.

These are not yet formalized in `.claude/agents/` — they're informal patterns. The orchestrator can spawn ad-hoc Agent tool calls following these patterns until/unless formal definitions are added.

## What NOT to Do

- **Do NOT write creative prose as Sonnet.** Spawn Opus for all creative work.
- **Do NOT invent canon.** If a session note is unclear, ASK the user; do not fill gaps with plausible invention.
- **Do NOT reveal secrets through narration.** The POV character can only narrate what they know.
- **Do NOT update the live web page's Campaign Arc Status section by appending.** Always REPLACE the content; the section is a current-state window, not an archive.
- **Do NOT skip writing the matching `website/updateN.md`** when the page is updated.
- **Do NOT batch chapter writing + canon updates without checking with the user** — they often want these in separate turns.
- **Do NOT spawn parallel Opus agents to co-write a single chapter** — voice fractures. One Opus per chapter.
- **Do NOT trust character names from your own memory alone.** Especially Klarah, Aravashnial, Khar-Zadûn. Always verify against the character file before writing.
- **Do NOT delete or rewrite chapter prose without the user's explicit approval.** Chapters are published; treat them as canon.
- **Do NOT use Korroc, Caleth, or Thane's POV to narrate Caleth's Riftwarden origin or Aravashnial's identity.** Those are private to Caleth (and Aravashnial).
