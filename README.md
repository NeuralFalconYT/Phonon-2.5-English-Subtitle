
# 🎙️ Phonon-2.5-English Subtitle

A simple, open-source English subtitle generator powered by [Phonon-2.5-English](https://huggingface.co/FermionResearch/Phonon-2.5-English).

Generate accurate, timestamped English subtitles for **YouTube videos, Shorts, Reels, and word-by-word captions** using a Gradio interface.

## ✨ Features

- 🎙️ **Phonon-2.5-English ASR** — English speech-to-text transcription.
- ⏱️ **Word-Level Timestamps** — Uses timestamps provided by Phonon.
- 🎬 **YouTube Subtitles** — Sentence-level horizontal subtitles.
- 📱 **Shorts / Reels Subtitles** — Short, vertical-friendly subtitle segments.
- 🔤 **Word-Level Subtitles** — One subtitle per recognized word.
- 📝 **TXT Transcript** — Export the full transcript.
- 📦 **ZIP Export** — Download all SRT files and the transcript together.
- 🎛️ **Gradio Interface** — Upload audio/video or use a local file path.
- 📊 **Live Activity Indicator** — Shows that transcription is running.
- 💻 **CPU Support** — Runs locally using the Fermion CPU backend.

> **Language:** English only.

## 📦 Output Formats

| Format | Description |
|--------|-------------|
| YouTube / Horizontal | Sentence-level SRT |
| Shorts / Reels Vertical | Short caption segments |
| Word Level | One word per SRT cue |
| Transcript TXT | Plain-text transcript |
| Export ZIP | All three SRT files + transcript |

### Example Output

Input:

`myvideo.mp4`

Generated files:

```text
myvideo_youtube_sentence.srt
myvideo_shorts_vertical.srt
myvideo_word_level.srt
myvideo_transcript.txt
myvideo_subtiles.zip
```

## 🚀 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/NeuralFalconYT/Phonon-2.5-English-Subtitle.git
cd Phonon-2.5-English-Subtitle
```

### 2. Install Dependencies

Python dependencies:

```bash
pip install -r requirements.txt
```

**requirements.txt**

```text
fermion-research==0.2.15
numpy==2.2.6
soundfile==0.13.1
gradio==5.50.0
```

### 3. Install FFmpeg

FFmpeg and FFprobe are required for audio extraction.

Check your installation:

```bash
ffmpeg -version
ffprobe -version
```

Make sure both are available in your system PATH.

### 4. Run the Application

```bash
python app.py
```

The Gradio interface will open in your browser.

## 🎬 How to Use

1. Launch the application.
2. Upload an audio or video file.
3. Configure optional subtitle formatting settings.
4. Click **Generate**.
5. Monitor the transcription activity indicator.
6. Download individual SRT/TXT files or the complete ZIP archive.

## ⚙️ How It Works

```text
Audio / Video Input
        |
        v
FFmpeg Audio Extraction
        |
        v
16 kHz Mono WAV
        |
        v
Phonon-2.5-English
        |
        v
Speech Recognition
+ Word-Level Timestamps
        |
        v
Subtitle Formatting
        |
        +--> YouTube / Horizontal SRT
        |
        +--> Shorts / Reels SRT
        |
        +--> Word-Level SRT
        |
        +--> Transcript TXT
        |
        v
     ZIP Export
```

## 📊 Transcription Progress

The application displays:

- Audio extraction progress
- Audio duration
- Transcription status
- CPU processing status
- A moving activity indicator
- Completion summary

**Note:** The transcription activity bar indicates that processing is ongoing. It does not represent an actual percentage of Phonon inference completion.

## 🤗 Hugging Face Spaces

This application supports deployment through a compatible Gradio Space.

The repository includes:

- `app.py`
- `requirements.txt`
- `packages.txt`

The `packages.txt` file installs FFmpeg in supported Spaces environments.

## ⚠️ Limitations

- English transcription only.
- Transcription speed depends on CPU performance and recording length.
- Subtitle accuracy depends on audio quality and the ASR model.
- An ongoing blocking model inference cannot be immediately interrupted by the Stop button.
- Long recordings may require additional memory and processing time.



## 🙏 Credits & Acknowledgements

This project is powered by **Phonon-2.5-English**, developed and released by **FermionResearch** on Hugging Face.

### Original Model

- **Model:** [FermionResearch/Phonon-2.5-English](https://huggingface.co/FermionResearch/Phonon-2.5-English)
- **Organization:** [FermionResearch](https://huggingface.co/FermionResearch)

All credit for the speech recognition model and its underlying technology belongs to its original creators.

This repository provides a Gradio-based subtitle generation interface built around the original model.

**Disclaimer:** This is an independent project and is not officially affiliated with or endorsed by FermionResearch or Hugging Face.

Please refer to the original model repository for its license and usage conditions.

