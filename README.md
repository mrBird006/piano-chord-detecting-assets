# 🎼 Audio Note & Chord Dataset

This dataset contains **12,261 audio files** representing isolated musical notes and chords generated at various tempos and durations. It is designed for tasks such as music information retrieval.

---

## 📦 Dataset Access

You can access the full dataset via Hugging Face:

🔗 **Dataset Homepage**:  
https://huggingface.co/datasets/mrBird006/piano-chord-decting-dataset

📥 **API Access**:  
```bash
curl -X GET \
  "https://datasets-server.huggingface.co/first-rows?dataset=mrBird006%2Fpiano-chord-decting-dataset&config=default&split=train"


Each audio file is in **WAV format**, with a consistent naming convention encoding musical parameters.

---

## 🔤 Audio File Naming Pattern

```
notes_[midi]_t[tempo]_d[duration].wav
```


Where:

- `<midi>`: MIDI number of the note or notes played. A single note is indicated by its number (e.g. `60`), chords by multiple values separated with hyphens (e.g. `60-64-67`).
- `<tempo>`: Tempo in beats per minute (BPM), e.g., `60`, `120`, `180`.
- `<duration>`: Note duration in beats, such as:
  - `0.25` → sixteenth note
  - `0.5`  → eighth note
  - `1.0`  → quarter note
  - `2.0`  → half note

📌 Example:
```
notes_100_t120_d0.25.wav → MIDI note 100, tempo 120 BPM, duration 0.25 (sixteenth note)
```

---

## 📊 CSV Metadata Fields

The file `dataset_metadata.csv` contains detailed information per audio sample. Columns include:

| Column               | Description                                       |
|----------------------|---------------------------------------------------|
| `timestamp`          | Time of frame within the audio                    |
| `notes_pressed`      | List of MIDI notes pressed                        |
| `num_notes`          | Number of notes played                            |
| `global_tempo`       | Tempo in BPM                                      |
| `note_duration`      | Duration in beats (0.25, 0.5, 1.0, 2.0)           |
| `rel_beat_pos`       | Relative beat position of the frame               |
| `spectral_centroid`  | Spectral centroid of the frame                    |
| `label_notes`        | Canonical list of notes                           |
| `chord_name`         | Detected chord name (e.g., Cmaj7, E7)             |
| `audio_file`         | Name of the corresponding audio file              |
| `mfcc_1` to `mfcc_13`| MFCC coefficients 1 to 13                         |

---

## 📦 Usage Ideas

- Instant Chord recognition

---

## ⚠️ License

### Audio files
The rendered audio files in `generated_audio/` were generated using the FluidR3_GM.sf2 SoundFont by Frank Wen and are licensed under Creative Commons Attribution 3.0 (CC BY 3.0). When using or redistributing these files, you must credit the author and link to the license:

- **SoundFont:** FluidR3_GM.sf2 by Frank Wen  
- **License:** CC BY 3.0  
- **URL:** https://creativecommons.org/licenses/by/3.0/legalcode  

### Code, metadata & MIDI data
Everything else in this repository—code, metadata, MIDI generation logic and documentation—is released under the MIT License. See the [`LICENSE`](./LICENSE) file for full details.

