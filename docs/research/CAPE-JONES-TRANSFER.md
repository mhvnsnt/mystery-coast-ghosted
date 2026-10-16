# Cape Jones research transfer survey

What transfers from the Cape Jones research library to Mystery Coast:
Ghosted, and what does not. Surveyed 2026-10-16 by reading the cape-jones
repo docs directly (the delegated survey worker failed twice with no
output, so this was done by hand from the source docs).

Owner rule: study technique, never copy assets. Everything below is
technique and tooling, not content.

## TRANSFERS — yes

### 1. OpenFaceFX lip-sync cue sheets (COMPLEMENTARY-STACK.md)
- What: audio + transcript to viseme animation curves. MIT, numpy-only,
  runs on CPU. Outputs directly to OpenToonz/Moho `.dat` (Preston-Blair
  mouth names), Rhubarb TSV/JSON, Papagayo `.pgo`. The `.dat` output drops
  straight into OpenToonz/Tahoma2D.
- Why it transfers: this is exactly the HB limited-animation dialogue
  method (mouth-switch on held poses). Already pulled into cape-jones
  (`tools/openfacefx/`).
- Wire-up: document in TOOLING-2026.md and PIPELINE.md as the lip-sync
  step; cite in ANIMATION-REFERENCE.md.

### 2. Vector-based inbetweening insight (PRO-INBETWEENING-RESEARCH.md)
- What: all professional auto-inbetweening works on vectors, not raster
  pixels. RIFE/ffmpeg minterpolate blend pixels and ghost on flat cartoon
  colors. OpenToonz/Tahoma2D vector inbetweening moves strokes, no
  ghosting.
- Why it transfers: directly applicable to 2D cutout/vector character
  animation. This is the correct inbetweening method for the show.
- Wire-up: PIPELINE.md inbetweening section; ANIMATION-REFERENCE.md
  citation.

### 3. RIFE ghosting warning (INTERPOLATION-RESEARCH.md)
- What: tested on hand-drawn line art, RIFE v4 produces
  semi-transparent ghosting on flat color regions because optical flow
  cannot lock onto textureless areas. Verified with own eyes on the Cape
  Jones flying scene.
- Why it transfers: as a WARNING. Do not blanket-interpolate limited
  animation. Use selectively (walk-cycle in-betweens, pans, slow-mo) or
  not at all.
- Wire-up: PIPELINE.md "restraint" rule; ANIMATION-REFERENCE.md.

### 4. Scratch TTS pipeline (TRACK-B-AUDIO-PULL.md)
- What: Piper TTS (MIT engine, fast CPU, consistent character voices),
  KittenTTS (Apache-2.0, tiny), espeak-ng (GPL-3.0, fallback). All
  license-checked and pulled into cape-jones `tools/`.
- Why it transfers: scratch dialogue for animatics and timing. Final
  voices stay human (owner rule), but scratch TTS is how you time a
  dialogue-first production.
- Wire-up: PIPELINE.md animatic stage; TOOLING-2026.md.

### 5. Stock-library music model (docs/soundtracks/SOUNDTRACKS.md)
- What: Cape Jones scores from reusable sources: a public-domain 1922
  film score (intro), a surf-rock track in the Scooby-Doo chase-scene
  tradition (outro/action), an AI-generated public-domain symphony piece.
  One library, re-edited per episode.
- Why it transfers: this IS the Hanna-Barbera music department method
  (see HB-LIMITED-ANIMATION.md: Ted Nichols cue libraries reused for
  decades). Same model, new library.
- Wire-up: PIPELINE.md score stage; build the show's own cue library.

### 6. Music/SFX generation tools (TRACK-B-AUDIO-PULL.md)
- What: ACE-Step (Apache-2.0, lyrics-to-song), Stable Audio Open (MIT
  code, text-to-music and SFX), Magenta (Apache-2.0, MIDI composition),
  MMAudio (video-to-SFX), Demucs (MIT, stem separation).
- Why it transfers: scoring and SFX for a cartoon. Stable Audio's SFX
  generation and the stock-library approach cover the HB sound-effects
  tradition.
- Wire-up: TOOLING-2026.md; PIPELINE.md score/SFX stage.

### 7. Automate-the-wait pattern (docs/AUTOMATION.md)
- What: the Pantera render needed manual chunk advancement; fixed with a
  "Run All" notebook that loops render-verify-zip per chunk with resume.
  Owner law: AUTOMATE-THE-WAIT.
