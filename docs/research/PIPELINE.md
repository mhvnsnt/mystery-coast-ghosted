# Mystery Coast: Ghosted — production pipeline

The recommended minimal pipeline for this show, synthesized 2026-10-16
from the HB/Scooby/SGC2C/ATHF research, the Cape Jones transfer survey,
and the 2026 tooling research. Owner laws: proven open-source tools only;
automate the wait; no orphaned research.

## The shape of the pipeline

Dialogue-first, audio-first, like ATHF and like 1969 Scooby-Doo. Voices
are recorded before animation. Animation serves the performance. The
Xsheet is timed like it is 1969: twos and threes, held poses, no blanket
interpolation.

```
script (beat sheet)
  -> scratch dialogue (Dia/Piper) for timing
  -> ensemble voice record (final voices, improv pass)
  -> audio cut + animatic (Kdenlive)
  -> character rigs (Tahoma2D cutout skeletons, mouth-switch)
  -> animate on 2s/3s (Tahoma2D Xsheet)
  -> lip sync (Rhubarb/OpenFaceFX cue sheets)
  -> selective smoothing ONLY where marked (TheAnimeScripter/RIFE)
  -> backgrounds (Krita, parallax loops)
  -> composite + grade (Blender VSE/compositor)
  -> score from cue library + SFX (Audacity)
  -> encode + QC + deliver (ffmpeg)
```

## Stage by stage

### 0. Beat sheet (the formula is the engine)
Write to the 6-beat mystery formula (see SCOOBY-DOO-1969-PIPELINE.md):
arrive, monster problem, split up, fake haunting proven, trap backfires,
unmasking. Subvert beats deliberately for the lazy cast: the trap always
backfires, the reveal happens too early, nobody cares. A 3-5 person
writing core can generate a season if the formula carries structure.

### 1. Scratch dialogue and timing
Generate scratch scene dialogue with Dia (multi-speaker, one pass) or
Piper (single lines, instant CPU). Cut it to a click track at fixed BPM.
Lock walk cycles to exact frame counts per beat (the Hanna metronome
method). Scratch voices are for animatics ONLY. Final voices are human.

### 2. Ensemble voice record
Record the cast together in one room (or low-latency remote), ad-lib
encouraged. Do a dedicated improv pass after the scripted takes. The best
ad-libs get written into the series bible and canonized (the "Jinkies"
method). Hot-mic the host performer: record from the moment they enter
the booth, keep the unguarded material.

### 3. Audio cut + animatic
Cut the audio version first (ATHF method: editor works the audio cut for
a couple of weeks). Build the animatic in Kdenlive from boards (Krita)
timed to the final VO. Animation does not start until the animatic is
locked.

### 4. Character rigs (build once, reuse forever)
Tahoma2D cutout skeleton rigs for the cast. Characters designed FOR the
pipeline: separated head/body/limb levels, clean joint separation points,
seam-hiding accessories (the collar rule), simple mouth shape sets,
mouth-switch layers. Build the one-time stock library now: walk, run,
chase-panic, scared reaction, idle, talk poses. Per-episode animation then
drops to near zero (the SGC2C/Croker model).

### 5. Animate on the Xsheet
Animate on 2s and 3s (8-12 unique poses per second). Hold strong key
poses. Let the poses be funny in and of themselves (Takamoto). Compensate
with writing, voice acting, music cues, and SFX, not with more drawings.
Target roughly 1/7th the drawing volume of full animation (the HB ratio:
~2,000 drawings per 7 minutes instead of 14,000).

### 6. Lip sync
Rhubarb (bundled in Tahoma2D) or OpenFaceFX cue sheets driving
hand-drawn mouth charts on held poses. Lip sync to mouth shapes only, not
full facial animation.

### 7. Selective smoothing (restraint rule)
AI interpolation touches ONLY shots the timing charts explicitly mark:
walk-cycle in-betweens, slow-mo, camera pans. Never blanket-interpolate.
RIFE ghosts on flat cartoon colors (verified in Cape Jones testing). The
holds ARE the style.

### 8. Backgrounds
Krita-painted, HB-style. Build modular looping backgrounds for chase
sequences (the chase is the recycling slot). Parallax loops for runs.

### 9. Composite, grade, finish
Blender VSE for the edit, compositor for final grade. ffmpeg for encode
(x264 CRF 17 for proofs, per the repo's promo-kit standard). QC with
before/after frames on every visual change (repo ANIMATION LAWS).

### 10. Score and SFX from the cue library
Build the show's cue library ONCE: chase, sneak, scare-sting, reveal,
transition stings. Sources: compose/commission, Incompetech (CC BY),
FreePD (CC0), Pixabay Music, Freesound (CC0/CC-BY) for SFX. Music editors
re-edit ("Frankenstein") the cues per episode. Post-score only the
pilot/specials to picture. Keep a small reaction/sweetening SFX library
and use it sparingly (do not repeat the 1960s laugh-track mistake).

### 11. Automation rule
Every batch step loops to completion without manual kicks
(AUTOMATE-THE-WAIT). No chunk-advancing by hand. If a step needs a human
between runs, redesign the step.

## Episode structure (stolen from ATHF, adapted)

- Cold-open chaos unrelated to the plot (the Dr. Weird slot).
- The 6-beat mystery, solved mostly by accident while the cast bullshits
  around.
- Consequence-free reset: endings can kill, injure, or humiliate everyone.
  Next episode, everything is back. This lets a lazy cast stay lazy with
  no arc pressure.
- The decoy premise: the show sells "they solve mysteries" and abandons
  it on camera with an in-universe excuse.

## Comedy operating rules (stolen from SGC2C)

- One-bar greenlight: does it make the one decider laugh. That is the only
  note.
- Protect the straight-man asymmetry: one sincere party against the
  idiots. If everyone performs, it collapses.
- Two-person write/direct: one consistent comedic voice, no writer-room
  drift.
- The recontextualization edit: sincere or odd responses first, host
  questions built around them in post. Comedy assembled, not just written.

## What this pipeline explicitly rejects

- Blanket AI interpolation (destroys the HB look).
- Talking-head AI lip sync (wrong output for hand-drawn mouths).
- Generative video for character animation (fights the limited-animation
  style; Cape Jones tools for a different show).
- 3D rendering lanes (no 3D in this show).
- Laugh tracks (dated; SGC2C proved the format works without one).
- Comedy by committee (one decider, one bar).
