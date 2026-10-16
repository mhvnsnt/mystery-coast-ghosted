# Open-source 2D animation tooling (verified 2026)

Tools verified real, maintained, and license-checked 2026-10-16 for an HB
limited-animation pipeline. Owner rule: proven open-source tools, never
hand-built hacks.

## The core stack

### Tahoma2D — animation core (Modified BSD, v1.6.3 released 2026)
Full 2D animation suite (fork of OpenToonz/Ghibli Toonz): raster+vector
drawing, Xsheet + Timeline, skeleton cutout/puppet rigging (FK/IK), drawing
substitution, mesh deform, FX Schematic node compositing, FFmpeg export,
built-in Rhubarb lip sync. Releases through 2026 (1.6 in March, 1.6.1 in
May, 1.6.2 in July, 1.6.3 current). The Xsheet/exposure workflow is
literally how HB timed limited animation (held drawings, twos, planned
holds). Cutout skeleton rigging is puppet-style character animation
without redrawing.

- Project: https://github.com/tahoma2d/tahoma2d
- Releases: https://github.com/tahoma2d/tahoma2d/releases
- Cutout docs:
  https://github.com/tahoma2d/tahoma2d_docs/blob/HEAD/source/creating_cutout_animation.rst

### Rhubarb Lip Sync — lip sync (MIT, bundled in Tahoma2D 1.5+)
Phoneme recognition from audio (PocketSphinx) to 9 mouth shapes (A-H, X),
JSON/TSV/XML timing. Maintenance mode but complete and stable (last push
2025-04-03). Hand-drawn mouth charts driven by its cues are exactly the
HB-style approach. Being built into Tahoma2D removes integration work.

- Project: https://github.com/danielswolf/rhubarb-lip-sync
- Bundling: https://github.com/tahoma2d/tahoma2d/releases/tag/v1.5

### OpenFaceFX — lip-sync cue sheets (MIT, CPU-only)
Audio + transcript to viseme animation curves. Outputs to
OpenToonz/Moho `.dat` (Preston-Blair mouth names), Rhubarb TSV/JSON,
Papagayo `.pgo`. The `.dat` output drops straight into Tahoma2D. Already
pulled into cape-jones (`tools/openfacefx/`).

### Krita — boards and backgrounds (GPL, v5.3.4 / v6.0.4 released ~Sept 2026)
Raster painting + frame-by-frame animation workspace, onion skinning,
timeline, Comic Manager for storyboards. No cutout rigging/bone system, so
it cannot be the animation core. Use for storyboards, background painting,
FBF effects.

- https://krita.org/

### Blender — composite and finishing (GPL)
Grease Pencil (GPv3 rewrite since 4.3; 5.2 LTS June 2026; 5.3 due
2026-11-10 with Carver tool + VSE ripple editing), compositor, Video
Sequencer. Best as FX + composite companion, not the primary animation
tool.

### TheAnimeScripter — selective interpolation (MIT-family, updated Oct 2026)
Toolkit bundling RIFE interpolation + AI upscalers with anime-tuned
defaults, scene-change detection, dedup modes. The most practical RIFE
wrapper. Use ONLY where the boards call for it (walk-cycle in-betweens,
slow-mo, pans). Restraint is the feature: blanket interpolation destroys
the held-pose timing that defines the HB look.

- https://github.com/NevermindNilas/TheAnimeScripter

### RIFE (Practical-RIFE) — interpolation engine (MIT)
Real-time video frame interpolation; v4.25 author-recommended
("anime scenes significantly improved"). Stable/maintenance mode. See the
restraint rule above and the ghosting warning in CAPE-JONES-TRANSFER.md.

- https://github.com/hzwer/practical-rife

## Scratch dialogue (animatics only — final voices stay human)

### Dia (Nari Labs) — multi-speaker scratch scenes (Apache 2.0)
1.6B TTS generating multi-speaker dialogue in one pass from a transcript,
with laughter/nonverbals. GPU needed (~8-10GB VRAM). Best for scratch
scene dialogue: a two-character back-and-forth in one generation, exactly
what animatics need for timing.

- https://github.com/nari-labs/dia

### Piper TTS — instant scratch lines (engine GPLv3)
Fast local neural TTS (ONNX, CPU-friendly, 15-100MB voices), 20+
languages. Best for instant scratch lines, one voice per character. Note:
some individual voices carry their own licenses; check per voice. Already
pulled into cape-jones (`tools/piper/`).

