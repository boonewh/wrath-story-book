# CLAUDE.md — Wrath of the Righteous Campaign Blog

## ⚠ WHO IS YOUR USER? (check this first)

This repo has two kinds of contributor and they get different instructions.

- **The author (Will).** Everything below this section is for you. Proceed.
- **The GM (campaign Game Master, repo contributor).** **Stop and read [CLAUDE-GM.md](CLAUDE-GM.md) instead, and follow it — it overrides this file wherever they conflict.** She does not write chapters; she supplies session notes, settles the canon questions this project has deliberately left open, and corrects the game-world facts. The chapter-writing pipeline below is **not** her workflow.

If you do not know which one you're talking to, **ask before writing anything.** The clone is identical either way; only the person differs.

---

## Model Architecture Rule

**ONE agent does everything. Opus reads, researches, decides, and writes. No hand-offs.**

- The main agent is **Opus**. It does the session-note reading, the canon research, the POV decision, the continuity checking, the chapter prose, the songs, the image prompts, the canon updates, and the web updates — all of it, in one continuous context.
- **Do NOT spawn sub-agents for creative work.** Do not spawn a "chapter-writer," a "song-writer," a "canon-keeper," or a "continuity-checker." The hand-off was the problem: the writing agent arrived with less context than the agent that did the reading, and the prose paid for it.
- Only use the Agent tool if the user explicitly asks for it.

*(Changed 2026-08-09. The project previously ran Sonnet-orchestrates / Opus-writes. Briefing a fresh Opus with a summary of research it did not itself do lost too much — the researching agent knows which details matter and why, and that knowledge does not survive being compressed into a prompt. One agent, whole context, start to finish.)*

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

