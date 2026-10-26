# Sound Forge

Browser-based game-music sketchpad. Pick a genre, get a full arrangement (melody, chords, bass,
arpeggio, pad, drums), tweak it, export WAV/MIDI. Single HTML file, Web Audio API, no build step,
no dependencies, no samples — every instrument is synthesized.

Inspired by "Score Forge" from [this r/aigamedev post](https://www.reddit.com/r/aigamedev/comments/1xfgvzz/ok_we_live_in_a_future_i_let_ai_create_me_a_tool/).

## Run

Open `index.html` in Chrome/Edge/Firefox. That's it.

## Features

- **8 genres × 3 styles** — Synthwave, Sci-fi, Postapo, Drama, Epic, Fantasy, Hip-hop, Ambient.
  Each style sets key, tempo, progression, instruments, drum pattern.
- **6 tracks** with density (Off / Soft / Normal / Busy), instrument, octave shift, volume, mute/solo.
  28 synth patches + 6 synthesized drum kits, reverb/delay sends, compressor + limiter.
- **Global**: tempo, swing, bars (4/8/16), key (auto or any root/mode — changing it transposes notes).
- **Sections + song**: create/duplicate/delete/rename sections, drag to reorder the arrangement,
  loop one section or play the whole song.
- **Piano roll**: click to add, drag to lengthen, click/right-click to delete. Scale and chord tones
  are tinted. Per-bar chord picker (re-voices backing), copy/paste/clear bar.
- **Generators**: New melody (motif with call & answer, cadence on tonic), New chords, New beat, Build backing.
- **Keyboard**: computer keys `Z S X D C…` (lower octave) and `Q 2 W 3 E…` (upper), chord/scale
  highlighting and "nice next notes" hints. Record live at the playhead or step-input when stopped.
- **Export**: Song → WAV, **Section loop → WAV (seamless**, renders two passes and keeps the second
  so reverb tails wrap — loops cleanly in a game engine), Song → MIDI, project save/load as JSON.
- Space = play/pause, Ctrl+Z = undo, autosave to localStorage.

## SFX generator (`sfx.html`)

sfxr-style sound-effect generator, but layered (up to 4 layers per sound, e.g. noise burst + sub drop
for an explosion). Rendered offline, so what you hear is exactly what gets exported.

- **16 categories**: Pickup, Coin/Gem, Laser, Explosion, Hit/Hurt, Jump, Blip/UI, Footstep, Swoosh,
  Powerup, Magic/Heal, Death, Alarm, Creature growl, Critter chirp, DNA splice. Each click = new random take.
- **Per layer**: wave (square/saw/triangle/sine/white/pink/brown noise), level, start delay,
  attack/sustain/punch/decay, frequency + slide (amount & curve), pitch jump (arpeggio), repeat,
  vibrato, FM (ratio/depth), lowpass sweep + resonance, highpass.
- **Output**: volume, drive, bitcrush, downsample, reverb, echo. Auto-normalized, silence trimmed.
- **Mutate** (bigger change), **Totally random**, **Variations** (N subtle versions — footsteps, hits)
  with batch WAV export. History of every take; save/load sounds as JSON.
- Export: mono 16-bit 44.1 kHz WAV.
