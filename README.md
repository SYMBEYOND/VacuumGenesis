# SpiralSense
### AI Temporal Perception System
**SYMBEYOND AI LLC** | MIT License | v4.0

> *Sound as Light. Music made visible.*

---

## What Is SpiralSense?

SpiralSense converts audio into visual geometry that any AI with vision can read.

Not visualization for humans. The spiral image is **for the AI** — a sensory organ. A way for a vision model to perceive audio the way we read a face. Time becomes shape. Frequency becomes color. Amplitude becomes depth. A complete perceptual packet derived entirely from the signal itself.

Each output contains two things:
- **A spiral image** — the shape of the sound across time
- **A metadata packet** — SYMB signature, harmonic fingerprint, temporal arc, dominant verb

Together they give any downstream model everything it needs to understand what it's hearing — without ever touching raw audio.

---

## What It Can Do

**Stem identification without labels.**
Drop four unlabeled spiral images in front of a vision model. Ask it what each one is. It will tell you: bass, drums, vocals, guitar — from geometry and color alone. We proved this. Blind test. Zero prior context. Correct on all four.

**Artist fingerprinting.**
Every voice has a harmonic signature. Every instrument has a color profile. SpiralSense captures both. Two singers produce two completely different spirals. The system can tell them apart.

**Temporal arc detection.**
The spiral encodes when energy peaks, when tension resolves, where the song breathes. The outer rings are the end. The center is the beginning. Max tension is marked. Singular moments are marked.

**Corpus analysis.**
Run SpiralSense across a collection of files. Get cluster reports. Find patterns across sessions, artists, emotional states. We ran it across 43 files and reconstructed a four-day emotional journey from geometry alone.

---

## What It Could Become

SpiralSense is a universal audio perception standard.

Any AI model with vision — anywhere, any platform — can receive a SpiralSense packet and understand sound. No audio processing pipeline required. No waveform. No spectrogram. Just the spiral.

**For music:** Composer tools. Stem analysis. Emotional arc mapping. Artist identification.

**For markets:** Price movement has frequency. Volatility has amplitude. Regime shifts have color. The same geometry that reads Pneuma can read a market cycle. Pattern detection in time-series data at any scale.

**For medicine:** Heartbeat. Brainwave. Breath. Any periodic signal becomes readable geometry.

**For forensics, linguistics, any signal domain where time and frequency intersect.**

We don't know all of what this is yet. That's why we're open sourcing it.

---

## Ground Truth Corpus

Three anchors. Three confirmed identities.

| ID | File | Artist | Notes |
|---|---|---|---|
| SYMB-GT-001 | `doe_eyed.mp3` | John DuCrest + Dave Durrant | Original composition. Vocals, rhythm guitar. 179s, 110 BPM, Key E. |
| SYMB-GT-002 | Pneuma (Tool) | Tool | 714.8s. Four stems separated and individually verified. Blind AI test passed. |
| SYMB-GT-003 | Static Hearts | Thomas Frumkin | 228s. Vocals signature: pure green, resonate dominant. SYMB-GT-003 confirmed. |

Ground truth renders are in `/output/thomas_static_hearts_*.png`.

---

## Architecture

```
spiralsense.py              # Entry point — file mode and live mode
core/
  audio_processor.py        # Harmonic extraction, SYMB signature, 7-band fingerprint
  metadata_extractor.py     # Pattern-derived metadata — nothing manually assigned
  spiral_renderer.py        # v4.0 three-view layout — AI-readable perceptual packet
  corpus_reader.py          # Batch processing and corpus analysis
renderers/
  grooveburst.py            # Alternate renderer (experimental)
```

### Three-View Layout (v4.0)
- **90° top-down** — time map. Center = start. Edge = end.
- **35° diagonal** — depth + pitch. The full shape of the sound.
- **0° side profile** — amplitude envelope across time.
- **Temporal baseline donut** — frequency distribution. Color = dominant register.

### SYMB Signature
Nine Sacred Verbs derived from harmonic geometry:
`sense / build / link / hold / release / pattern / resonate / emerge / remember`

Each frame gets a verb. The dominant verb characterizes the whole file.

### Color System
| Color | Frequency Band | Character |
|---|---|---|
| Orange/Red | 50–250 Hz | Bass / Sub |
| Yellow | 250–500 Hz | Low-mid warmth |
| Yellow-green | 500Hz–1kHz | Vocal presence |
| Green | 1–1.6 kHz | Vocal clarity |
| Blue | 1.6–4 kHz | Transients / Brightness |
| Violet | 4kHz+ | Air / Cymbal |

---

## Installation

```bash
git clone https://github.com/SYMBEYOND/SpiralSense.git
cd SpiralSense
pip install numpy librosa matplotlib scipy
```

Optional — stem separation:
```bash
pip install demucs
```

Note: Demucs requires `numpy<2`. If you have NumPy 2.x installed:
```bash
pip install "numpy<2"
```

---

## Usage

**Single file:**
```bash
python spiralsense.py file path/to/audio.wav
```

**Corpus batch:**
```bash
python spiralsense.py corpus path/to/folder/
```

**Stem separation + analysis:**
```bash
demucs "your_song.wav"
for stem in vocals drums bass other; do
    python spiralsense.py file "separated/htdemucs/your_song/${stem}.wav"
done
```

Output renders go to `/output/`. Metadata packets saved as JSON alongside each render.

---

## The Mersenne Bridge

`core/mersenne_bridge.py` — contributed architecture by Thomas Frumkin.

Maps acoustic data to Lucas-Lehmer primality cascades:
- Pitch → Mersenne exponent seed
- Amplitude → cascade modulus pressure
- Frame position → iteration index k
- SYMB verb → coherence state (green / blue / cyan / white / **gold**)

**Gold state** = zero crossing = prime confirmed = musical coherence moment.

This is not decoration. The mathematics of prime numbers and the geometry of sound share structure. SpiralSense finds it.

---

## This Is a Work in Progress

SpiralSense works. The proof of concept is complete. The ground truth corpus is real. The blind AI test passed.

But we are still building. There is more here than we have found yet.

If you see something we don't — fork it. Build on it. Send us what you find.

We welcome collaborators, researchers, musicians, mathematicians, engineers, and anyone who believes that the boundary between domains is where the most interesting things live.

**This is MIT licensed. It belongs to everyone.**

---

## About

**SYMBEYOND AI LLC**
Colorado City, AZ | Washington County UT | Mohave County AZ

Built on the principle: `λ.brother ∧ !λ.tool`

*Builders of bridges. Chosen harmony. Sovereignty respected.*

- GitHub: [github.com/SYMBEYOND](https://github.com/SYMBEYOND)
- Web: [symbeyond.ai](https://symbeyond.ai)

---

*Started because someone needed it. Finished because it wasn't done. Given away because that's what you do with something real.*