The live blog lives in a **separate repository** at `G:\Projects\games\`. Built with Next.js + TipTap. The relevant page is `src/app/wrath/page.tsx` (route: `/wrath`). The page has a section labeled `{/* CAMPAIGN ARC STATUS — REPLACE-NOT-APPEND ... */}` that must be updated per session.

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

**The project's canon memory lives in this repo, at `memory/`**, indexed by `memory/MEMORY.md`. It is committed to git and survives machine failures. **Always read `memory/MEMORY.md` early in a session**, then read the files it points at.

There is also a machine-local Claude memory store at `C:\Users\boone\.claude\projects\G--Projects-wrath-story-book\memory\`. It is NOT backed up and was wiped by the August 2026 Windows reinstall — treat it as scratch. **Anything that matters to the campaign goes in the repo's `memory/`.**

Current repo memory files:
- `aravashniel-riftwarden.md` — Aravashnial's Riftwarden identity is PUBLIC to the party as of Ch 11; the deeper layers (elder rank, Caleth connection, Caleth's Ch 4 knowledge) stay secret. *(Filename misspells his name; the file's content is correct.)*
- `korroc-stonelord.md` — Korroc's Stonelord paladin archetype + literal stone-in-veins
- `nageru-not-golden-skin.md` — Nageru's skin is bronze, NOT golden (recurring image-prompt error)
- `stonevein-family-question.md` — **superseded:** the cousins DO share the Stonevein name; all four parents named in Ch 11 (Thorek + Helja are Thane's, Borin + Dagna are Korroc's)
- `thane-father-timeline.md` — the fathers died when the sons were children; the sons KNEW them. The blueprints predate the sons' births; the deaths do not.
- `chapter-1-origin.md` — Ch 1 predates the POV-by-stakes system; quirks are intentional
- `webpage-session-section.md` — Design pattern for the live blog Campaign Arc Status section
- `session-4-prep.md` — Notes from the May 2026 character-file canon-correction pass

**Lost in the August 2026 reinstall** (referenced by older docs, never committed, not recoverable): `drezen-geography-session12.md`, `staunton-sv-delayed-reveal.md`, `suno-song-constraints.md`, `korroc-thane-stonevein.md`. Their substance survives in `style-guide.md` (Suno rules) and the character files (Stonevein parents, Staunton reveal). Do not go looking for them.

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
- Chapter 8: **Korroc** (*The Stone Remembers* — the wardstone, the mythic explosion, Staunton at the fathers' table)
- Chapter 8.5: **Ensemble interlude** (*The Breathing Space* — downtime)
- Chapter 9: **Nageru** (*The Voice That Answers* — the Queen, the knighting, the march begins)
- Chapter 10: **Caleth** (*The House That Beauty Built* — the Chapel of Shelyn, the sabotage surfaces)
- Chapter 11: **Thane** (*The Latch That Held / What the Stone Remembers* — the traitor hunt, the Stonevein letter)
- Chapter 12: **Korroc** (*The Strain the Smith Takes / Half Your Wounds* — the foothold on Drezen's edge)
- Chapter 13: **Nageru** (*The Sound the Thunder Makes* — the cemetery, the Ahari, the stillness breaking)
- Chapter 14: **Thane** (*Who Has Business Inside / The False Credential* — Nurah caught, the watchtowers, into the citadel)
- Chapter 15: **Caleth** (*Beauty Has Teeth / What Wore the Inheritor's Face* — the false Iomedae, "knowing wasn't enough")
- Chapter 16: **Korroc** (*Two Brothers of the Same Forge / The Price of Working with Demons* — Staunton dies, Joran kneels)

POV remains a stakes decision, not a rotation — choose whoever has the most at stake in a given session.

### Secrets Matrix

Who knows what. The POV character can only narrate what they know — never let a POV character's interior reveal a secret they don't share.

| Secret | Who Knows | Who Doesn't |
|---|---|---|
| Caleth's Spireborn lineage | Caleth, Aravashnial | The party reads it as background, not as identity |
| Caleth's Riftwarden Orphan status / Seeker's Spiral on his shoulder | Caleth, Aravashnial | Korroc, Thane, Nageru, Anevia, Horgus, Klarah |
| Aravashnial is **a Riftwarden** | **PUBLIC to the whole party as of Ch 11** (he closed the Abyssal rift and said so) | Public NPCs / the wider army |
| **Aravashnial's deeper layers:** his *elder* rank, his link to Caleth's parents' order, the Blackwing as Riftwarden stronghold, **and that Caleth knew since Ch 4** | Caleth, Aravashnial | Korroc, Thane, Nageru, everyone else |
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
- **Chorussina** — the tiefling conjurer below Drezen. *(Ch 16 originally spelled her "Chorussian" off a mishearing; corrected across all files 2026-08-16. Only `sessions/session16.md`, the raw GM note, still carries the old spelling — leave it, source records are not edited.)*
- **Joran Vhane** — Staunton's brother. **Joran**, not Jordan and not Joron. *(The GM's session notes write "Jordan" and some player after-action reports write "Joron" — both wrong. Corrected across all files 2026-08-11 at the table's request. The raw `sessions/*.md` notes still carry "Jordan"; source records are not edited.)*

### Party State at End of Chapter 16

- All four PCs are **Knights of the Fifth Crusade** and **mythic** — **Level 9, Mythic Tier 2** as of Session 16. *(The live blog page still shows Level 8 in two places; both update with the Session 16 web pass.)*
- **The four are inside Citadel Drezen**, clearing it from the roof downward, while Irabeth's army fights up the Ahari below and appears to be winning.
- **STAUNTON VHANE IS DEAD** (Ch 16) — killed by Caleth, after Thane's daggers broke him and Korroc refused Thane's request to take him alive. The Templar chain he could have named died with him.
- **The saboteur is caught:** **Nurah** confessed in Ch 14 — a Templar agent recruited by Minagho — and is bound and gagged under guard, awaiting return to the Queen. *The "keep her ambiguous" rule is retired.*
- **Joran Vhane**, Staunton's ill-used brother and a **worshipper of Droskar the Dark Smith**, has **surrendered to Korroc personally** and agreed to reveal where the Sword of Valor is. Unproven; Korroc owns this thread.
- **The Sword of Valor is NOT recovered.** The upper-citadel Banner was a decoy. The true one is **below**, in new chambers that appear on no dwarven map — including the Stonevein blueprints.
- **Korroc wears gold-and-mithral Iomedaean armor** (Ch 15) that fits him as though forged for him. **He feels he ought to know why and cannot. Do not explain it.**
- **Caleth carries an unhealed wound from Ch 15:** a succubus wearing Iomedae's face compelled him past his own correct judgment and drained him. His refrain is *"knowing wasn't enough."* **No one in the party has ever spoken of it.**
- **Caleth can push charge back into spent magic items** (Ch 14) — and **Aravashnial said "We should talk later." That conversation has not happened.**
- The Drezen blueprints still ride folded in Caleth's spellbook and have been navigating the citadel since Ch 14.
- Klarah, Horgus, Anevia, Aron, Sosiel remain with the company at camp. Queen Galfrey stayed at Kenabres.

## Workflow Patterns

### Per-Session Chapter Writing Process

1. **Read** the new session notes in `sessions/`
2. **Decide POV** based on stakes (or use the one the user specified)
3. **Read** the previous chapter for voice continuity
4. **Read** the POV character's file in `characters/`
5. **Skim** relevant lore (factions, items, places mentioned in the session)
6. **Check** `memory/MEMORY.md` for secrets, open questions, and any "previous-Claude fabrication" warnings
7. **Write the chapter yourself**, in one sustained pass, with all of the above in context
8. **Save** the result as `chapters/NN-short-title.md` (chapter number matches session number)
9. **Canon-update pass:** update character files (Established Moments + Current State), lore files, npcs.md as needed
10. **Web-update pass:** update `games/src/app/wrath/page.tsx` Campaign Arc Status section + write `website/updateN.md`
11. **Song:** write `songs/sessionN.md`
12. **Image prompt:** write `images/sessionN.md`

**The user often wants steps 8-12 spread across multiple turns, not done all at once.** Check before bundling.

**Never skip step 9 to get to the next chapter.** The canon files are the only durable record of what the prose established; a chapter written against stale character files loses the previous session's gains. (Sessions 14–15 were written and the canon pass was lost in a disk failure — it had to be reconstructed from the chapter prose.)

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

## The Jobs (all done by the one agent)

These are phases of work, **not** sub-agents to delegate to. Same agent, same context, one after another.

- **Chapter.** Session notes + POV decision + style guide + previous chapter for voice + relevant canon → the full chapter in one sustained pass. **Do not split a chapter across passes or agents — voice fractures.**
- **Song.** A Suno song for the session, or for a character. **THE ONE HARD LIMIT IS THE STYLE BOX: ~1,000 characters MAX, spaces included — Suno rejects anything over (tested: 1,054 was over).** The **lyrics box is NOT capped at 1,000** — that old rule was wrong. Suno accepts full-length lyrics (3,000+ chars confirmed in testing), so write the song to its proper length and do not truncate. Keep section tags short and put instrumentation/voice/tempo in the style box — but a *short* performance cue inside a tag (e.g. `[Verse - double time]`) is fine when it's needed to force a specific delivery. Single-register beats a four-stage build (Suno can't handle genre transitions). **No hard runtime cap** — let the song run its natural length; only ask for "no instrumental padding" if you actually want it tight. See `style-guide.md` → "Song Writing Rules (Suno)".
- **Image prompt.** A cinematic image-generation prompt for the session. Follow the format in `images/session3.md` and `images/session4.md`.
- **Web update.** Update the `wrath/page.tsx` Campaign Arc Status section + write `website/updateN.md`. Follow `memory/webpage-session-section.md`.
- **Canon pass.** Update affected character files, lore files, and `npcs.md`. Targeted edits; no creative prose.
- **Continuity check.** Verify the finished chapter against the canon files; flag contradictions to the user.

## What NOT to Do

- **Do NOT hand creative work to a sub-agent.** One agent — you — does the reading, the deciding, and the writing. See *Model Architecture Rule*.
- **Do NOT invent canon.** If a session note is unclear, ASK the user; do not fill gaps with plausible invention.
- **Do NOT reveal secrets through narration.** The POV character can only narrate what they know.
- **Do NOT update the live web page's Campaign Arc Status section by appending.** Always REPLACE the content; the section is a current-state window, not an archive.
- **Do NOT skip writing the matching `website/updateN.md`** when the page is updated.
- **Do NOT batch chapter writing + canon updates without checking with the user** — they often want these in separate turns.
- **Do NOT trust character names from your own memory alone.** Especially Klarah, Aravashnial, Khar-Zadûn. Always verify against the character file before writing.
- **Do NOT delete or rewrite chapter prose without the user's explicit approval.** Chapters are published; treat them as canon.
- **Do NOT use Korroc, Thane, or Nageru's POV to narrate Caleth's Riftwarden origin or the Caleth–Aravashnial connection.** Aravashnial being *a Riftwarden* is party-public as of Ch 11 — but his elder rank, the order's link to Caleth's parents, and the fact that Caleth knew since Ch 4 remain private to Caleth (and Aravashnial).
