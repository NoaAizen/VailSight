# VailSight – Multi-Sensor Perception & Navigation System

🏆 One of 3 winning projects (out of 64 teams) in the MAFAT B.U.I.L.D Competition, September 2026

VailSight is a team-built perception and navigation system that fuses data from several sensors: mmWave radar, IMU, thermal camera and RGB camera. It runs on NVIDIA Jetson and OpenMV N6 hardware.

## System Overview

| Component | Details |
|---|---|
| Radar | TI IWR1843 mmWave radar |
| Motion | IMU |
| Cameras | Thermal camera, RGB camera |
| Compute | NVIDIA Jetson, OpenMV N6 |
| Software | Python, C, Linux |

The sensor data is synchronized on one shared clock and passed to the team's fusion, tracking and navigation code.

## Tech Stack

Python · C · Linux · NVIDIA Jetson · OpenMV N6 · pytest · sensor fusion · computer vision

## Team

Developed as a team project in the MAFAT B.U.I.L.D Competition.
