# TTS Dataset Preparation Notebook

This repository contains a Jupyter Notebook for processing audio files, performing speaker diarization, extracting segments, and transcribing them using Whisper and Gemini models. It works with GPU support.

---

## Requirements

- Python 3.10.11  
- GPU with CUDA (for PyTorch)  
- Conda (recommended)  

---

## Setup Instructions

### 1. Clone the repository

```bash
git clone <your-repo-url>
cd <repo-folder>
````

### 2. Create Conda environment with Python 3.10.11

```bash
conda create -n tts_env python=3.10.11
conda activate tts_env
```

### 3. Install PyTorch with GPU support

```bash
conda install pytorch torchvision torchaudio pytorch-cuda=12.1 -c pytorch -c nvidia
```

### 4. Install remaining dependencies

```bash
pip install -r requirements.txt
```

### 5. Set up environment variables

Create a `.env` file in the repository root.

Add your API keys:

```env
HF_TOKEN=<Your_HuggingFace_Token>
GEMINI_API_KEY=<Your_Gemini_API_Key>
```

### 6. Run the Notebook

Open `Notebook.ipynb` in Jupyter.

Execute cells step by step to process audio files, generate speaker embeddings, and export segments with transcriptions.

---

## Notes

* The notebook will automatically detect if GPU is available.
* Speaker embeddings are saved locally for reuse (`speaker_embeddings.pt`).
* Audio segments shorter than `MIN_LEN` are padded or merged to avoid very short clips.

```
