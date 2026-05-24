---
title: "Speak2Write"
date: 2026-05-22T10:00:00+01:00
draft: false
tags: ["python", "ml"]
description: "One-line summary of the project."
cover:
  # image: "/images/projects/sample-cover.jpg"
  alt: "Project cover"
  relative: false
ShowToc: true
TocOpen: false
---

## Speak2Write — Audio Transcription Text Editor

Speak2Write is an experimental desktop application that captures short chunks of audio, transcribes them into text, and presents the results in a lightweight text editor UI. The core goals are low-latency transcription, resilience to silence/noise (via VAD), and a simple UX for dictation and note-taking.

## Architecture (summary)

The application is organized into three cooperating components:

- **UI (PyQt5)** — The main application window. Users start/stop/pause recording and view live transcriptions.
- **Audio Record Process (Chunking)** — Records the microphone stream and slices it into short `.wav` files (configurable chunk length, e.g., 3s) which are enqueued for transcription.
- **Transcribe Process (Silero VAD + Whisper)** — Dequeues chunk files, runs Silero VAD to detect speech, sends speech chunks to Whisper for transcription, and deletes temporary `.wav` files after processing.

### Workflow (high level)

1. User triggers recording in the PyQt5 UI.
2. Audio Record Process saves fixed-interval chunks (e.g., 3s) and pushes file paths to a queue.
3. Transcribe Process pulls chunk paths, runs Silero VAD; if speech is detected, the chunk is passed to Whisper for transcription.
4. Transcribed text is sent back to the UI (async) and the chunk file is deleted.

## Key Features

- Chunked recording avoids large files and enables near-real-time transcription.
- Silero VAD filters out silence/noise to save CPU on Whisper calls.
- Configurable chunk length and cycle length for fine-tuning latency vs throughput.

## Stack

- Python 3
- PyQt5 (UI)
- Silero VAD (voice activity detection)
- OpenAI/Whisper (speech-to-text)
- Standard libraries: multiprocessing/queue, wave, sounddevice (or pyaudio)

## Screenshots

Screenshot of the app UI:

![Speak2Write UI](https://raw.githubusercontent.com/praveenRI007/Speak2Write/main/Capture.png)

Architecture / workflow diagram:

![Speak2Write Architecture](https://raw.githubusercontent.com/praveenRI007/Speak2Write/main/Speak2Write.png)

## How to run (quick)

Clone the repo and follow the README in the project:

- Repo: https://github.com/praveenRI007/Speak2Write

Quick steps (see the repo for full instructions):

```bash
git clone https://github.com/praveenRI007/Speak2Write.git
cd Speak2Write
# create venv, install deps
pip install -r requirements.txt
# run the app
python main.py
```

## Links

- GitHub: https://github.com/praveenRI007/Speak2Write
- Screenshot: https://github.com/praveenRI007/Speak2Write/blob/main/Capture.png
- Workflow diagram: https://github.com/praveenRI007/Speak2Write/blob/main/Speak2Write.png

---

