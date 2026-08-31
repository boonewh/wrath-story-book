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
├── chapters/                    # Published chapters (NN-short-title.md; interludes are NN.5-)
├── characters/                  # PC + NPC reference files (canon source-of-truth)
│                                #   + chapter19-letters.md (the Ch 19 letters, full text)
├── lore/                        # factions.md, items.md, kenabres.md, worldwound.md, timeline.md
├── sessions/                    # Raw GM session notes (input to chapters)
├── songs/                       # Suno song lyrics per session
├── images/                      # Image generation prompts per session
├── website/                     # Per-session changelog of live-site updates
└── memory/                      # Claude memory system (persistent notes)
```

## Cross-Project Relationship

The live blog lives in a **separate repository** at `G:\Projects\games\`. Built with Next.js + TipTap. The relevant page is `src/app/wrath/page.tsx` (route: `/wrath`). The page has a section labeled `{/* CAMPAIGN ARC STATUS — REPLACE-NOT-APPEND ... */}` that must be updated per session.

When the blog page is updated, a matching `website/updateN.md` changelog file is written in *this* repo. Pattern set by `website/update4.md` — top matter, what changed (grouped by file path), files NOT touched, verification steps, cross-references.

The Vanguard section on the same page (`page.tsx:126`) displays Level/Mythic Tier; that line **must stay in sync** with the milestone footer at the bottom of the Campaign Arc Status section (`page.tsx:549–553`). An inline code comment marks it. **Both currently read Level 9 Gestalt / Mythic Tier 3** and were verified in sync during the Session 19 pass. Changelogs exist for sessions 4, 7, 9, 10, 11, 12, 13, 16, 17, 18 and 19.

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

Current repo memory files (14). **`memory/MEMORY.md` is the authoritative index and is kept current — read it, not this list, for the live wording.**

*Character and craft:*
- `aravashniel-riftwarden.md` — Aravashnial's Riftwarden identity is PUBLIC to the party as of Ch 11; the deeper layers (elder rank, Caleth connection, Caleth's Ch 4 knowledge) stay secret. *(Filename misspells his name; the file's content is correct.)*
- `korroc-stonelord.md` — Korroc's Stonelord paladin archetype + literal stone-in-veins
- `nageru-not-golden-skin.md` — Nageru's skin is bronze, NOT golden (recurring image-prompt error)
- `chapter-1-origin.md` — Ch 1 predates the POV-by-stakes system; quirks are intentional
- `webpage-session-section.md` — Design pattern for the live blog Campaign Arc Status section
- `session-4-prep.md` — Notes from the May 2026 character-file canon-correction pass

*The Stonevein family (read all four together — they supersede each other in sequence):*
- `stonevein-family-question.md` — **superseded:** the cousins DO share the Stonevein name; all four parents named in Ch 11 (Thorek + Helja are Thane's, Borin + Dagna are Korroc's)
- `thane-father-timeline.md` — the sons KNEW their fathers; the blueprints predate the sons' births. **⚠ PARTLY SUPERSEDED by `the-fathers-survived.md` — this file still says the fathers *died*. They did not.**
- `the-fathers-survived.md` — **⚠ THE BIGGEST CANON CHANGE SINCE THE WARDSTONE (Ch 19).** Thorek and Borin were captured, not killed; Staunton arranged the ambush; they dug twenty feet out over a year and vanished into the riverbed. **Where they went is open. Keep it open.**
- `stonevein-mothers-status.md` — Ch 19 settles both, and both files were wrong in opposite directions: **Helja is DEAD** (how and when is NOT established — do not invent it); **Dagna is ALIVE in Nerosyan** and means to come south. Drezen was the family's home.

*Open threads that must STAY open — do not explain, do not resolve off-screen:*
- `whisper-below-drezen.md` — NOT Chorussina's ritual. **Stopped in Ch 18 when the Banner went up — a coincidence in time, not a cause.** Source unknown. Nobody gets retroactive credit for stopping it.
- `joran-vhane-lost-healing.md` — four live causes (claw / ritual / crystal / Droskar); the GM left all four open. Do not pick one. *(Filename is `joran-vhane-lost-healing.md`; the front-matter `name:` inside still reads `jordan-`.)*
- `thane-unspoken-possession.md` — Thane has **never told anyone** he was possessed in Ch 18. Ch 19 walked him to the door and he could not open it. Must cost him something to say.
- `fane-of-irori.md` — Sister Lyra's charge to Nageru; its founders *"were waiting for something. Or perhaps someone."* Unlocated. **⚠ This is his next POV chapter, and do NOT make him the answer.**

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
- Chapter 17: **Thane** (*Every Name But Two* — Staunton's ledger, the butterfly cell, Chorussina, Joran's hands stop working)
- Chapter 18: **Korroc** (*The Mark It Chose* — Eustoyriax, Thane possessed, the true Sword of Valor, the armor takes Torag's mark)
- Interlude 2 / Ch 18.5: **Korroc** (*He Wouldn't Have to Ask* — the Purity Forge, Joran at the anvil, the working laid into Radiance)
- Chapter 19: **Thane** (*Twenty Feet of Stone* — the fathers survived, the letters from home, Jesker Helton in Delamere's tomb)

POV remains a stakes decision, not a rotation — choose whoever has the most at stake in a given session.

**⚠ NAGERU IS SIX CHAPTERS OVERDUE.** His last POV was Ch 13. He is also the only PC without a character song. `memory/fane-of-irori.md` flags the Irori fane as his chapter — but note its own warning: **receiving a summons is not the same as answering it.** A POV chapter about getting a letter is a chapter about waiting. Spend him when they actually go.

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
| **Thane was possessed by Eustoyriax in Ch 18 — and was conscious inside it the whole time** | The party saw the possession; **NOBODY knows he was awake in there, because he has never said one word about it** | Everyone. He made himself unaskable on purpose, in about four seconds. |
| **Caleth's Ch 15 wound** (the succubus wore Iomedae's face and compelled him past his own correct judgment) | Happened in front of the party | **No one has ever spoken of it, including him.** Refrain: *"knowing wasn't enough."* |
| Nageru's charge from Sister Lyra (the lost fane of Irori) | Nageru | The party knows only *"they also gave me something else to do."* **Thane deliberately did not ask, and offered hands instead. That debt is outstanding.** |
| Caleth can push charge back into spent items | **Now semi-public** — demonstrated on a forge floor in front of Korroc, Nageru and Aravashnial (Interlude 2) | Nobody understands the mechanism, **Caleth least of all** |

**⚠ The strongest unused material in the campaign:** two men in this party are carrying an unspoken thing a demon did to them — Thane (Ch 18) and Caleth (Ch 15) — **and neither knows about the other's.**

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
- **Thorek** + **Helja** — Thane's father and mother. **Borin** + **Dagna** — Korroc's father and mother. All four are **Stonevein**.
- **Eustoyriax** — the shadow demon who held the true Sword of Valor and possessed Thane (Ch 18)
- **Aponavicius** — the marilith who held Drezen; it was her vanity that spared the Banner
- **Chorussina** — the tiefling conjurer below Drezen *(see the correction note above)*
- **Jesker Helton** — the Erastilian priest recovered from **Delamere's** tomb (Ch 19)
- **Sister Lyra** — of the Order of Irori, at the Sunken Fist; **Elara** + **Kaelen** are Nageru's parents (Ch 19 letters)
- **Rennick** — the young paladin of Iomedae who spotted the changed mark on Korroc's breastplate (Ch 18)

### Party State at End of Chapter 19

*(Ch 19 is the last written chapter. Sessions 17, 18, 18.5 and 19 are all published; `sessions/` has notes through session 19.)*

**Advancement:** All four PCs are **Knights of the Fifth Crusade** and mythic — **Level 9 Gestalt, Mythic Tier 3.** The tier came in Session 18 with the taking of Drezen; **Session 19 granted no advancement.** The live blog page (Vanguard line + milestone footer) is verified in sync at Level 9 / Tier 3.

**Where they are and what they're doing:**
- **DREZEN IS TAKEN.** The citadel is held, the **Sword of Valor is RECOVERED (Ch 18)** and flies over it. **The objective of Book 2 is complete.**
- **The Queen's new mandate (Ch 19):** use Drezen as a base of operations and **explore the Wounded Lands to the south and west** for anything usable against the demons. Consult Sosiel, Aron, Irabeth on the region's history and legends. Reinforcements came north with the letter.
- At the close of Ch 19 the four are on a **night wagon ride back to Drezen** from Delamere's tomb, with the rescued Erastilian priest **Jesker Helton** asleep in the bed and Korroc sitting up over him.

**The Stonevein arc — the campaign's live engine:**
- **⚠ THE FATHERS SURVIVED (Ch 19).** Thorek and Borin were **captured, not killed**; **Staunton Vhane arranged the ambush**; they were put to work on the citadel they had helped build, dug **twenty feet** to a pre-fall water tunnel over better than a year, and escaped into the dry riverbed east of Drezen. **Neither is on the list of the dead. Neither was recorded as recaptured. WHERE THEY WENT IS OPEN — do not resolve it, do not kill them off-page, do not bring them back.**
- **The riverbed east of the walls is now a standing location with a claim on the party.** Aravashnial had the eastern bridge repairs moved up the list for exactly one reason: *"if you intend to find out where your fathers went, this is where their trail begins."* Aron's engineers open that ground over the following month.
- **Helja Stonevein is DEAD** (Thane's mother — *how and when is NOT established; do not invent it*). **Dagna Stonevein is ALIVE in Nerosyan**, wrote to both cousins in Ch 19, and intends to come south after seventy-five years. **Drezen was the family's home** — Dagna and Helja knew its streets first; the four met and became a family there.
- **Thane's banked flame has changed shape a third time.** Not vengeance, not the wrong record — *his father was a nuisance in a ledger for a year and dug his way out*, and Thane's private, unshared conclusion is ***"I could not have done that."*** Do not let him make peace with it quickly.
- **Thane means to write to Dagna about the fathers and has not yet.** Korroc owns the grief; Thane owns the investigation. Keep that split.
- **Staunton arranged the ambush and Staunton is dead** — killed in Ch 16 over Thane's explicit objection after he asked for the man alive (*"Three days,"* was his estimate). **That disagreement is now permanently unresolvable and neither cousin has spoken of it. Live thread.**

**Per character:**
- **Korroc** wears **the Armor of the Pious** — *not* "the Armor of Iomedae" any more. It is old craft that **takes the mark of whoever is inside it**, and in Ch 18 the sunburst became **Torag's hammer and anvil** with no ghost of the old mark underneath. The "something I should know" was **smith-lore, not a hidden past.** From Ch 18 he wears **Torag on shield and chest alike** — the two-gods reading is over. *(Whose suit it was, who made it, and how it reached a demon's treasury are all still open.)* He is modifying it at the Purity Forge; **what he is adding is not established — needs the GM.**
- **Thane** carries **his mother's blade, his father's knife, and a punch dagger he made himself** at the Purity Forge. The blade he wipes after every kill **is a dead woman's knife, and has been for some time.** He was **possessed by Eustoyriax in Ch 18** and has told no one he was awake inside it.
- **Caleth** carries **Radiance**, which now holds **a second working laid in at the Purity Forge** — Thane cut the channels, Caleth's own casting failed three times (*"It rejected an incompatible structure"* / *"It's got a latch already"*), and **Aravashnial seated it like a weld.** **⚠ WHAT THE WORKING DOES IS NOT ESTABLISHED — needs the GM before anything references it.** He still carries the Ch 15 wound (*"knowing wasn't enough"*), unspoken by anyone. The Drezen blueprints still ride folded in his spellbook.
- **The *"we should talk later"* conversation FINALLY HAPPENED (Interlude 2) — and settled nothing.** Aravashnial interrogated the recharging mechanism and Caleth answered *"I don't know"* to nearly all of it; a second attempt in one day produces nothing at all. The elf proposed a testing programme and **Caleth fled up a staircase to escape it.**
- **Nageru** received two letters in Ch 19 — one from his parents **Elara and Kaelen**, one from **Sister Lyra** charging him to find **a lost fane of Irori** near Drezen. He has told the party almost nothing. Lyra's line ***"There is always another step"*** has escaped into the story: he said it aloud on the night march, **Thane overheard and it landed hard, and Nageru does not know that.**

**NPCs and prisoners:**
- **STAUNTON VHANE IS DEAD** (Ch 16). **NURAH DENDIWHAR IS DEAD (Ch 18)** — she got out of her irons, began a teleport, **Aravashnial reversed it**, she was called on to surrender, chose to fight, and was killed. **She never reached the Queen.** Reported by Irabeth, not witnessed by the party. Thane: *"She made her choice."*
- **Joran Vhane** is **in custody in Drezen, working the Purity Forge under guard.** He **can no longer cast healing magic (Ch 17)** — four live causes, **do not pick one.** Korroc changed tactics after watching his own armor decide what it belonged to: *"I can't hammer a man into a shape."* He handed him a hammer instead. **He is not being redeemed by argument; he is being left alone next to an anvil.**
- **Jesker Helton** — Erastilian priest, rescued from Delamere's tomb in Ch 19, was possessed, and **Korroc offered him atonement, which has been offered and NOT yet performed.**
- **Queen Galfrey** is not at Drezen; her mandate arrived by letter. Irabeth, Anevia, Aravashnial, Aron, Sosiel, Horgus and Klarah are with the company.

**⚠ Threads deliberately left open — do NOT close any of these without the table:**
the whisper below Drezen (stopped, unexplained, no retroactive credit) · where the fathers went · how Helja died · Joran's lost healing · what Radiance's new working does · whose armor Korroc is wearing · the lost fane of Irori and what its founders were waiting for · four loose vials from Ch 19 · Thane's silence about the possession.

## Workflow Patterns

### Per-Session Chapter Writing Process

1. **Read** the new session notes in `sessions/`
2. **Decide POV** based on stakes (or use the one the user specified)
3. **Read** the previous chapter for voice continuity
4. **Read** the POV character's file in `characters/`
5. **Skim** relevant lore (factions, items, places mentioned in the session)
6. **Check** `memory/MEMORY.md` for secrets, open questions, and any "previous-Claude fabrication" warnings
7. **Write the chapter yourself**, in one sustained pass, with all of the above in context
8. **Save** the result as `chapters/NN-short-title.md` (chapter number matches session number; **interludes take the previous chapter's number plus `.5`** — see `08.5-` and `18.5-`)
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
- **Joran Vhane**, not Jordan/Joron (2026-08-11); **Chorussina**, not Chorussian (2026-08-16)
- **The Stonevein fathers did not die** (Ch 19) — eighteen chapters of "fallen, bodies never recovered" turned out to be a cover story the enemy built on purpose
- **Helja is dead / Dagna is alive** (Ch 19) — the character files had both wrong, in opposite directions
- **Korroc's armor is the Armor of the Pious**, not "the Armor of Iomedae" (Ch 18) — it wears Torag's mark now
- **American English** enforced from Ch 19 onward (2026-08-30); earlier files deliberately left alone

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
- **Do NOT write British spellings.** This project is **American English** — `gray`, never `grey`, plus *color / armor / honor / recognize / defense / traveling*. It applies to chapters, canon files, songs, image prompts and website changelogs alike. **Ch 19 onward is clean; Chapters 1–18.5 and older canon files were deliberately left alone (~90 instances) — do not sweep them without asking.** See `style-guide.md`.
- **Do NOT trust character names from your own memory alone.** Especially Klarah, Aravashnial, Khar-Zadûn. Always verify against the character file before writing.
- **Do NOT delete or rewrite chapter prose without the user's explicit approval.** Chapters are published; treat them as canon.
- **Do NOT use Korroc, Thane, or Nageru's POV to narrate Caleth's Riftwarden origin or the Caleth–Aravashnial connection.** Aravashnial being *a Riftwarden* is party-public as of Ch 11 — but his elder rank, the order's link to Caleth's parents, and the fact that Caleth knew since Ch 4 remain private to Caleth (and Aravashnial).
