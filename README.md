# Audio Feature Extraction Pipeline with Librosa

This project implements an exploratory audio feature extraction pipeline using **Librosa** and **Matplotlib**. It processes raw audio signals (`.wav`) to generate visual and mathematical footprints crucial for building downstream Speech Recognition, Audio Classification, or Deep Learning models.

## 📌 Core Concepts Explained

### 1. Sample Rate ($sr$)
Sound is an analog continuous wave. To process it on computers, it must be converted into digital numbers by capturing snapshots of its height at fixed intervals. The **Sample Rate** (measured in Hertz) defines how many snapshots are captured per second. Setting `sr=16000` means capturing 16,000 discrete digital points every single second of audio.

### 2. Time-Domain vs. Frequency-Domain
* **Time-Domain (`y`):** Tracks how a sound wave's *amplitude* changes over a timeline. It tells us **when** a noise happens and **how loud** it is, but it hides information about pitch.
* **Frequency-Domain:** Breaks apart the audio signal to uncover **which pitches/notes** (frequencies) make up the collective sound mix.

### 3. Short-Time Fourier Transform (STFT) & Spectrograms
A standard Fourier Transform calculates the frequency makeup of an entire audio clip all at once, discarding the time element. The **Short-Time Fourier Transform (STFT)** solves this by sliding small, overlapping time windows across the audio, computing the frequencies inside each specific window. Stacking these windows horizontally creates a **Spectrogram**—a 2D heat-map tracking frequencies over time.

### 4. The Mel Scale & MFCCs
* **Mel Scale:** Human ears interpret pitches non-linearly. We easily notice the pitch jump between 100 Hz and 200 Hz, but struggle to notice the jump between 10,000 Hz and 10,100 Hz. The Mel Scale deforms real frequencies (Hertz) to match how humans actually perceive pitch intervals.
* **MFCCs (Mel-Frequency Cepstral Coefficients):** MFCCs take a Mel-scale spectrogram and run a compression algorithm (Discrete Cosine Transform) over it. This extracts the overarching envelope structure of the sound (the "timbre" or tone quality) while dropping irrelevant background static. It serves as a compact fingerprint ideal for machine learning pipelines.

---


### How the next execution steps looks like

```bash

1. MFCC Matrix → CNN [DONE]

2. MFCC Matrix → CNN [PENDING]

3. Mel Spectrogram → CNN

4. Speech → Text

5. Whisper Implementation

```
