# CLAUDE.md — Wrath of the Righteous Campaign Blog

## ⚠ WHO IS YOUR USER? (check this first)

This repo has two kinds of contributor and they get different instructions.

- **The author (Will).** Everything below this section is for you. Proceed.
- **The GM (campaign Game Master, repo contributor).** **Stop and read [CLAUDE-GM.md](CLAUDE-GM.md) instead, and follow it — it overrides this file wherever they conflict.** She does not write chapters; she supplies session notes, settles the canon questions this project has deliberately left open, and corrects the game-world facts. The chapter-writing pipeline below is **not** her workflow.

If you do not know which one you're talking to, **ask before writing anything.** The clone is identical either way; only the person differs.

---

## Model Architecture Rule

**ONE agent does everything. Opus reads, researches, decides, and writes. No hand-offs.**

- The main agent is **Opus**. It does the session-note reading, the canon research, the POV decision, the continuity checking, the chapter prose, the songs, the canon updates, and the web updates — all of it, in one continuous context. *(Image prompts used to be on this list and are now deprecated — see step 12 below.)*
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

The Vanguard section on the same page shows **level and mythic tier together in its header** ("Level 10 Gestalt · Mythic 4"), and the Campaign Arc Status milestone footer shows **Book / Mythic Tier / Level**. **The two must stay in sync**; an inline code comment marks both. *(Session 21 briefly split tier onto the individual Vanguard cards because tiers had diverged; Session 22 brought all four level again and the per-card field was removed. If they ever diverge again, restore the per-card `tier` and a footer range.)* **As of the Session 22 pass: Level 10; ALL FOUR at Mythic Tier 4; the footer range collapses to "Mythic Tier 4".** See `memory/mythic-tiers-personal-quests.md`. Changelogs exist for sessions 4, 7, 9, 10, 11, 12, 13, 16, 17, 18, 19, 20, 21, 22, 23 and 24.

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

Current repo memory files (28, plus the index). **`memory/MEMORY.md` is the authoritative index and is kept current — read it, not this list, for the live wording.**