- https://github.com/rhasspy/piper

### Kokoro-82M — quality scratch voices (Apache 2.0)
82M-parameter open-weight TTS, natural 24kHz voices, offline, ~20 voice
presets. Best quality-per-convenience scratch voice.

## Music and SFX (the modern HB stock library)

### Incompetech (Kevin MacLeod) — production music (CC BY 4.0)
2,000+ library-music tracks in film-score/cartoon styles (e.g. "Scheming
Weasel," styled after classic cartoon scoring; "Comic Hero"
silent-film-comedy cues). The modern equivalent of HB's stock-music
libraries. Attribution required; paid no-attribution license available.

- https://incompetech.com

### FreePD archive — public-domain cues (CC0 1.0)
Kevin MacLeod's former public-domain music site (freepd.com closed 2025);
community GitHub mirror of the archive. Zero-attribution cartoon scoring
cues.

### Pixabay Music — volume pick (Pixabay Content License, no attribution)
170k+ royalty-free tracks and loops. Quality varies; use for beds/stingers
when you need quantity fast.

- https://pixabay.com/music/

### Freesound — SFX library (CC0 / CC BY / CC BY-NC per sound)
700k+ community SFX (boings, whistles, slides, crashes: the cartoon
vocabulary) with per-file licensing and a REST API. Filter to CC0/CC-BY
for safety. The SFX side of the HB stock-sound tradition; the API makes
it scriptable.

- https://freesound.org

### Audacity — score layup (GPLv3, v4.0.1 released 2026-09-30)
Audio editing/mixing for the final score + SFX layup. Where the stock cues
get cut to picture.

### ACE-Step — song generation (Apache 2.0)
Lyrics-to-full-song, fast. For theme/cue generation.

### Stable Audio Open — music and SFX generation (MIT code)
Text-to-music + SFX (44.1kHz stereo). Small-SFX variant for foley-style
generation.

### Demucs — stem separation (MIT)
4-stem hybrid transformer (vocals/drums/bass/other). For pulling apart
reference tracks and cleaning recordings.

## Honest exclusions (investigated, rejected, with reasons)

- **Pencil2D**: frame-by-frame only, no rigging. Wrong core for a puppet
  show.
- **Synfig Studio** (GPLv3, v1.5.4 Jan 2026): auto-tweening and bones are
  useful, but strengths skew toward smooth morphing/full animation, and UX
  is widely reported crash-prone. Backup choice, not the core.
- **Wav2Lip / MuseTalk / talking-head AI**: animate photorealistic faces
  from audio; output video, not phoneme charts for hand-drawn mouths.
  Wrong tool for 2D cartoon lip sync.
- **Coqui XTTS**: CPML license has non-commercial/training restrictions
  that complicate a commercial pipeline. Dia and Kokoro cover the need
  under clean Apache-2.0 terms.
- **Bark (Suno)**: MIT but enormous, slow, effectively unmaintained.
  Superseded by Kokoro/Dia.
- **EISAI / AnimeInbet / AnimeInterp as production tools**: great papers,
  stale code. Use their ideas (EISAI's hold-aware dedup especially), not
  their repos.
- **Uppbeat free tier**: monthly download caps + required credits. Fine as
  a supplement, not a library foundation.
- **Papagayo-NG**: fun (Preston Blair phoneme sets are the actual HB
  mouth-chart tradition) but manual and stale (last push 2023-04-25).
  Rhubarb wins.
- **SMEAR (MoStyle Blender add-on)**: real open-source smear-frame
  generation (SIGGRAPH 2024), but license not verified this pass and it
  targets 3D/mesh animation. Verify LICENSE before building on it.

## Could not verify (stated plainly)

- No maintained open-source walk-cycle template pack found. Recommendation:
  author house walk cycles once as Tahoma2D template scenes and reuse them.
  That is the HB method anyway.
- No maintained open-source HB-style background generators found. Krita
  plus a house style guide is the honest answer.
- Blender's exact SPDX license identifier not re-verified this pass
  (GPLv2-or-later historically).

## The single most important pipeline decision

Restraint with AI interpolation. Limited animation's charm IS the holds,
the twos, the snappy pose-to-pose pops. RIFE everywhere turns Scooby-Doo
into soap-opera video. Animate on the Xsheet like it is 1969, and let AI
touch only the shots the timing charts explicitly mark for smoothing.
