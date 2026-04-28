# Predator SDR

## Overview

Predator SDR is a fork of [SDR++](https://github.com/AlexandreRouma/SDRPlusPlus), a high-performance Software Defined Radio application. This project aims to provide a cleaner, more mission-focused interface for working in the electromagnetic environment (EME).

## Project Type

This is a **C++ desktop/Android application** — not a web app. It uses:
- **CMake** as the build system
- **Dear ImGui** for the GUI
- **OpenGL / GLES 3** for rendering
- **FFTW3 + Volk** for DSP processing
- **Kotlin/JNI** for the Android wrapper

## Replit Environment

Since this is a native C++ application (not a web app), a simple Python HTTP server (`server.py`) serves an informational landing page (`index.html`) at **port 5000**. This page describes the project, its tech stack, roadmap, and build instructions.

### Files

- `server.py` — Python HTTP server serving the landing page on port 5000
- `index.html` — Project info/landing page
- `CMakeLists.txt` — CMake build configuration for the C++ application
- `core/` — Core SDR engine (C++)
- `source_modules/` — Hardware driver plugins (RTL-SDR, HackRF, Airspy, etc.)
- `sink_modules/` — Audio/network output handlers
- `decoder_modules/` — Signal decoders (AM/FM/SSB, Meteor, M17, etc.)
- `misc_modules/` — Utility plugins (scanner, recorder, frequency manager, etc.)
- `android/` — Android Gradle project + Kotlin wrapper

## Building Natively (Linux)

```bash
sudo apt install cmake libfftw3-dev libglfw3-dev \
  librtlsdr-dev libhackrf-dev libairspy-dev \
  portaudio19-dev libsoapysdr-dev

mkdir build && cd build
cmake .. -DCMAKE_BUILD_TYPE=Release
make -j$(nproc)
sudo make install
```

## Roadmap

- [x] Android app
- [ ] Linux build
- [ ] Windows build
- [ ] Remote SDR ecosystem
