# Wrath of the Righteous — A Pathfinder Campaign Blog

## Project Overview

This is a long-running creative writing project that adapts our weekly Pathfinder RPG sessions into novel-style fantasy prose. Each chapter is published as a blog entry. Final length will be approximately 60 chapters covering the Wrath of the Righteous adventure path, from the fall of the Kenabres wardstone through the campaign's mythic conclusion.

The party plays Saturdays. The blog gets written between sessions.

## How to Write a New Chapter

When asked to write a new chapter, follow this order:

1. Read this README in full.
2. Read `style-guide.md` for prose rules.
3. Read the raw session notes from `sessions/` for the session being adapted.
4. Read the previous 1-2 chapters from `chapters/` for voice continuity, paying special attention to the POV character's prior chapters if any exist.
5. Skim relevant character files from `characters/` for the POV character and any whose history is directly relevant to this session's events.
6. Check `lore/timeline.md` for where we are in the larger arc and what's been established.
7. Check `lore/factions.md` and `lore/items.md` if the session involves Templars, Vescavor, the silver scales, Radiance, or any other established lore element.
8. Write the chapter as a new markdown file in `chapters/`, named `NN-short-title.md` where NN is the chapter number.

After writing, suggest 1-2 sentences for `lore/timeline.md` summarizing what was established.

## POV Method (The Abercrombie Method)

We use Joe Abercrombie's POV-by-stakes structure, not strict rotation.

POV is assigned to **whoever has the most at stake in a given session** — the character making the hardest call, whose history is most relevant to events, whose internal arc moves forward most. The chapter is written in deep third-person limited from inside that character, with prose colored by their interior voice.

If the user doesn't specify a POV character, recommend one based on the session notes and explain your reasoning before writing.

Approximate POV distribution over the full 60-session campaign:

- **Caleth:** 18-22 chapters (the secret-keeper, the moral-political center)
- **Korroc:** 14-18 chapters (the faith-anchor, the emotional spine)
- **Thane:** 12-16 chapters (the investigator, the Templar-hunter)
- **Nageru:** 10-14 chapters (rare by design — when we get inside his head, it matters)
- **Occasional NPC chapter:** 4-5 total across the campaign (Anevia, Irabeth, possibly an enemy POV at a major turning point)

Don't worry about hitting these numbers exactly. Let the story dictate.

## The Three Established Songs and Style Diptych/Triptych

Three character songs have been written so far, each capturing one character's interior register:

- **"When the Sky Fell on Kenabres"** — Korroc's anthem (power metal war-march)
- **"The Spireborn's Letter"** — Caleth's vigil (orchestral, builds to release)
- **"The Knife and the Name"** — Thane's blood-debt ballad (folk-orchestral)

Nageru's song is yet to be written. When his major POV chapter lands, it will be the natural moment.

## Style Influences

The prose blends:

- **Brandon Sanderson's** character interiority and worldbuilding density
- **Robert E. Howard's** visceral, rhythmic combat
- **Joe Abercrombie's** POV-by-stakes structure and grim humor
- **Patrick Rothfuss's** attention to prose rhythm and the sound of sentences

Specifics are in `style-guide.md`. Read it.

## The Mythic Inflection Point

Around session 10-15, the party will become Mythic — gaining legendary abilities and a scope-shift in the story. The prose register should **grow with the characters** at that point. Korroc's forge-metaphors become temple-metaphors. Caleth's observations gain cosmic edges. Thane's grudge becomes something closer to fate. Nageru's stillness becomes something the gods notice.

Don't change voices. Deepen them.

## Critical Continuity (Do Not Forget These)

These are non-negotiable established facts. Treat them as canon:

- **Anevia and Thane are PARTNERS** — both hired by the Eagle Watch on a contract investigating Templar infiltration. They are NOT romantically involved. They have a professional working relationship and genuine friendship.
- **Thane was HIRED BY the Eagle Watch**, not a member of it. He's an independent contractor.
- **Anevia** was also hired by the Eagle Watch — same contract, different angle (she works the soldiery and marketplaces; Thane works the gutters).
- **Caleth is Spireborn** (a half-elf trained at the Mordant Spire), a **Paladin of Shelyn**, and also a **Wizard**. He wears no armor and uses mage armor.
- **Caleth privately witnessed Terendelev's transformation** in the crowd at Armasse, and the dragon *recognized him* and smiled at him in the half-second before launching. He has not told the others. This is a Spireborn secret he is carrying.
- **Each surviving character carries one silver scale from Terendelev** with a single charge of a unique ability:
  - Korroc's scale: levitation
  - Caleth's scale: still unspent (he is holding it)
  - Thane's scale: levitation
  - Nageru's scale: a divine smite empowerment for one fight
- **Yaniel's sword "Radiance"** has been recovered from the cultists. Stolen from the Kenabres museum; rightful relic of the Fourth Crusade.
- **The S. V. letter** is in Thane's chain shirt, naming three Templar safe houses (Nyserian Manor, Topaz Solutions, Tower of Estrod) with passphrase ("I've new material for the archives") and naming Drezen as the Templar destination. This is plot-critical evidence.
- **Hosilla** is the Templar contact in Kenabres they killed. **S. V.** is her superior, not yet identified. **Vorlesh** is named in the letter as the one who "finished with the wardstone."
- **Chief Sull and Nathholm** are allies. The party promised to harry Vescavor where found and carry word to the surface.
- **Aravashniel** is a half-blind wizard saved with a restoration potion. He's an ally; his vision is partially restored.
- **Horgus Gwerm** is a noble; difficult, snobbish, occasionally redeemable. Saved at the chasm by Nageru.

## Tone Guidance

This is grim fantasy. Demons are real. Children die. Cities burn. The party has lost much and will lose more.

But it is not grimdark. There is faith. There is friendship. There is grim humor. Korroc complains about climbing. Thane and Caleth quip at each other. Nageru has dry one-liners. People love each other and say so, or say so by their actions.

The Worldwound is a horror, but the Mendevian Crusade is a real, meaningful resistance, and the party will become a meaningful part of why it survives.

## File Naming Conventions

- Chapter files: `chapters/NN-short-title.md` (e.g., `chapters/04-the-broken-gate.md`)
- Session notes: `sessions/session-NN-raw-notes.md`
- Always lowercase, hyphenated.
- Chapter numbers match session numbers.

## Output Expectations

When writing a chapter:

- Open with a chapter title styled as `# Chapter Title` with a subtitle line.
- Use horizontal rules (`---`) to separate major scenes within a chapter.
- End every chapter with `*[To be continued.]*` on its own line.
- Chapters should be substantial — typically 4,000-8,000 words depending on the session's content. Don't pad. Don't truncate either.
- If you reach an output limit, stop at a logical scene break and tell the user to say "continue." Never truncate mid-scene.

## When You're Done

After writing the chapter, briefly summarize:

1. The chapter file path you created.
2. 1-2 sentences for `lore/timeline.md`.
3. Any character file updates that would be worth making (e.g., "Thane now has the S. V. letter — worth adding to thane.md").
4. Any new lore elements that should be added to `lore/` files.

Then stop. The user will tell you what to update.