# TTS Dataset Preparation Notebook

This repository contains a Jupyter Notebook for processing audio files, performing **speaker diarization**, extracting segments, and transcribing them using Whisper and Gemini models. It works with GPU support.

---

## Requirements

- Python 3.10.11
- GPU with CUDA (for PyTorch)
- Conda (recommended)

---

## Setup Instructions

1. **Clone the repository**

```bash
git clone <your-repo-url>
cd <repo-folder>
Create Conda environment with Python 3.10.11

bash
Copy code
conda create -n tts_env python=3.10.11
conda activate tts_env
Install PyTorch with GPU support

bash
Copy code
conda install pytorch torchvision torchaudio pytorch-cuda=12.1 -c pytorch -c nvidia
Install remaining dependencies

bash
Copy code
pip install -r requirements.txt
Set up environment variables

Create a .env file in the repository root.

Add your API keys:

env
Copy code
HF_TOKEN=<Your_HuggingFace_Token>
GEMINI_API_KEY=<Your_Gemini_API_Key>
Run the Notebook

Open Notebook.ipynb in Jupyter or VSCode.

Execute cells step by step to process audio files, generate speaker embeddings, and export segments with transcriptions.

Notes
The notebook will automatically detect if GPU is available.

Speaker embeddings are saved locally for reuse (speaker_embeddings.pt).

Audio segments shorter than MIN_LEN are padded or merged to avoid very short clips.

markdown
Copy code
