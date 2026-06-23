# Unofficial-PEQdB-Companion-App-for-macOS | PEQdB Flow
High-performance macOS Parametric EQ with Accelerate-powered real-time FFT analyzer, headroom safety protection, and ad-hoc preset sharing for audiophile setups.

PEQdB Flow is a professional grade Parametric Equalizer (PEQ) and real time audio visualization tool for macOS. It features a responsive, clutter free audio engineering interface designed for high performance audio processing with minimal latency and CPU overhead.

It is optimized for high end DACs and IEMs and comes bundled with the AKG EO IG955 (Qudelix/T71 Downmix Setup) configuration.

   

## Features

### Interactive Parametric EQ Editor
Drag and drop EQ handles directly on the graph canvas with snap to octave frequencies and 0 dB gain.

### Logarithmic FFT Visualizer
Real time 32 bin logarithmic spectrum visualizer running at 30 FPS, offloaded from the audio processing thread to eliminate audio dropouts.

### Soft Knee Saturation Limiter
Safe soft clip saturation limiting at 0.9 full scale in the output rendering stage to protect hearing and hardware.

### Headroom Safety and Preamp Auto Fix
Automatic detection of clipping risks if total EQ boost exceeds Preamp headroom, featuring a one click Auto Fix preamp adjustment.

### Dynamic Layout and Theme Support
Glassmorphic, responsive UI panels that adapt to macOS system Light and Dark appearance modes.

### Force Touch Preset Renaming
Rename custom presets directly in the sidebar by pressure clicking (Force Touch) on their names.

### Equalizer APO Integration
Share and import standard 1:1 Equalizer APO .txt configuration strings.

### Keyboard Shortcuts
Spacebar toggles bypass globally when text fields are not focused. Command + T opens the preset import panel.

### Menu Bar Helper
Access loopback controls, bypass EQ, or open the main panel directly from the macOS menu bar.

   

## Prerequisites and Audio Routing

PEQdB Flow captures audio from a virtual loopback device and renders it to a physical audio interface (such as a DAC or headphones).

1. Install a virtual audio driver such as BlackHole (2ch).
2. Set the macOS system audio output to BlackHole 2ch.
3. Open PEQdB Flow and navigate to the Audio Routing tab.
4. Set the Input Device to BlackHole 2ch and the Output Device to your physical interface (e.g., Fosi Audio DS2 or Qudelix 5K).
5. Grant microphone access on first launch to allow loopback capture.

   

## Installation

1. Extract the release package:
   ```bash
   unzip PEQdBFlow.zip
   ```
2. Move the app to the Applications directory:
   ```bash
   mv PEQdBFlow.app /Applications/
   ```

To clear Gatekeeper quarantine attributes for ad hoc signed apps, run:
```bash
xattr  cr /Applications/PEQdBFlow.app
```

   

## Building from Source

To build a production Release version of PEQdB Flow:

### Requirements
  macOS Sonoma (14.0) or later
  Xcode IDE installed in /Applications/Xcode.app
  XcodeGen installed via Homebrew

### Execution
Run the automated build script:
```bash
./build_release.sh
```

This script generates the project file, compiles the Release configuration, performs ad hoc signing, and packages the result in build/Release/PEQdBFlow.zip.
