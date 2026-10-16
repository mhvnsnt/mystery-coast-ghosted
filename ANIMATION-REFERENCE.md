# Animation reference: use it before you animate

**Library:** [`mhvnsnt/animation-research-library`](https://github.com/mhvnsnt/animation-research-library) (private). It's legal-only:
- public-domain cartoons (Fleischer, Popeye, PD Looney Tunes) from the Internet Archive
- Blender Studio open-movie production files (CC-BY: boards, animatics, rigs, scenes)
- Pepper&Carrot source art
- technique breakdowns sorted by production stage: script → boards → animatic → model sheet → rig → scene → final

**How agents use it here**
1. Find the shot type (punch, take, walk, lip sync, cutout rig, smear) in the library's technique index. Read it and cite it in the PR.
2. Pull pieces from this repo's kits, mask-cut them (no rectangles), and check them on a checkerboard.
3. Edit the segment's existing `timeline.json` and layers in place, then render.
4. Ship before/after frames and the rendered clip. Done means a clip exists.

**Rules:** this repo's `AGENTS.md` → "ANIMATION LAWS", plus the money-machine-hq [instruction gate](https://github.com/mhvnsnt/money-machine-hq/blob/main/.github/pull_request_template.md) and [Laws 14 & 15](https://github.com/mhvnsnt/money-machine-hq/blob/main/docs/AGENTS.md).

**Worked example:** `https://github.com/mhvnsnt/TRIPPEDD-Production-studios-/tree/main/production/TRIPPEDD_EP01/goodville/segment-dino-story` (layered, mobile-editable, voice synced) and [GOODVILLE-POSTMORTEM.md](https://github.com/mhvnsnt/TRIPPEDD-Production-studios-/blob/main/production/TRIPPEDD_EP01/goodville/GOODVILLE-POSTMORTEM.md).

## Technique citations (added 2026-10-16)

Before animating, consult the matching technique below and cite it in the
PR (repo AGENTS.md, Animation Law 1).

From `mhvnsnt/animation-research-library` TECHNIQUES.md:
- "Limited animation" — reuse cycles, held bodies with only mouth and eyes
  moving, stylized poses. The core of this show's look.
- "Smears & multiples" — blur/stretch/multi-limb in-betweens for fast
  action. Use sparingly; the HB method holds poses instead.
- "Ones vs twos" — 12 drawings/sec on twos, ones only for fast action.
  This show animates on 2s and 3s (8-12 unique poses/sec).
- "Comic timing" — a hold, then a snap. Hard holds on poses, near-instant
  moves between them.

From this repo's `docs/research/`:
- `HB-LIMITED-ANIMATION.md` — the full HB method: level separation,
  design-for-reuse, metronome timing, stock music library.
- `PIPELINE.md` — the show's pipeline, including the restraint rule: AI
  interpolation touches ONLY shots the timing charts mark for smoothing.
  RIFE ghosts on flat cartoon colors; the holds ARE the style.
- `CAPE-JONES-TRANSFER.md` — OpenFaceFX/Rhubarb lip-sync cue sheets and
  the vector-inbetweening method.

No rectangular crops. Ever. (Unchanged.)