- Why it transfers: as a PRINCIPLE, not the code. Any batch step in this
  show's pipeline (render, encode, upload) must loop to completion without
  manual kicks.
- Wire-up: PIPELINE.md automation rule.

### 8. Pre-production tooling pattern (TRACK-D-PULL.md)
- What: Trelby (screenwriting), fountain_to_beats.py /
  fountain_to_animatic.py (script to timing to animatic), Kdenlive (NLE
  pick), proxy_gen.py.
- Why it transfers: script-to-animatic is format-agnostic. A
  dialogue-first show needs exactly this chain.
- Wire-up: PIPELINE.md pre-production stage.

## TRANSFERS — partial

### 9. The 12-stage "studio in a box" pipeline (docs/COMPLETE-PIPELINE.md)
- What: FlipaClip drawings in, finished animation out: animatic, denoise,
  line cleanup, interpolation, de-ghost, upscale, FX, QC, grade, audio
  mix, encode, social export.
- What transfers: the STAGE ORDER and the finish.py QC/encode/social
  export pattern. Animatic-first ordering.
- What does not: the anime-specific FX stages (energy_blast, neon
  stroke_reveal, LED scene assembler), the anime upscale chain, and
  ToonCrafter/ToonComposer AI animation (wrong for limited animation).
- Wire-up: PIPELINE.md adapted stage list.

### 10. LatentSync / MuseTalk (COMPLEMENTARY-STACK.md)
- What: end-to-end AI lip sync, audio + video in, synced video out.
- Why partial: they animate video pixels (talking-head style), not
  phoneme charts for hand-drawn mouths. Wrong output for a 2D cartoon
  pipeline. Rhubarb/OpenFaceFX (above) are the right tools.
- Excluded from the 2D pipeline with this reason.

## DOES NOT TRANSFER — with reasons

### 11. Blender Cycles render optimizations (docs/research/RENDER-SPEED.md)
- What: 10-20x Cycles speedups (fewer samples, OIDN, half-res + SPAN
  upscale, half-fps + RIFE).
- Why not: this is 3D path-tracing optimization. A 2D limited-animation
  show has no 3D renders. Nothing to optimize.

### 12. Kaggle GPU queue automation (docs/AUTOMATION.md, kaggle_queue.py)
- What: systemd-timer GPU job queue for T4 rendering.
- Why not: the 2D pipeline runs on CPU/local. If heavy AI interpolation
  is ever needed, revisit; until then it is idle infrastructure.

### 13. AI video generation stack (GEMINI-PULL.md, GEMINI-FULL-PULL.md,
    STUDIO-GRADE-PULL.md, 2026-STUDIO-DEEP-DIVE.md)
- What: Wan 2.2, LTX-Video, HunyuanVideo, Mochi, ToonComposer,
  One-to-All Animation pose transfer.
- Why not: generative video output fights the HB limited-animation look
  (see the RIFE restraint rule). These are Cape Jones tools for a
  different visual style. Revisit only for specific FX shots, never for
  character animation.

### 14. 3D asset pipeline (TRACK-C-PULL.md)
- What: Kenney/KayKit CC0 3D kits, ambientCG, itch.io rigged characters.
- Why not: 2D show. No 3D assets needed.

### 15. Merch/community/monetization stack (TRACK-F-PULL.md)
- What: printful-mcp, ForgeBot, OBS overlays, tip jars.
- Why not: show is in pre-production. Revisit at distribution time.

## Stays in cape-jones (show-agnostic, not copied)

- The full pipeline scripts (`production/pipeline/`) — referenced, not
  duplicated. This show gets its own slim pipeline doc.
- The 3D render lane (Pantera, Kaggle notebooks) — different show,
  different medium.
- The AI video generation weights and runbooks — different visual style.

## Sources read

- docs/research/RESEARCH-INDEX.md (full index)
- docs/research/PRO-INBETWEENING-RESEARCH.md
- docs/research/INTERPOLATION-RESEARCH.md
- docs/research/RENDER-SPEED.md
- docs/research/COMPLEMENTARY-STACK.md
- docs/research/TRACK-B-AUDIO-PULL.md
- docs/research/TRACK-D-PULL.md (via index)
- docs/COMPLETE-PIPELINE.md
- docs/AUTOMATION.md
- docs/soundtracks/SOUNDTRACKS.md
