# Cape Jones transfer addendum (2026-10-16, part 2)

Follow-up findings from the late-arriving transfer-survey worker, which
read 15 cape-jones docs including several not covered in
CAPE-JONES-TRANSFER.md. Every file claim below was re-verified to exist
in mhvnsnt/cape-jones main via the GitHub API before writing. Judgment
calls are marked as such.

## Additional TRANSFERS — yes

### 1. dialogue_pipeline.py (production/pipeline/dialogue_pipeline.py)
- What: dialogue JSON to per-line WAVs plus timing.json. Engine priority
  per the worker: Dia2 (multi-speaker tags) to Chatterbox (voice cloning)
  to Kokoro (fast CPU) to Bark (non-verbals: laughs, sighs, gasps) to
  espeak-ng fallback.
- Why it transfers: a lazy comedy-mystery ensemble lives on banter.
  Scratch dialogue in hours with consistent character voices, feeding the
  animatic and the lip-sync stage.
- Wire-up: copy and retune for this show's cast; output feeds the
  Rhubarb/OpenFaceFX lip-sync stage. (Proposal, not yet done.)

### 2. anime_fx.py — speed lines, impact flash, screen shake
- What: CPU-only ffmpeg/OpenCV overlays: radial manga speed lines, impact
  flash plus starburst, animated-crop screen shake.
  (production/pipeline/anime_fx.py, verified present.)
- Why it transfers: mystery chases need speed lines and impact frames; the
  ghost-reveal moment needs impact flash. Direct fit.
- Wire-up: PIPELINE.md FX stage.

### 3. retro_fx.py — VHS/CRT/chromatic aberration
- What: VHS tracking distortion, CRT scanlines, phosphor glow, noise,
  intensity control. (production/pipeline/retro_fx.py, verified present.)
- Why it transfers: "found footage" / haunted VHS / security-cam segments
  fit the mystery format and the SGC2C/ATHF retro register.
- Wire-up: PIPELINE.md FX stage.

### 4. comp_glow.py — glow, light-wrap, atmosphere, vignette
- What: scriptable ffmpeg compositing: neon glow, background light spill
  on character edges, depth haze, focus vignette, with presets.
  (production/pipeline/comp_glow.py, verified present.)
- Why it transfers: ghost glow effects, haunted-house atmosphere,
  neon-sign mystery locations.
- Wire-up: PIPELINE.md FX stage.

### 5. MIXED-MEDIA-GUIDE.md — environment techniques
- What: three technique studies from real shows: Gumball photo-background
  compositing under flat characters, Ed-Edd-n-Eddy emotional
  non-realistic color, Chowder fixed-screen-space pattern fills.
  (docs/environments/MIXED-MEDIA-GUIDE.md, verified present.)
- Why it transfers: show-agnostic technique, not assets. Photo-background
  compositing gives cheap mystery locations; emotional color carries
  mystery mood.
- Wire-up: background art direction reference; replace Cape Jones
  examples with this show's locations (haunted house, van interior).

### 6. ToonCrafter — selective cartoon interpolation
- What: cartoon-native interpolation (SIGGRAPH Asia 2024) that handles
  flat color regions better than RIFE. Cape Jones pulled it for Kaggle T4
  runs (per RESEARCH-INDEX.md, INTERPOLATION-RESEARCH row).
- Why it transfers, with a restraint: for hero shots and chase scenes
  ONLY, via the shared kaggle_queue. This is compatible with the
  restraint rule in PIPELINE.md (AI touches only marked shots). It does
  not replace the Xsheet-first method.
- Judgment call: generative interpolation is a tool for marked shots,
  never the default.

## Additional TRANSFERS — partial (qualified)

### 7. LatentSync — talking-head close-up post-process
- What: audio plus video in, lip-synced video out. Works on animated
  characters per the worker; GPU on Kaggle.
- Why partial: it re-renders video pixels rather than producing phoneme
  charts, so it cannot replace the Rhubarb/OpenFaceFX mouth-chart
  workflow. But as a POST-PROCESS on finished, locked dialogue close-ups
  (the SGC2C interview framing is this show's DNA), it is a legitimate
  option for talking-head shots.
- Judgment call: post-process only, never the primary lip-sync method.

### 8. kaggle_queue.py — shared GPU queue
- What: JSON queue plus systemd timer for batch Kaggle GPU jobs.
  (docs/AUTOMATION.md, read in part 1.)
- Correction to part 1: this was marked "does not transfer" on the
  grounds the 2D pipeline runs on CPU. That was too broad. The queue is
  show-agnostic infrastructure; Mystery Coast's GPU jobs (ToonCrafter
  hero shots, LatentSync close-ups, Dia2 scratch voices) should go
  through the EXISTING queue with a show tag, not a new one.

## Stays excluded (worker agreed or no new evidence)

- Cycles render optimizations, Pantera pipeline, 3D living-room, LED
  system, canon grades, canon soundtrack picks, Quaternius/Tripo 3D,
  Track F merch: all confirmed 3D or canon-specific. No change.
- JoSTC (line-art vector tracing): mentioned by the worker but not
  independently verified this pass. Left out until verified.

## Wire-up status of this addendum

Proposals 1-6 are documented, not yet executed. They belong in a future
pipeline-setup turn: copy dialogue_pipeline.py and retune, add the three
FX scripts to the FX stage, adopt the mixed-media environment guide, and
wire ToonCrafter/LatentSync jobs through the shared kaggle_queue with a
show tag. Nothing here changes the restraint rule: AI touches only marked
shots.
