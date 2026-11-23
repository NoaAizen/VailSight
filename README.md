# VailSight – Multi-Sensor Perception & Navigation System

🏆 One of 3 winning projects (out of 64 teams) in the MAFAT B.U.I.L.D Competition, September 2026

VailSight is a team-built perception and navigation system that fuses data from several sensors: mmWave radar, IMU, thermal camera and RGB camera. It runs on NVIDIA Jetson and OpenMV N6 hardware.

Built by a 6-person team, June – September 2026.

## System Overview

| Component | Details |
|---|---|
| Radar | TI IWR1843 mmWave radar |
| Motion | IMU |
| Cameras | Thermal camera, RGB camera |
| Compute | NVIDIA Jetson, OpenMV N6 |
| Software | Python, C, Linux |

The sensor data is synchronized on one shared clock and passed to the team's fusion, tracking and navigation code.

## My Role – Noa Aizen

I owned the sensor integration layer: getting the radar, IMU and thermal data onto the Jetson, synchronized and ready for the rest of the team.

- **Sensor integration and synchronization:** brought radar data onto the NVIDIA Jetson and aligned radar, IMU and thermal data on one shared clock, including timestamp handling.
- **Sensor API and recording tools:** built an API and recording tools that teammates used for their fusion and navigation code.
- **Radar-to-camera calibration:** ran the radar-to-RGB calibration session (calibration tools built by a teammate) and recorded the calibration data: 22 fit points and 6 held-out points.
- **Pose initialization:** worked on the system's pose initialization.
- **Radar test suite:** researched the radar output, defined test requirements and directed Claude (AI) to write pytest tests, including replay on recorded sensor data.
- **Team coordination:** coordinated the team's tasks from June until the final.
- Also assisted with the team's AI object detection model.

## Where to Find My Code

The `main` branch contains this overview only. My code lives in the feature branches:

- **Jetson bridge receiver (C):** [bridge/bridge_rx.c](https://github.com/NoaAizen/VailSight/blob/1c4bbc873dac1f58f59490c825fa88f4b29c64e7/bridge/bridge_rx.c). Reassembles framed thermal, RGB and IMU records from the N6 board, verifies CRC and resyncs after errors. Live-verified on 18.8.2026: 190 s with 0 lost records (thermal and RGB at 8.6 Hz, IMU at 200 Hz).
- **Bridge protocol:** [bridge/bridge_protocol.h](https://github.com/NoaAizen/VailSight/blob/1c4bbc873dac1f58f59490c825fa88f4b29c64e7/bridge/bridge_protocol.h)
- **Radar replay tool:** [board/mmwave/replay.py](https://github.com/NoaAizen/VailSight/blob/1c4bbc873dac1f58f59490c825fa88f4b29c64e7/board/mmwave/replay.py)
- **Sensor API for teammates:** `yael_api/` on the `IMU` branch
- **Radar tests (72 pytest tests):** [tests/mmwave](https://github.com/NoaAizen/VailSight/tree/1c4bbc873dac1f58f59490c825fa88f4b29c64e7/tests/mmwave)

## Tech Stack

Python · C · Linux · NVIDIA Jetson · OpenMV N6 · pytest · sensor fusion · computer vision

## Team

Developed by a team of 6 as part of the MAFAT B.U.I.L.D Competition.