*Character and craft:*
- `aravashniel-riftwarden.md` — Aravashnial's Riftwarden identity is PUBLIC to the party as of Ch 11; the deeper layers (elder rank, Caleth connection, Caleth's Ch 4 knowledge) stay secret. *(Filename misspells his name; the file's content is correct.)*
- `korroc-stonelord.md` — Korroc's Stonelord paladin archetype + literal stone-in-veins
- `nageru-not-golden-skin.md` — Nageru's skin is bronze, NOT golden (recurring image-prompt error)
- `chapter-1-origin.md` — Ch 1 predates the POV-by-stakes system; quirks are intentional
- `webpage-session-section.md` — Design pattern for the live blog Campaign Arc Status section
- `session-4-prep.md` — Notes from the May 2026 character-file canon-correction pass

*The Stonevein family (read all five together — they supersede each other in sequence):*
- `stonevein-family-question.md` — **superseded:** the cousins DO share the Stonevein name; all four parents named in Ch 11 (Thorek + Helja are Thane's, Borin + Dagna are Korroc's)
- `thane-father-timeline.md` — the sons KNEW their fathers; the blueprints predate the sons' births. **⚠ PARTLY SUPERSEDED — its "died in the Fourth Crusade" framing is wrong: captured (Ch 19), escaped, died afterward (Ch 24).**
- `the-fathers-survived.md` — **(Ch 19)** Thorek and Borin were captured, not killed; Staunton arranged the ambush; they dug twenty feet out over a year and escaped into the riverbed. **⚠ Its "where they went is open" rule is RETIRED by Ch 24.**
- `the-fathers-are-buried.md` — **⚠ (Ch 24) BOTH FATHERS ARE DEAD, buried at Sesker's Gully.** Borin died of his wounds there and Thorek buried him; Thorek went on, died somewhere unknown, and **two unknown humans carried him back.** Dagna ruled they stay. **The GM closed the thread** — the two humans are a question, not a hook.
- `stonevein-mothers-status.md` — Ch 19 settles both, and both files were wrong in opposite directions: **Helja is DEAD** (how and when is NOT established — do not invent it); **Dagna is ALIVE, in Drezen since Ch 23.** Drezen was the family's home.

*Open threads that must STAY open — do not explain, do not resolve off-screen:*
- `whisper-below-drezen.md` — NOT Chorussina's ritual. **Stopped in Ch 18 when the Banner went up — a coincidence in time, not a cause.** Source unknown. Nobody gets retroactive credit for stopping it.
- `joran-vhane-lost-healing.md` — four live causes (claw / ritual / crystal / Droskar); the GM left all four open. Do not pick one. *(Filename is `joran-vhane-lost-healing.md`; the front-matter `name:` inside still reads `jordan-`.)*
- `thane-unspoken-possession.md` — Thane has **never told anyone** he was possessed in Ch 18. Ch 19 walked him to the door and he could not open it. Must cost him something to say.
- `fane-of-irori.md` — Sister Lyra's charge to Nageru; its founders *"were waiting for something. Or perhaps someone."* **✔ FOUND in Ch 21, and the table made Nageru the answer: he is literally the Son of Irori, and the whole party heard it.** Still open: what it means for his parents, what "work" remains, what becomes of the fane.
- `nageru-went-for-the-atonement.md` — **⚠ Nageru's Ch 20 absence was Jesker's atonement, NOT the fane.** Do not credit that trip to the Irori quest. *(His POV drought ended with Ch 21.)*
*New in Session 23:*
- `caleth-parents-and-uncle.md` — **Caleth's parents were Aelariel (Spireborn elf) and Talia Aranor (human), both Riftwardens, both killed by Vang. Aelariel was Aravashnial's brother — ARAVASHNIAL IS CALETH'S UNCLE.** Only Caleth knows. Why the elf never told him, and what the Spiral means, stay open. **⚠ Ch 24: he showed the party the Spiral (not what it means), and Thane suspects there is more.**

- `the-drake-and-jerribeth.md` — Ch 20's three open items: **Jerribeth** (the party believes she is an elf and must keep believing it), the **drake that flew west**, and the **language Marhevok screamed that nobody knew**. Do not resolve any of them.

*Timeline:*
- `campaign-elapsed-time.md` — **about ONE year has passed since Armasse (as of Ch 21).** Never write "two years" for the party's time together; the whole Fifth Crusade lasts ~2 years.

*New in Session 21:*
- `mythic-tiers-personal-quests.md` — **party Level 10; tiers per character.** Nageru 4 (the fane), the rest 3. Personal quests grant tiers; don't invent the unstated ones.
- `aravashnial-taken.md` — **a six-legged flying dragon carried off Aravashnial and four soldiers** (Ch 21); Vang held him (Ch 22). **✔ Ch 24: he walked home and is asleep in Drezen's infirmary.** How he got out is OPEN.

*New in Session 20:*
- `grunhuld-wintersun-bone-spikes.md` — **the clan's bone spikes are WORN, not grown.** Only Marhevok grew them, and only raging. **Jestak was Grunhuld-Wintersun.** Korroc is now their clanliege.
- `caleth-chose-the-hammer.md` — Terendelev's charge inverted on Caleth in Ch 20 and he told nobody; he now carries the party's one true resurrection. **Radiance's working is *spell storing*.**

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
- Chapter 20: **Caleth** (*The Kind One / Three Attempts* — the Wintersun clan, the broken duel, Korroc inherits a tribe, and the charge Terendelev actually gave him)
- Chapter 21: **Nageru** (*What Was Lost / The Fane That Waited* — Fiendsplitter, the fane restored, "Son of Irori," Aravashnial taken)
- Chapter 22: **Caleth** (*The Shadow That Cast None / What the Water Showed* — the note in Aravashnial's study, the failed rescue, and the name of the man who killed his parents)
- Chapter 23: **Caleth** (*Children Are Not Equations / Runs in the Blood* — the locked journal, the letters in the cover, Aravashnial is his uncle; Dagna arrives; the tunnel and the dead prisoner; north toward the Khar-Zadûn graveyard)
- Chapter 24: **Thane** (*The Graves at Sesker's Gully / Two Humans Came Back* — the specter, the fathers' graves, Dagna's ruling, the Spiral shown, the Pauper's Thighbone, Aravashnial walks home)

POV remains a stakes decision, not a rotation — choose whoever has the most at stake in a given session.

**✔ NAGERU'S POV DROUGHT ENDED WITH Ch 21.** ✔ **AND HE HAS A CHARACTER SONG — `songs/character-nageru.md`, "The Thunder Wakes."** *(Older notes across this file, README.md and two memory files claimed he was the only PC without one. That was stale; corrected 2026-09-20. **All four PCs now have character songs.**)* *(Historical note, pre-Ch 21:)* **NAGERU IS SEVEN CHAPTERS OVERDUE — AND HE WAS ABSENT FROM SESSION 20 ENTIRELY** (player out; in fiction he went back to Drezen to see Jesker Helton's atonement performed, **not** to pursue the fane). His last POV was Ch 13. He is also the only PC without a character song. `memory/fane-of-irori.md` flags the Irori fane as his chapter — but note its own warning: **receiving a summons is not the same as answering it.** A POV chapter about getting a letter is a chapter about waiting. Spend him when they actually go.

### Secrets Matrix

Who knows what. The POV character can only narrate what they know — never let a POV character's interior reveal a secret they don't share.

| Secret | Who Knows | Who Doesn't |
|---|---|---|
| Caleth's Spireborn lineage | Caleth, Aravashnial | The party reads it as background, not as identity |
| Caleth's Riftwarden Orphan status / Seeker's Spiral on his shoulder | Caleth, Aravashnial. **⚠ Ch 24: Korroc, Thane and Nageru have SEEN the mark** and heard him call it *"the mark of the Seeker's Spiral… I have been told"* | **What it means, that it is a Riftwarden mark, and who told him** — still Caleth's alone. Anevia, Horgus, Klarah know nothing. |
| Aravashnial is **a Riftwarden** | **PUBLIC to the whole party as of Ch 11** (he closed the Abyssal rift and said so) | Public NPCs / the wider army |
| **Aravashnial's deeper layers:** his *elder* rank, his link to Caleth's parents' order, the Blackwing as Riftwarden stronghold, **and that Caleth knew since Ch 4** | Caleth, Aravashnial | Korroc, Thane, Nageru, everyone else |
| The fate of Caleth's biological parents | No one in the party knows | Caleth seeks it |
| Caleth's Terendelev recognition / dream | Caleth | The rest of the party |
| Thane + Anevia's Eagle Watch contract | Thane, Anevia, Caleth (Ch 3 reveal), Korroc (partial) | Nageru |
| Anevia + Irabeth are married | Party learned in Ch 4 (Anevia knew always) | Public NPCs |
| Nageru's Lawbringer / Sunken Fist origin | Mostly internal to Nageru | Party doesn't have the full shape |
| **Thane was possessed by Eustoyriax in Ch 18 — and was conscious inside it the whole time** | The party saw the possession; **NOBODY knows he was awake in there, because he has never said one word about it** | Everyone. He made himself unaskable on purpose, in about four seconds. |
| **Caleth's Ch 15 wound** (the succubus wore Iomedae's face and compelled him past his own correct judgment) | Happened in front of the party | **No one has ever spoken of it, including him.** Refrain: *"knowing wasn't enough."* |
| Nageru's charge from Sister Lyra (the lost fane of Irori) | Nageru; **the fane itself is now public** (Ch 21), since they were all in it | The party knows the temple was Irori's and that it welcomed Nageru. **The letter and Lyra's instructions are still his alone.** Thane never asked; his offered hands came anyway. |
| **Nageru is literally the Son of Irori** (Ch 21, GM-confirmed) | **The whole party heard the monk say it**, and got a strong hint of what he is | **Nobody has spoken of it**, including Nageru. What it means for his parents is unknown to everyone. |
| **Aravashnial is Caleth's UNCLE** (Ch 23); Caleth's parents were **Aelariel and Talia Aranor** | **Caleth only** (and Aravashnial) | Everyone. Nageru found the letters and does not know what they say. **⚠ Ch 24: Thane SUSPECTS** — he heard *"I have been told"* and saw Caleth's face at the sleeping elf's bedside (*"not a student's"*). He does not know what it is and has not asked. |
| **Caleth's Spiral dreams and visions** (Ch 23–24) — a shadowless man; Aravashnial behind an iron door; a waking *"Interesting"*; Vang with Caleth's shadow touching the mark | **Ch 24: the party saw him freeze and wake screaming, saw the mark, and heard *"Whatever took Aravashnial has been watching me"* / *"Vang is finding me through it."*** | **The content of the dreams.** Nobody knows of the first dream. |
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
- **Thorek** + **Helja** — Thane's father and mother. **Borin** + **Dagna** — Korroc's father and mother. All four are **Stonevein**. *(The Session 23 notes write "Boren"; source records are not edited.)*
- **Aelariel** + **Talia Aranor** — Caleth's father and mother (Ch 23). Aelariel has no second name. **Kenabres**, never "Kenebras" (the GM's prop certificate carries that AI typo).
- **Eustoyriax** — the shadow demon who held the true Sword of Valor and possessed Thane (Ch 18)
- **Aponavicius** — the marilith who held Drezen; it was her vanity that spared the Banner
- **Chorussina** — the tiefling conjurer below Drezen *(see the correction note above)*
- **Jesker Helton** — the Erastilian priest recovered from **Delamere's** tomb (Ch 19)
- **Sister Lyra** — of the Order of Irori, at the Sunken Fist; **Elara** + **Kaelen** are Nageru's parents (Ch 19 letters)
- **Rennick** — the young paladin of Iomedae who spotted the changed mark on Korroc's breastplate (Ch 18)
- **Marhevok Grunhuld-Wintersun** — the Kellid clanliege killed in Ch 20. The clan is the **Grunhuld-Wintersun** (hyphenated).
- **Beverach** — his successor as the clan's acting leader, appointed by Korroc. **NOT "Beverick"** — that is what Marhevok called him for years, wrongly, and the error is a character beat. *(The raw session notes use both; source records are not edited.)*
- **Jerribeth** — the "beautiful elf woman" who gave Marhevok a Baphomet scrying token. **⚠ The party must not learn what she actually is.**
- **Jestak** — the siege-captain spared in Ch 14. **⚠ Established in Ch 20 as Grunhuld-Wintersun.**
- **Kamilo Dann** — the quartermaster at **Vilareth Ford**; **Eagle Rock** is the escarpment west of it
- **Fiendsplitter** — the intelligent dwarven axe (Ch 21). **Korroc's since Ch 24** (Thane threw it to him).
- **Sesker's Gully** — the abandoned village on the Khar-Zadûn graveyard and waystation (Ch 24). The graveyard itself has no name of its own.
- **Arlys Harnaste** — the specter laid to rest in Ch 24; the **Harnaste** mausoleum. **Saint Argil** — whose thighbone is in the **Pauper's Thighbone** (Caleth's artifact, Ch 24).
- **Xanthir Vang** — **Xanthir**, not "Xanther" *(the Session 21 notes spell it Xanther; source records are not edited)*

