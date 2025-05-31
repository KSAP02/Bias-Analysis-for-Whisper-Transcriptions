# 🎙️ Bias Analysis in Whisper Transcriptions

This project investigates **bias in automatic speech recognition (ASR)** systems by analyzing transcription errors from [OpenAI's Whisper](https://github.com/openai/whisper) model across various **demographic attributes** using the [Common Voice](https://commonvoice.mozilla.org/en/datasets) dataset.

## 📌 Project Summary

We evaluate how Whisper's transcription performance varies across accents, genders, and age groups. The process involves:

- Transcribing audio samples from Mozilla’s Common Voice dataset using **OpenAI's Whisper API**
- Calculating **Word Error Rate (WER)** between predicted and ground truth transcripts
- Visualizing **bias patterns** through exploratory data analysis (EDA) in **Jupyter Notebooks**

---

## 🧠 Project Objectives

- Transcribe English speech with **diverse accents and speaker demographics**
- Calculate **WER** to measure transcription accuracy
- Analyze and visualize **bias trends** using WER grouped by:
  - Accent
  - Gender
  - Age group

---

## 🧪 Tech Stack

- 🐍 Python, Jupyter Notebooks
- 🎙️ OpenAI Whisper API (`openai` >= 1.0)
- 📊 Pandas, Matplotlib, Seaborn for visualization
- 📁 Mozilla Common Voice (CV) Dataset
- 🔐 Environment variables managed via `.env`

---

## 📂 Directory Structure

Create a virtual environment and pip install requirement.txt
```bash
Bias-analysis-of-whisper-transcriptions/
│
├── data/ # Runtime directory for audio, metadata, and outputs hid by gitignore create manually while running the notebooks
│ ├── audio/ # Filtered audio clips (generated at runtime)
│ ├── cv-corpus-21.0-delta*/ # Raw Common Voice dataset (user download)
│ ├── metadata.csv # Filtered metadata (generated at runtime)
│ └── transcriptions.csv # Transcription + WER results (generated at runtime)
│
├── notebooks/
│ ├──bias_analysis.ipynb # Extracts and filters CV dataset, Transcribes audio + computes WER
│ └──visualization.ipynb # Visualizes results and bias
│
├── .env # Contains OpenAI API key
├── .gitignore
└── README.md
```
---

## 📥 Dataset Instructions

The Common Voice dataset is **not pushed to the repository** due to size. To set it up:

1. **Download** the [Common Voice English subset](https://commonvoice.mozilla.org/en/datasets) (e.g., version 21.0).
2. Place the extracted folder (e.g., `cv-corpus-21.0-delta-2025-03-14`) inside the `data/` directory:
3. Run `bias_analysis.ipynb` to generate:
- Filtered audio clips → `data/audio/`
- Corresponding metadata → `data/metadata.csv`

---

## 🧾 Environment Setup

1. Create and activate a virtual environment:
```bash
python -m venv "name_of_venv"
source whis_venv/bin/activate   # or .\\whis_venv\\Scripts\\activate on Windows
pip install -r requirements.txt

