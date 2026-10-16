# Research library — Mystery Coast: Ghosted

Every doc here is sourced research with URLs, wired into the production
pipeline or explicitly excluded with a written reason. No orphaned research.
Owner law: RESEARCH-TO-REPO — all research lives in the appropriate repos'
docs, never local-only.

## Contents

| Doc | What |
|---|---|
| CAPE-JONES-TRANSFER.md | What transfers from the Cape Jones research library and what does not, with reasons |
| HB-LIMITED-ANIMATION.md | Hanna-Barbera limited-animation technique: how HB made cartoons cheap and fast |
| SCOOBY-DOO-1969-PIPELINE.md | Scooby-Doo, Where Are You! (1969) production pipeline: roles, formula, numbers |
| SGC2C-PRODUCTION.md | Space Ghost Coast to Coast: how the talk-show/improv format was actually made |
| ATHF-PRODUCTION.md | Aqua Teen Hunger Force: Photoshop/AE/FCP pipeline, Radical Axis, improv voice sessions |
| TOOLING-2026.md | Open-source 2D animation tooling verified for 2026: rigging, inbetweening, lip sync, scratch TTS, music/SFX libraries |
| PIPELINE.md | The recommended minimal pipeline for this show, synthesized from all of the above |
| BIBLE-PROPOSALS.md | Clearly-marked proposals for SHOW-BIBLE.md gaps (proposals only — the bible is owner canon, not rewritten) |

## Wire-up log

Every finding is either pulled in and wired up, or excluded with an honest
reason. A finding without a pull-in is incomplete work.

| Finding | Wired up as | Or excluded because |
|---|---|---|
| OpenFaceFX lip-sync cue sheets (MIT, Tahoma2D-ready) | TOOLING-2026.md; PIPELINE.md stage 6; ANIMATION-REFERENCE.md citation | |
| Vector-based inbetweening (strokes, not pixels) | PIPELINE.md stage 5/7; ANIMATION-REFERENCE.md citation | |
| RIFE ghosting warning on flat cartoon colors | PIPELINE.md restraint rule (stage 7); ANIMATION-REFERENCE.md | |
| Scratch TTS (Piper, Dia, Kokoro) for animatics | TOOLING-2026.md; PIPELINE.md stage 1 | |
| Stock-library music model (HB method) | PIPELINE.md stage 10 | |
| Music/SFX gen tools (ACE-Step, Stable Audio, Demucs, Freesound) | TOOLING-2026.md; PIPELINE.md stage 10 | |
| Automate-the-wait principle | PIPELINE.md stage 11 | |
| Pre-pro chain (Trelby/fountain to animatic, Kdenlive) | PIPELINE.md stages 0-3 | |
| 12-stage pipeline stage order + finish/QC pattern | Adapted into PIPELINE.md | |
| HB limited-animation techniques (2s/3s, level separation, design-for-reuse, metronome timing, cycles) | HB-LIMITED-ANIMATION.md; PIPELINE.md stages 4-5 | |
| Scooby 6-beat mystery formula | SCOOBY-DOO-1969-PIPELINE.md; PIPELINE.md stage 0 | |
| SGC2C recontextualization edit, stock library, one-bar greenlight | SGC2C-PRODUCTION.md; PIPELINE.md comedy rules | |
| ATHF audio-first cycle, improv sessions, cold opens, decoy premise | ATHF-PRODUCTION.md; PIPELINE.md episode structure | |
| Tahoma2D as animation core, Rhubarb lip sync, Krita boards, Blender finish | TOOLING-2026.md; PIPELINE.md | |
| LatentSync / MuseTalk | | Excluded: talking-head video output, wrong for hand-drawn mouth charts |
| Blender Cycles render optimizations | | Excluded: 3D path-tracing, no 3D in this show |
| Kaggle GPU queue automation | | Excluded: 2D pipeline runs on CPU; revisit if heavy AI needed |
| AI video generation stack (Wan, LTX, Hunyuan, ToonComposer) | | Excluded: generative video fights the HB limited-animation look |
| 3D asset pipeline (Kenney/KayKit) | | Excluded: 2D show |
| Merch/community stack | | Excluded: show is in pre-production |
| Synfig as core, Pencil2D, Coqui XTTS, Bark, Papagayo-NG | | Excluded: see TOOLING-2026.md honest exclusions |
| SMEAR Blender add-on | | Excluded pending license verification |

## Technique citations for animators

Before animating, consult `mhvnsnt/animation-research-library` (see
`ANIMATION-REFERENCE.md` at repo root) and cite the technique in the PR.
Relevant entries in that repo's TECHNIQUES.md: "Limited animation",
"Smears & multiples", "Ones vs twos", "Comic timing".