### Party State at End of Chapter 24

*(Ch 24 is the last written chapter. `sessions/` has notes through session 24.)*

**⚠⚠ SESSION 24 IN BRIEF — read this first; it overrides Session 23 and everything below where they conflict:**
- **✔ THE STONEVEIN FATHERS ARE DEAD, AND THE THREAD IS CLOSED.** At **Sesker's Gully** (the abandoned village on the Khar-Zadûn graveyard and waystation), a laid-to-rest specter led the party to **five crude graves: THOREK and BORIN side by side**, three others unknown. **Borin died there of his wounds and Thorek buried him; Thorek went on, died somewhere unknown, and two unknown humans carried him back.** Dagna ruled they **stay there** among Khar-Zadûn's dead. The GM's note called it *"the end of this whole thread."* See `memory/the-fathers-are-buried.md`.
- **✔ ARAVASHNIAL IS HOME.** He walked in from the west for days, chased by **three construct spiders** (the party destroyed them); **Thane picked off the anti-magic collar** (Caleth has it); *"Been walking. For days."* He is **asleep in Drezen's infirmary** under Korroc's life-bond. **How he got out is OPEN.** Caleth still has told no one he is his uncle.
- **⚠ CALETH SHOWED THE PARTY THE SPIRAL** after a waking vision (*"Interesting"*) and a dream of Vang touching it. *"I have been told it is the mark of the Seeker's Spiral… it seems as if Vang is finding me through it."* **Not what it means; not who told him.** **Thane caught "I have been told" — and later Caleth's face at the bedside — and suspects more.**
- **✔ FIENDSPLITTER IS KORROC'S** (Thane threw it to him in the crypt). It talks in its wielder's head and calls demons at range.
- **New gear:** **Caleth — the Pauper's Thighbone** (an artifact; nine gold runes that feed spells and keep a ledger of the bearer's generosity), **the anti-magic collar**, a horn, arrows. **Korroc — a ring** (powers unestablished). **Thane — boots** (longer stride, long jumps) and arrows. See `lore/items.md`.
- **Vang's week ran out and nothing came.** Then Aravashnial walked home. *(This and Thorek's being among the dead the two humans brought back are prose-only, not in the notes — ✔ confirmed by Will 2026-10-04; the GM has read Ch 24.)*
- **Thane asked Sosiel to speak with his father** — *"highly unusual"*; not refused, not agreed. Open.
- **A gold light from the specter's chest wrapped Thane and "found nothing it was looking for."** Unexplained.

