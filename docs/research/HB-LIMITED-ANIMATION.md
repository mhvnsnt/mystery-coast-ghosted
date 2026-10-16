# Hanna-Barbera limited-animation technique

How HB actually made cartoons cheap and fast. Researched 2026-10-16 for
Mystery Coast: Ghosted. Owner rule: study technique, never copy assets.

## The economics that created the style

At MGM, Hanna and Barbera had about $45,000 for five minutes of animation.
For TV they got $2,700 for five minutes of *Ruff and Reddy*. MGM's
7-minute Tom and Jerry shorts cost about $35,000 vs. about $3,000 per
5-minute Ruff and Reddy episode. The HB style was not an aesthetic choice.
It was a hard budget constraint engineered into a system.

- Why it matters: design your production system around a real per-minute
  budget first, then build the visual language to fit it, not the reverse.
- Sources: "Hanna-Barbera: The Architects of Saturday Morning"
  (https://www.illustrationhistory.org/essays/hanna-barbera-the-architects-of-saturday-morning);
  Wikipedia, "Hanna-Barbera" (https://en.wikipedia.org/wiki/Hanna-Barbera)

## Frame-rate conventions: animate on 2s and 3s

Full animation (Disney) is 24 unique drawings per second. HB "planned
animation" repeated frames 2-3 times, yielding only 12 or 8 different
drawings per second (on twos and threes). A typical 7-minute HB short used
about 2,000 drawings instead of the usual 14,000 for full animation.

- Why it matters: deliberately animating on 2s/3s (8-12 unique poses/sec)
  is the single biggest cost saver and the core of the HB look. Do not
  interpolate. Hold.
- Sources: illustrationhistory.org essay (same); Beacon Journal
  (https://www.beaconjournal.com/story/news/2022/07/16/history-hanna-barbera-cartoons-and-connection-cincinnati-history/10037600002/)

## Character level separation: break the body into levels

Characters were split across cel levels so only the moving part was
redrawn. Fred Flintstone's head ran as one cel while separate mouth cels
were overlaid as he talked; the rest of the body sat on a held cel.

- Why it matters: this is exactly modern cutout rigging (head/body/limb
  layers with a mouth-switch system). Build characters as separated,
  independently animatable parts from day one.
- Sources: illustrationhistory.org essay (same); Wikipedia, "Hanna-Barbera"

## Design-for-reuse

HB characters were given neckties and collars so the head could sit on its
own cel without a seam line. Fred and Barney got five-o'clock shadows to
further reduce animation (Iwao Takamoto, *My Life with a Thousand
Characters*).

- Why it matters: design characters FOR the pipeline. Clean separation
  points at joints, simple mouths, accessories that hide layer seams.
  Character design is a production decision.
- Source: illustrationhistory.org essay (same)

## Walk cycles, run cycles, looping backgrounds

Animation cycles (walks, runs) were regularly repurposed, and
looping/repeating backgrounds were used extensively in chase sequences.

- Why it matters: build a library of reusable cycles (walk, run,
  chase-panic, scared reaction) and modular background loops. The chase
  sequence in every mystery episode is where you recycle the most.
- Sources: Wikipedia, "Hanna-Barbera"; hrwiki.org/wiki/Hanna-Barbera

## Timing by metronome, not by eye

Bill Hanna timed cartoons with a metronome: at 24fps he marked beats so a
144-bpm click equals 10 frames per beat, using it to set walk tempos and
coordinate action in frames.

- Why it matters: HB's snappy comic timing was measured, not felt. Modern
  equivalent: score action to a click track / fixed frame counts per beat
  in your Xsheet or timeline. This is why the walks and takes land.
- Source: illustrationhistory.org essay (same), quoting Hanna's *A Cast of
  Friends*

## Compensate with poses, writing, sound

HB explicitly redirected effort: "the writing had to be better scripted,
the gags had to be funnier, the cameraman had to be more creative, and the
sound effects more expressive." Takamoto: the poses had to be "extremely
accomplished and funny in and of themselves." Ward Kimball (Disney's Nine
Old Men): "Limited animation can be the best way to put across a humorous
idea." Chuck Jones dismissed it as "illustrated radio" because dialogue,
music, and SFX carried the shows over action.

- Why it matters: the formula is hold strong key poses plus invest in
  script, voice acting, music cues, and sound effects. For a
  dialogue-heavy, lazy-cast mystery show, this validates voice-first
  production.
- Sources: illustrationhistory.org essay (same); Wikipedia, "Hanna-Barbera"

## The stock music library system

Instead of scoring each episode, HB recorded cue libraries once and reused
them across shows for decades. Ted Nichols' 1969 Scooby-Doo underscore cues
became staples "used in countless subsequent cartoons" (still being reused
into 1985). Music editors "mixed and matched parts from all the tracks to
make a beautiful Frankenstein monster of a music bed in each episode."
Composer Hoyt Curtin said most cues were "play it once and then record."

- Why it matters: commission or compose a reusable cue library (chase,
  sneak, scare-sting, reveal) once, then re-edit it per episode forever.
  This is a huge recurring-cost killer.
- Sources: Cartoon Research
  (https://cartoonresearch.com/index.php/celebrating-ted-nichols-and-the-hanna-barbera-house-sound/);
  mxdwn (https://television.mxdwn.com/news/famed-hanna-barbera-composer-of-the-flintstones-and-scooby-doo-ted-nichols-passes-at-97/);
  classicjq.com Hoyt Curtin interview
  (http://www.classicjq.com/info/hoytcurtininterview.aspx)

## Scale through personnel, not process

HB's technique was perfected at scale by Kenneth Muse (ex-MGM), and the
studio staffed up with laid-off veterans (Michael Maltese, Warren Foster,
Tony Benedict). The process stayed cheap because the drawings were cheap,
not because labor was.

- Why it matters: limited animation is a drawings-savings system, not a
  talent-savings system. Spend on a few great posers/writers/voices, not
  on inbetweeners.
- Source: illustrationhistory.org essay (same)

## Myth-busting (verified)

- "Limited animation is just cheap/bad animation." The documented method
  shows engineered design: reusable poses that had to be "extremely
  accomplished and funny in and of themselves" (Takamoto), measured
  metronome timing, deliberate reinvestment in writing/voices/music/SFX,
  with defenders like Ward Kimball.
- "The name Scooby-Doo came only from Sinatra's scat singing." Disputed.
  Takamoto documented that an early-1960s HB development drawing already
  bore the name "Skooby," years before the 1969 flight story.

## Techniques to steal (with modern open-source equivalents)

1. Animate on 2s/3s (8-12 unique poses/sec), hold frames. Tahoma2D Xsheet:
   set exposure explicitly; Blender Grease Pencil stepped interpolation;
   Krita animation on 2s.
2. Character split into independently animatable levels (head/mouth/body)
   with held cels. Cutout rigging: Tahoma2D skeleton/peg hierarchy, mouth
   via switch layers.
3. Reusable walk/run/chase cycles + looping backgrounds. Build a shared
   cycle library as template scenes; backgrounds as parallax loops.
4. Design-for-reuse: clean joint separation points, seam-hiding
   accessories, limited mouth shape sets. Write it into the character
   design bible.
5. Metronome/beat-based timing. Cut animatics and action to a click track
   at fixed BPM (Kdenlive/Shotcut); lock walk cycles to exact frame counts
   per beat.
6. One reusable stock-music cue library, re-edited per episode by music
   editors. Compose/commission once, or use royalty-free libraries
   (Incompetech, FreePD, Pixabay Music). Post-score only the
   pilot/specials to picture.
7. Dialogue-first: voices recorded before animation, visuals built to
   serve the vocal. Animatic-first pipeline: final VO to animatic to
   animation. Lip sync only to held mouth shapes.
8. Stock SFX + small sweetening library, used sparingly. Build one SFX
   pack (freesound.org CC0/CC-BY). Do not repeat the 1960s mistake of
   over-repeating a tiny laugh library.
9. Recycle the formula show-to-show. Once the pipeline works, reuse the
   engine for spinoffs/variants with different skins. That was HB's actual
   business model.
