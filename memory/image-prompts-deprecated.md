---
name: image-prompts-deprecated
description: Image prompts are no longer part of the per-session pipeline. Do not write images/sessionN.md unless explicitly asked; the practice may be dead for good.
metadata:
  type: feedback
---

**Image prompts are no longer a required step.** Stated by Will on 2026-09-06: *"we're not putting prompts in the repo anymore. I'm not sure we will again."* Treat the step as **optional at best, and quite possibly deprecated permanently.**

**Why it existed, and why it stopped — this is the part that matters.** The step was never about keeping a record. Early on, **AI-written prompts reliably produced better images than hand-written ones**, so having Claude draft the prompt was worth a file in the repo. **That is no longer true.** Image generation has improved, and Will and the GM have gotten good at writing prompts that produce exactly what they want. The prompt now goes **straight into ChatGPT** and never becomes a file at all.

So the artifact is obsolete twice over: it is not needed as a *drafting aid*, and it was never wanted as a *record*. `images/` contains **four files — sessions 2, 3, 4 and 6** — and nothing since (last touched in the *"After week 8"* commit).

⚠ **There is no Session 20 image prompt, and there is not going to be one.** *(An earlier version of this file and of [[gm-is-a-repo-contributor]] claimed the GM had written one outside the repo. She had not. That was an assumption built from the phrase "image prompt already done by the GM" and never checked — the images side of a session is simply hers now and produces no repo artifact.)* **Do not go looking for a missing prompt file for any recent session, and do not tell the author one is waiting to be pulled.**

## How to apply

- ⚠ **Do not write `images/sessionN.md` as part of a per-session pass.** Not proactively, not "for completeness," and not because `CLAUDE.md`'s numbered pipeline still lists it.
- **Do not offer it at the end of a session pass** the way the song is offered. If the author wants one he will say so.
- If he *does* ask for one, write it — the old format in `images/session3.md` and `images/session4.md` still stands.
- **Do not delete the four existing files.** They are a record of what was done; they are simply not a pattern to continue.

**The song is different and is still live.** `songs/` is current and the author still asks for them per session. Do not let this deprecation bleed onto the song step. See [[gm-is-a-repo-contributor]] — the GM sometimes writes those herself, so check `songs/` and consider pulling before writing one.

**This is a workflow preference, not a canon fact** — and note what would have to change for it to reverse: the value was always *"does an AI draft beat what we'd write ourselves."* Today it does not. **Do not offer to resume image prompts on the theory that it is a missing step**; it is a solved problem, not an abandoned one. If the author revives them, update this file rather than treating the revival as a contradiction.
