# Sekai OCR Vision Panel

This project mirrors the AI status overlay used in our shooter prototypes, but tailored for real-world webcam telemetry. No live video is rendered in the DOM; instead, we extract lightweight metrics and present them as OCR-friendly text.

## Features
- **AI Status Panel (H / E / S / EV)**: 150×100px canvas with black background + white monospace text. Updated every 300 ms.
- **Ambient Window**: Running percentage of mean brightness plus min/max window.
- **Contrast & Motion**: Standard deviation (σ) of brightness and delta-based motion score (0–999).
- **Color Bias**: Per-channel averages and a coarse “Warm/Green/Cool/Neutral” tilt indicator.
- **Non-visual processing**: Video frames stay hidden; only numeric data is exposed for downstream Vision-AI pipelines.

## Getting Started
1. Serve `index.html` via any static HTTP server or open it directly in a modern browser (Chrome/Edge recommended).
2. Allow webcam access when prompted. The stream runs off-screen and will not be shown to the user.
3. Watch the AI panel + metric cards update in real time. `statusLog` prints the latest acquisition / error messages.

## H/E/S/EV Codes
- **H**: Ambient light percentage (zero-padded). Computed from average frame brightness.
- **E**: `width×height` (truncated to 6 chars) plus motion score.
- **S**: Stream phase (`REQ`, `CAP`, `ERR`).
- **EV**:
  - `10` nominal
  - `30` high light
  - `40` low light
  - `55` high contrast
  - `60` heavy motion
  - `90` error

## Architecture Notes
- Sampling resolution is clamped to 160×120 per frame to keep CPU usage low.
- All computations use Canvas 2D pixel data; no external ML models are involved.
- The status panel shares its format with other Vision-AI “watcher” modules, so OCR scripts can be reused without changes.

Feel free to extend `sampleFrame()` with additional heuristics (edge density, face count, etc.) as long as the panel stays minimal and deterministic.
