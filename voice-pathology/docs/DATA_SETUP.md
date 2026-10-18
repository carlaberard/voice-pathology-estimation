# Data and environment setup

The original project uses an EGG/NSP research dataset supplied separately during the university assignment. **The dataset, processed recordings, patient metadata and trained `.pkl` files are not distributed in this public portfolio repository.** Ensure you have permission and comply with the data provider's terms before running or sharing any related files.

## Python and FFmpeg

From the repository's root folder:

```bash
python -m venv .venv
# On Windows:
.venv\Scripts\activate
python -m pip install -r requirements.txt
jupyter lab
```

Install **FFmpeg** separately and confirm `ffmpeg -version` works in your terminal; notebook cells call the `ffmpeg` executable via `subprocess`.

## Required dataset structure

By default, place source recordings under `data/Speech_pathologies_dataset/`:

```text
data/
└── Speech_pathologies_dataset/
    ├── Healthy/
    ├── Laryngitis/
    ├── Hyperfunctional_Dysphonia/
    └── Recurrent_Laryngeal_Nerve_Paralysis/
```

Each class folder should contain the corresponding recordings in the `.egg` and `.nsp` formats expected by the original notebook, with patient identifiers and vowel/condition tags in filenames. See the notebook's dataset inspection cell for the precise filename parsing convention.

## Portable paths

The notebook defaults to a repository-local `data/` input folder and `outputs/` for processed files, intermediate WAV recordings, feature CSVs, and trained models. These folders are excluded from version control through `.gitignore`.

Alternatively set environment variables *before launching Jupyter*:

- `VOICE_PATHOLOGY_DATA_DIR`: folder containing the source `Speech_pathologies_dataset`
- `VOICE_PATHOLOGY_OUTPUT_DIR`: folder for locally generated artifacts

To replicate the pipeline, run cells in order and allow time for thousands of file conversions and acoustic-feature calculations. The notebook is intended as research code and can require adjustments for different data layouts or installed package versions.

## Microphone demonstration

The final notebook cell contains a local, optional 3 × 5-second vowel-recording demonstration using `sounddevice`. By default, `RUN_LIVE_DEMO = False` prevents unexpected microphone access when running the notebook. Only enable it once a compatible `trained_model_NSP.pkl` has been trained and the microphone is configured. It uses the NSP-only model, **not** the better-performing EGG+NSP fusion model.

The demo is **not a medical diagnostic tool**. Because a conventional microphone can differ from the original neck-surface sensor and some feature values are filled with zeros, performance and probability outputs may not generalize.
