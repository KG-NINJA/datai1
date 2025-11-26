# Sekai OCR Vision Panel

This project mirrors the AI status overlay used in our shooter prototypes, but tailored for real-world webcam telemetry. No live video is rendered; instead, lightweight metrics are presented as OCR‑friendly text.

## Features
- **AI Status Panel (H / E / S / EV)**: 150×100px, black background + white monospace text, updated every 300 ms.
- **Ambient Window**: Mean brightness with min/max.
- **Contrast & Motion**: Standard deviation and delta‑based motion score.
- **Color Bias**: Per‑channel averages with coarse bias detection.
- **Non‑visual processing**: Frames stay hidden; only stats exposed.

## Getting Started
1. Serve `index.html` via any static HTTP server or open directly.
2. Allow webcam access.
3. Monitor the real‑time AI panel and metrics.

## H/E/S/EV Codes
- **H**: Ambient light percentage.
- **E**: Resolution + motion.
- **S**: Stream phase.
- **EV**: Environment code.

## Architecture Notes
- Sampling at 160×120.
- Canvas 2D pixel processing.
- Deterministic OCR‑friendly panel.

## Neural Substrate Model (脳神経モデルとしての説明)
Each smartphone/browser acts as a **neuron‑like sensory cell**, emitting structured signals (H/E/S/EV).  
- Neuron = Smartphone  
- Membrane Potential = Telemetry  
- Spike = Motion/Contrast Event  
- Axon = Network channel  
- Synapse = AI gateway  

## Urban‑Scale Robotics (都市全体をロボット化)
This system is a precursor to a **city‑as‑a‑robot** design:
1. Perception  
2. Integration  
3. Planning  
4. Action  
5. Feedback  

## datai1 は始まりにすぎない
dataai1 provides the first stable signal vocabulary and sensory abstraction.
