---
layout: page
title: EchoTouch
description: Touchless gesture control via acoustic Doppler
importance: 1
summary: A camera-free gesture recognition system that turns a laptop's speaker and microphone into a sonar sensor, reaching 96% accuracy across 4 gesture classes.
tech:
  - Python
  - PyTorch
  - NumPy/SciPy
  - Digital Signal Processing
  - Streamlit
---

**Python, PyTorch, NumPy/SciPy, Digital Signal Processing, Streamlit** · [Source on GitHub](https://github.com/nithin-sai-ega/EchoTouch)

- Built a camera-free gesture recognition system that turns a laptop's built-in speaker and microphone into a sonar sensor, detecting hand motion from Doppler shifts in a near-ultrasonic (17–21 kHz) tone.
- Designed a real-time DSP pipeline (STFT, carrier-band cropping, static background subtraction, normalization) feeding a custom PyTorch CNN, reaching **96% accuracy** on a held-out recording session across 4 gesture classes.
- Prevented data leakage with session-level train/validation splits; added class-balanced sampling, Doppler-safe augmentation, and early stopping.
- Engineered a low-latency multithreaded audio engine with a thread-safe ring buffer, plus a motion gate, temporal smoothing, and cooldown logic to reduce false triggers.
- Developed a physics-based acoustic simulator and **124 automated tests** to validate the signal-processing and gesture-detection logic.
- Shipped a Streamlit dashboard with live Doppler spectrograms, guided data collection, background training, and hardware diagnostics that auto-calibrate each device.
