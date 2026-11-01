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
- **Radar-to-camera calibration:** calibrated the radar to the RGB camera so radar detections line up with the image. Fitted on 22 calibration points and checked on 6 held-out points.
- **Pose initialization:** worked on the system's pose initialization.
- **Radar test suite:** researched the radar output, defined test requirements and directed Claude (AI) to write pytest tests, including replay on recorded sensor data.
- **Team coordination:** coordinated the team's tasks from June until the final.
- Also assisted with the team's AI object detection model.

## Tech Stack

Python · C · Linux · NVIDIA Jetson · OpenMV N6 · pytest · sensor fusion · computer vision

## Team

Developed by a team of 6 as part of the MAFAT B.U.I.L.D Competition.