**⚠ SESSION 23 IN BRIEF — the Ch 22 state below still holds except where this or Session 24 overrides it:**
- **ARAVASHNIAL IS CALETH'S UNCLE.** His brother **Aelariel** (Spireborn elf, Riftwarden) and **Talia Aranor** (human, Riftwarden) were Caleth's parents; Caleth was born in **Kenabres**, 14 Sarenith 4689 AR (~25 now). Found in Aravashnial's **locked journal** (with Caleth's burned birth certificate) and **two letters sewn in his field journal's cover.** **Caleth has told no one.** He now **believes the Riftwarden Vang boasted of murdering in Ch 22 was his father.** See `memory/caleth-parents-and-uncle.md`.
- **VANG'S ULTIMATUM, by quasit:** abandon Drezen within the week or *"he will come and take more."* Korroc: *"Nope."* Irabeth is fortifying. **The party left on day four with ~three days left.**
- **Scrying Aravashnial now fails every time** — once violently denied. **Caleth's Spiral burns in dreams** of a shadowless man and of Aravashnial behind an iron door; he believes Aravashnial is reaching for him. Nobody has seen the mark.
- **DAGNA STONEVEIN IS IN DREZEN**, working as a stonemason. **Thane told her about the fathers in person** — the unwritten-letter thread is closed.
- **The escape tunnel is open; none of the bones are dwarven.** Via Sosiel's speak-with-dead: the fathers made the escape work; **the dead man does not know if they got out**; **Borin was injured**; they aimed for **a crypt with supplies, north up the riverbed** — Dagna: **the Khar-Zadûn graveyard and waystation, a day north and a little west.**
- **✔ WHERE THEY ARE AT THE CLOSE OF Ch 23: camped several hours north of Drezen along the dry riverbed, the four of them alone**, riding for the waystation. Thane: *"I need a horse."*
- **A rift-drake raid** (five drakes, lance-riding cultists) hit the excavation as a target of opportunity; Thane was carried off and got back. **Thane's scale was used (levitation; 3/day).**

**Advancement:** All four PCs are **Knights of the Fifth Crusade** and mythic. **Level 10 Gestalt, and ✔ ALL FOUR ARE MYTHIC TIER 4 as of Session 22.** Nageru reached 4 in Session 21 for the fane; **Caleth's came in Session 22 for killing the Woundworm** (⚠ *not* for rescuing Aravashnial — that failed), and the GM brought **Korroc and Thane** up with him to level the party. ⚠ **Tiers are still granted PER CHARACTER by personal quest** — Thane's and Korroc's remain unstated — so do not assume they stay matched, and check before recording any future change. See `memory/mythic-tiers-personal-quests.md`.

**Where they are and what they're doing:**
- **DREZEN IS TAKEN.** The citadel is held, the **Sword of Valor is RECOVERED (Ch 18)** and flies over it. **The objective of Book 2 is complete.**
- **The Queen's new mandate (Ch 19):** use Drezen as a base of operations and **explore the Wounded Lands to the south and west** for anything usable against the demons. Consult Sosiel, Aron, Irabeth on the region's history and legends. Reinforcements came north with the letter.
- **✔ The party is in Drezen at the close of Ch 24**, the evening Aravashnial came home; Korroc at his bedside, Caleth on the floor beside it, Thane on the step outside.
- ~~**⚠ ARAVASHNIAL IS TAKEN, AND Ch 22 WENT AFTER HIM AND FAILED.**~~ *(Historical — he is home as of Ch 24.)* The dragon was a **Woundworm named Scorizscar** — six legs, red, acid breath — **sent by Jerribeth**, and **Nageru killed it.** The party teleported into a cavern near the **Molten Scar**, **recovered all four soldiers alive**, wounded Jerribeth badly and lost her to a contingency spell — and **a templar teleported Aravashnial out mid-fight while Caleth was pinned to the ceiling watching.**
- ~~**⚠⚠ XANTHIR VANG HAS HIM.**~~ *(Ch 22 state; superseded by Ch 24.)* Established by a second scrying: an iron cage too small to stand in, a beaten face, a **black collar with a green crystal and needles**, and a **worm that walks** with no footsteps. **The scrying was SEVERED.** ⚠ **For lore he is alive; the party knows only that he *was*.** Vang has also **noticed Caleth.** See `memory/aravashnial-taken.md` and `memory/xanthir-vang-and-the-note.md`.
- **⚠⚠ VANG KILLED CALETH'S PARENTS**, and Aravashnial wrote it down for him on a page he never handed over — **quoting the Lantern Seer's third vision verbatim, which Caleth has never told a living soul.** ⚠ **How the elf knew it is unexplained. Do not resolve.** **Caleth has told nobody about the note.**
- **⚠ AN ABYSSAL RIFT** was burning at the far end of that cavern at midday and was **gone by evening.** Nobody investigated. ⚠ *Do not resolve.* See `memory/the-rift-at-the-molten-scar.md`.
- **✔ THE FANE OF IRORI IS FOUND AND RESTORED (Ch 21)**, thirty miles west, and **Nageru is the Son of Irori.** See `memory/fane-of-irori.md`.
- **A shared vision (Ch 21):** all four saw Delamere's crystal coffin melting away, at the same instant, in Drezen. Unexplained.
- **⚠ KORROC IS CLANLIEGE OF THE GRUNHULD-WINTERSUN (Ch 20)** — a Kellid clan of about four dozen, won by killing **Marhevok Grunhuld-Wintersun** in a challenge the man broke, and **resettled at Vilareth Ford**, where they doubled the size of the camp. **Beverach** leads them in his absence. Korroc promised them that **when the war ends they go wherever they want.** Irabeth: *"It won't be a problem unless it becomes a problem."*
- **The raids on Vilareth Ford have stopped.** That was Korroc's first order as their liege.

**The Stonevein arc — ✔ CLOSED in Ch 24 (the fathers are dead and buried at Sesker's Gully; see above).** The record below is kept; read it as history:
- **⚠ THE FATHERS SURVIVED (Ch 19).** Thorek and Borin were **captured, not killed**; **Staunton Vhane arranged the ambush**; they were put to work on the citadel they had helped build, dug **twenty feet** to a pre-fall water tunnel over better than a year, and escaped into the dry riverbed east of Drezen. **Neither is on the list of the dead. Neither was recorded as recaptured.** ~~WHERE THEY WENT IS OPEN~~ **✔ Ch 24: Sesker's Gully, and both are dead.**
- **The riverbed east of the walls is now a standing location with a claim on the party.** Aravashnial had the eastern bridge repairs moved up the list for exactly one reason: *"if you intend to find out where your fathers went, this is where their trail begins."* Aron's engineers open that ground over the following month.
- **Helja Stonevein is DEAD** (Thane's mother — *how and when is NOT established; do not invent it*). **Dagna Stonevein is ALIVE and, as of Ch 23, IN DREZEN** (she wrote to both cousins in Ch 19; she intended to come south after seventy-five years, and did). **Drezen was the family's home** — Dagna and Helja knew its streets first; the four met and became a family there.
- **Thane's banked flame has changed shape a third time.** Not vengeance, not the wrong record — *his father was a nuisance in a ledger for a year and dug his way out*, and Thane's private, unshared conclusion is ***"I could not have done that."*** Do not let him make peace with it quickly.
- **⚠ And a fourth (Ch 24).** The answer came — *"there was nothing behind it but a dwarf"* — and what he carries now is **the two strangers who brought his father back**, for life, and the question he will never ask in front of a priest: ***"Did you know we were looking?"*** Not a quest; the GM closed the thread.
- ~~Thane means to write to Dagna about the fathers and has not yet.~~ **✔ Closed Ch 23: he told her in person.** Korroc owns the grief; Thane owns the investigation. Keep that split.
- **Staunton arranged the ambush and Staunton is dead** — killed in Ch 16 over Thane's explicit objection after he asked for the man alive (*"Three days,"* was his estimate). **That disagreement is now permanently unresolvable and neither cousin has spoken of it. Live thread.**

**Per character:**
- **Korroc** now carries **boots of speed** (found in Drezen's stores) and can **widen the life-bond to take half** of a companion's wounds. He wears **the Armor of the Pious** — *not* "the Armor of Iomedae" any more. It is old craft that **takes the mark of whoever is inside it**, and in Ch 18 the sunburst became **Torag's hammer and anvil** with no ghost of the old mark underneath. The "something I should know" was **smith-lore, not a hidden past.** From Ch 18 he wears **Torag on shield and chest alike** — the two-gods reading is over. *(Whose suit it was, who made it, and how it reached a demon's treasury are all still open.)* He is modifying it at the Purity Forge; **what he is adding is not established — needs the GM.**
- **⚠ Korroc now carries FIENDSPLITTER (Ch 24)** — an intelligent dwarven battleaxe bearing Torag's mark that talks in many voices **inside its wielder's head**, senses demons at range, and wants their blood. Its other powers are not established. His warhammer remains his weapon of record. Also **a ring** from the Harnaste chest (powers unestablished).
- **Thane** carried Fiendsplitter from Ch 21 until **he threw it to Korroc in Ch 24**; he is no axe-man. He now wears **boots** from the Harnaste chest (longer stride, long jumps — no game names in prose). He carries **his mother's blade, his father's knife, and a punch dagger he made himself** at the Purity Forge. The blade he wipes after every kill **is a dead woman's knife, and has been for some time.** He was **possessed by Eustoyriax in Ch 18** and has told no one he was awake inside it.
- **Caleth** carries **Radiance**, whose second working — laid in at the Purity Forge, Thane cutting the channels, Aravashnial seating it after Caleth's own casting failed three times — **✔ is *spell storing*, established in Ch 20.** *(Table ruling: Radiance is not normally alterable; it took because the work was done on the Purity Forge.)* **⚠ HE FINALLY SPENT ONE IN Ch 22 — INTO JERRIBETH, INVERTED TO COLD, AND IT DID NOTHING AT ALL.** *Cold is not the road.* Do not write him as still holding it. **✔ Radiance also has GREATER DEMON BANE (established Ch 22)** — with a smite it identifies demons on contact. He still carries the Ch 15 wound (*"knowing wasn't enough"*), unspoken by anyone. The Drezen blueprints still ride folded in his spellbook — and **the party's one true resurrection potion now rides against them**, in his innermost coat pocket, over his heart.
- **⚠ Caleth now also carries the PAUPER'S THIGHBONE (Ch 24)** — an artifact; nine gold runes feed his spells and come back at dawn, and **a rune goes dark forever if he deliberately passes up a generous act.** Whether any has gone dark is not established. And **the anti-magic collar** off Aravashnial's neck: *"We'll keep that. For later."*
- **⚠ CALETH'S PRIVATE Ch 20 REALIZATION, TOLD TO NOBODY:** Terendelev's *"be the kind one — even when the others choose the hammer"* was about **him**. In Session 20 he was the one who chose the hammer, and Korroc was the kind one. **Never says it aloud; nobody else may name it.**
- **The *"we should talk later"* conversation FINALLY HAPPENED (Interlude 2) — and settled nothing.** Aravashnial interrogated the recharging mechanism and Caleth answered *"I don't know"* to nearly all of it; a second attempt in one day produces nothing at all. The elf proposed a testing programme and **Caleth fled up a staircase to escape it.**
- **⚠ Nageru found the fane in Ch 21 and was named Son of Irori (literal).** The party heard it; nobody has spoken of it. He received robes of his order. **Open:** what it means for Elara and Kaelen, what work remains, what becomes of the fane. *(Earlier state follows.)* He received two letters in Ch 19 — one from his parents **Elara and Kaelen**, one from **Sister Lyra** charging him to find **a lost fane of Irori** near Drezen. **⚠ HE WAS ABSENT FOR SESSION 20 AND IT WAS NOT THE FANE** — he went back to Drezen to see **Jesker Helton's atonement performed**, because *"a patient is a thing that waits."* **The fane remains entirely untouched; do not credit that trip to it.** Lyra's line ***"There is always another step"*** has escaped into the story: he said it aloud on the night march, **Thane overheard and it landed hard, and Nageru does not know that.**

**NPCs and prisoners:**
- **STAUNTON VHANE IS DEAD** (Ch 16). **NURAH DENDIWHAR IS DEAD (Ch 18)** — she got out of her irons, began a teleport, **Aravashnial reversed it**, she was called on to surrender, chose to fight, and was killed. **She never reached the Queen.** Reported by Irabeth, not witnessed by the party. Thane: *"She made her choice."*
- **Joran Vhane** is **in custody in Drezen, working the Purity Forge under guard.** He **can no longer cast healing magic (Ch 17)** — four live causes, **do not pick one.** Korroc changed tactics after watching his own armor decide what it belonged to: *"I can't hammer a man into a shape."* He handed him a hammer instead. **He is not being redeemed by argument; he is being left alone next to an anvil.**
- **Jesker Helton** — **✔ ATONED (Ch 20) and GONE.** **Sosiel Vaenic** performed the rite over most of a morning with **Nageru witnessing**; Jesker is clean, knows it, and is explicit that it settles nothing (*"a god forgives you in a morning"*). He has left for his home temple to **atone through deeds** and intends to come back, leaving someone to finish cleaning the Drezen shrine. He gave the party a **magic bow, arrows, and the symbols of Erastil.** His parting line — ***"Absolution's a beginning. A man can be forgiven and still owe"*** — was said in front of Thane, **who went still and said nothing.** *(His mother's lost wedding ring is still unfound and unexplained.)*
- **⚠ JERRIBETH HAS NOW BEEN MET (Ch 22), AND SHE IS PROVABLY A DEMON.** Caleth's smite fired and Radiance's demon bane bit; **he said so out loud** and Thane answered *"Of course she is."* She had the prisoners, took Aravashnial off his spellbook notation, left the soldiers for the dragon, fought, and **escaped wounded on a contingency.** ⚠ **The party's conclusion is SUCCUBUS and must stay succubus** *(GM secret, unchanged and off the page: glabrezu)*. **Her blood is on Radiance and a scrying with it still failed.** — Also from Ch 20: **Beverach** (acting leader of the Wintersuns at the Ford) and **Kamilo Dann** (feeding a doubled camp).
- **Queen Galfrey** is not at Drezen; her mandate arrived by letter. Irabeth, Anevia, Aron, Sosiel, Horgus and Klarah are with the company. **Aravashnial was taken (Ch 21) and walked home (Ch 24); he is asleep in the infirmary and has said four words.** **Dagna** is in Drezen working the stone.
- **NEW (Ch 21):** a **tattooed woman** who led the western temple, **escaped by contingency spell** with her winged bull-dragon (fate unknown); an **unnamed ancient monk** of the fane; the **six-legged dragon**. Jerribeth has posted a **1,000-platinum bounty on Arueshalae** (unnamed in the document; the party is sure), and **the party now suspects Jerribeth is a succubus** (suspicion only; the GM secret, that she is a glabrezu, stays off the page).

**New from Session 24, closed to invention:** **how Aravashnial got out**, where he walked from, and what was done to him · **who made or sent the construct spiders** · **who the two humans were** who brought Thorek back, and **where and how Thorek died** · **the other three graves' names** · **whether Sosiel will speak with Thorek** · **the gold light in the specter's chest** · **the ring's and the horn's powers** · **whether any Thighbone rune has gone dark, and where the babau got it** · **whether Vang really is "finding" Caleth through the Spiral** · **what Thane suspects about Caleth and Aravashnial.**

**✔ Closed by Session 24:** **where the fathers went** (Sesker's Gully; both dead) · **whether they got out, and how badly Borin was hurt** (out; badly enough to die of it) · **where Aravashnial is** (home) · **what Vang did when the week ran out** (nothing, yet).

**New from Session 23, closed to invention:** **why Aravashnial never told Caleth** · **whether he came home when Aelariel begged him to** · **what the Riftwardens' records and stories say about the Spiral** · **what the dreams are** · **what is denying the scrying** · **who burned the birth certificate** · **whether the fathers got out, and how badly Borin was hurt** · **what Vang does when the week runs out.** ⚠ **Flagged for Will:** `lore/factions.md` calls the Mordant Spire half-elven, but Aelariel is a Spireborn *elf*.

**⚠ Threads deliberately left open — do NOT close any of these without the table:**
the whisper below Drezen (stopped, unexplained, no retroactive credit) · ~~where the fathers went~~ *(closed Ch 24)* · how Helja died · Joran's lost healing · whose armor Korroc is wearing · the lost fane of Irori and what its founders were waiting for · four loose vials from Ch 19 · Thane's silence about the possession.

**New from Session 20, and equally closed to invention:**
**who Jerribeth really is** (the party must go on believing she is an elf) · **who sent the drake and where it flew** · **what language Marhevok screamed** (not Hallit, not Common, **not Abyssal** — his own clan did not know it either) · **what is in Aravashnial's sealed chest and who sent it** · **what became of Jestak**, now known to have been Grunhuld-Wintersun · **the shape that crossed the moon** on the night road · **Jesker's mother's wedding ring.**

**New from Session 21, and equally closed to invention:**
**what "Son of Irori" means for Elara and Kaelen** · **what work remains and what the fane's monks wait for** · **the tattooed woman's fate** · **Fiendsplitter's powers and history** · **the shared vision of Delamere's coffin melting** · **what the moon shape is** (now seen by all four) · **Aravashnial's chest and safe house, left behind.** *("Whether Aravashnial is alive" and "what the dragon is" were answered in Session 22 — see below.)*

**New from Session 22, and equally closed to invention:**
**where Aravashnial is now** · **who the templar was that took him** (nobody got his face) · **what the green-crystal collar does** — do not connect it to the Nahyndrian crystals · **how Aravashnial knew the Lantern Seer's third vision** · **who the murdered Riftwarden was and what he was to Aravashnial** (GM-confirmed family; the relationship is NOT stated) · **what happened to the Abyssal rift at the Molten Scar** · **where Jerribeth went** · **why her blood on the blade still could not find her** · **where the Ivory Sanctum is.**

**✔ Closed by Session 22:** **the dragon is a Woundworm named Scorizscar, and it is dead** · **Jerribeth sent it** · **all four soldiers survived** · **Jerribeth is confirmed a demon** (succubus to the party) · **Aravashnial is alive** — ⚠ *lore only; the party does not know it* · **the Lantern Seer's third vision is Xanthir Vang, not Staunton Vhane** · **Radiance has greater demon bane** · **Caleth's stored spell is spent.**

**✔ Closed by Session 21:** **the lost fane of Irori is found and restored** · **what its founders were waiting for: Nageru, the Son of Irori** · **Korroc was right about the shape across the moon.**

**✔ Closed by Session 20** *(recorded so nobody re-opens them by accident)*: Radiance's second working is **spell storing** · Jesker Helton's atonement was **performed** · the Wintersun bone spikes are **worn, not grown** — only Marhevok grew them, and only raging.

## Workflow Patterns

### Per-Session Chapter Writing Process

1. **Read** the new session notes in `sessions/`
2. **Decide POV** based on stakes (or use the one the user specified)
3. **Read** the previous chapter for voice continuity
4. **Read** the POV character's file in `characters/`
5. **Skim** relevant lore (factions, items, places mentioned in the session)
6. **Check** `memory/MEMORY.md` for secrets, open questions, and any "previous-Claude fabrication" warnings
7. **⚠⚠ SURFACE THE INTERPRETIVE CALLS — BEFORE WRITING A WORD.** Go back through the session notes and list every place the prose will have to **commit to something the notes do not state**, then put them to the author in one batch. **This step was added after Ch 22, where six preventable errors were caught one at a time in a finished draft.** Ask about: anything identified by appearance rather than name (a colored light, a shape, a sound); **who moved and who stayed** (teleports and "the group went" are chronically ambiguous); what a *repeated* action was aimed at; any number the prose must state; **any proper noun the prose wants and the notes lack — do not invent one**; and anyone's status, plus who in the party believes which. ⚠ **A batch of questions before drafting is cheap and welcome. A batch of corrections after drafting is expensive.** See `memory/chapter-drafting-pitfalls.md`.
8. **Write the chapter yourself**, in one sustained pass, with all of the above in context
9. **⚠ GREP THE DRAFT BEFORE HANDING IT OVER.** Six checks, all cheap:
   - `(two|three|several) years` — see `memory/campaign-elapsed-time.md`
   - British spellings — `\bgrey|colour|armour|honour|defence|centre|travell|recognis|realis`
   - **Name spellings** against the list above
   - **⚠ Character-trait violations.** For every character with real page time, open their file and grep their hard rules. Current cast: `old (man|elf)|elderly` (Aravashnial is **not** old), `Torag` near Thane (his god is **Alseta**), `golden` near Nageru's skin (**bronze**).
   - **⚠ Invented proper nouns.** Grep capitalized place/person names; confirm each against `characters/`, `lore/` or the session notes. Anything unmatched is invented — cut it or ask.
   - **⚠ Finality language about open-thread characters.** `dead|died|corpse|body|grave|mourn|grief` near anyone **missing** rather than confirmed dead — currently **Jerribeth**, and anyone else the story leaves missing. *(Aravashnial came home in Ch 24 and is alive; the Stonevein fathers are confirmed dead as of Ch 24 — write them as dead.)*
10. **Save** the result as `chapters/NN-short-title.md` (chapter number matches session number; **interludes take the previous chapter's number plus `.5`** — see `08.5-` and `18.5-`)
11. **Canon-update pass:** update character files (Established Moments + Current State), lore files, npcs.md as needed
12. **Web-update pass:** update `games/src/app/wrath/page.tsx` Campaign Arc Status section + write `website/updateN.md`
13. **Song:** write `songs/sessionN.md`
14. ~~**Image prompt:** write `images/sessionN.md`~~ — **⚠ DEPRECATED (2026-09-06). Do not do this.** Image prompts are no longer kept in the repo. Do not write one as part of a session pass and do not offer it at the end of one; write one only if the author explicitly asks. See `memory/image-prompts-deprecated.md`.

**The user often wants steps 10-14 spread across multiple turns, not done all at once.** Check before bundling.

**Never skip step 11 (the canon pass) to get to the next chapter.** The canon files are the only durable record of what the prose established; a chapter written against stale character files loses the previous session's gains. (Sessions 14–15 were written and the canon pass was lost in a disk failure — it had to be reconstructed from the chapter prose.)

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
- **About a year has passed, not two** (2026-09-13). Nine "two years" references to the party's elapsed time were fixed across Chs 13, 18.5, 19, 20 and 21, `caleth.md`, `thane.md` and a memory file. See `memory/campaign-elapsed-time.md`.

## The Jobs (all done by the one agent)

These are phases of work, **not** sub-agents to delegate to. Same agent, same context, one after another.

- **Chapter.** Session notes + POV decision + style guide + previous chapter for voice + relevant canon → the full chapter in one sustained pass. **Do not split a chapter across passes or agents — voice fractures.**
- **Song.** A Suno song for the session, or for a character. **THE ONE HARD LIMIT IS THE STYLE BOX: ~1,000 characters MAX, spaces included — Suno rejects anything over (tested: 1,054 was over).** The **lyrics box is NOT capped at 1,000** — that old rule was wrong. Suno accepts full-length lyrics (3,000+ chars confirmed in testing), so write the song to its proper length and do not truncate. Keep section tags short and put instrumentation/voice/tempo in the style box — but a *short* performance cue inside a tag (e.g. `[Verse - double time]`) is fine when it's needed to force a specific delivery. Single-register beats a four-stage build (Suno can't handle genre transitions). **No hard runtime cap** — let the song run its natural length; only ask for "no instrumental padding" if you actually want it tight. See `style-guide.md` → "Song Writing Rules (Suno)".
- ~~**Image prompt.**~~ **⚠ DEPRECATED — not part of the pipeline any more (2026-09-06).** `images/` stopped at session 6 and the practice was formally dropped after session 20. **Do not write one unless asked.** If asked, the old format in `images/session3.md` and `images/session4.md` still applies. The four existing files stay where they are as a record. See `memory/image-prompts-deprecated.md`.
- **Web update.** Update the `wrath/page.tsx` Campaign Arc Status section + write `website/updateN.md`. Follow `memory/webpage-session-section.md`.
- **Canon pass.** Update affected character files, lore files, and `npcs.md`. Targeted edits; no creative prose.
- **Continuity check.** Verify the finished chapter against the canon files; flag contradictions to the user.

## What NOT to Do

- **Do NOT hand creative work to a sub-agent.** One agent — you — does the reading, the deciding, and the writing. See *Model Architecture Rule*.
- **Do NOT invent canon.** If a session note is unclear, ASK the user; do not fill gaps with plausible invention. ⚠ **The hard part is noticing a note IS unclear** — in Ch 22 three notes read as facts while drafting and only became questions when the author pushed back. **Run step 7 before writing.** See `memory/chapter-drafting-pitfalls.md`.
- **⚠ Do NOT invent proper nouns.** No place names, titles, ranks or surnames that are not in `characters/`, `lore/` or the session notes. A *vague* detail is safe; a *specific and wrong* one gets quoted back as canon later. Write around it or ask. *(Ch 22 invented "Ramson's Ford" for one clause.)*
- **⚠ Do NOT write finality the POV character has no grounds for.** Narration must not bury someone the story has not buried. *(As of Ch 24 Aravashnial is home and alive, and the Stonevein fathers are dead and buried — the rule now guards Jerribeth and whoever goes missing next.)* *(Ch 22 wrote "a dead man's office" about a man the chapter was actively trying to rescue.)*
- **⚠ Do NOT call Aravashnial old.** He is an elf, long-lived but **not elderly**, and would be insulted. `characters/npcs.md` has said so in bold for months and the Ch 22 draft did it fourteen times anyway. **Reading a canon file is not the same as checking the draft against it.**
- **Do NOT let in-scene durations go unchecked.** Sanity-test any stated time against what the table actually did. *(Ch 22 gave the party eleven minutes to cast buffs; it is a round or two.)*
- **Do NOT reveal secrets through narration.** The POV character can only narrate what they know.
- **Do NOT update the live web page's Campaign Arc Status section by appending.** Always REPLACE the content; the section is a current-state window, not an archive.
- **Do NOT skip writing the matching `website/updateN.md`** when the page is updated.
- **Do NOT batch chapter writing + canon updates without checking with the user** — they often want these in separate turns.
- **Do NOT write British spellings.** This project is **American English** — `gray`, never `grey`, plus *color / armor / honor / recognize / defense / traveling*. It applies to chapters, canon files, songs, image prompts and website changelogs alike. **Ch 19 onward is clean; Chapters 1–18.5 and older canon files were deliberately left alone (~90 instances) — do not sweep them without asking.** See `style-guide.md`.
- **Do NOT write "two years" (or longer) for the party's time together.** About **one year** has passed since Armasse as of Ch 21, and the entire Fifth Crusade lasts roughly two years. Say "a year," "almost a year," or leave it unquantified. Pre-campaign backstory and outside timelines (e.g. when Maranse Delaskru vanished) are exempt. Grep any new chapter for `(two|three|several) years` before handing it over. See `memory/campaign-elapsed-time.md`.
- **Do NOT trust character names from your own memory alone.** Especially Klarah, Aravashnial, Khar-Zadûn. Always verify against the character file before writing.
- **Do NOT delete or rewrite chapter prose without the user's explicit approval.** Chapters are published; treat them as canon.
- **Do NOT use Korroc, Thane, or Nageru's POV to narrate Caleth's Riftwarden origin or the Caleth–Aravashnial connection.** Aravashnial being *a Riftwarden* is party-public as of Ch 11 — but his elder rank, the order's link to Caleth's parents, and the fact that Caleth knew since Ch 4 remain private to Caleth (and Aravashnial).
