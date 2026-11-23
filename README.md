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

## Key Commits – Noa Aizen

Noa Aizen's code lives in several feature branches. Each link below opens the commit directly:

**Radar (stage-1 bring-up and audit)**
- [`09de73e`](https://github.com/NoaAizen/VailSight/commit/09de73ec87fd7d7307ebcf721cb70a35754152d1) (09.08.2026) Stage-1 mmWave radar bring-up code
- [`943e7fc`](https://github.com/NoaAizen/VailSight/commit/943e7fcf265c1aacccdd7382a0c133aae14c366e) (09.08.2026) Radar audit follow-ups: cfg reconciliation, parser padding fix, tests
- [`fbe49c7`](https://github.com/NoaAizen/VailSight/commit/fbe49c7bb4ec57f33c42a7b730f39a7f22c834fb) (09.08.2026) Aliasing walk recording as a test and replay fixture

**N6 → Jetson bridge (C receiver, Python sender)**
- [`3544413`](https://github.com/NoaAizen/VailSight/commit/35444139e946d7edd5959400d8d2e92b3c017553) (17.08.2026) N6→Jetson bridge and IMU infrastructure
- [`f92f08b`](https://github.com/NoaAizen/VailSight/commit/f92f08b371234d2f4bafcfaf26c8240f199b42fe) (17.08.2026) Live-verified on N6 + Jetson, with fixes found in the live run
- [`c6c8cea`](https://github.com/NoaAizen/VailSight/commit/c6c8cea0abe4fa989810532554b4d1609a1fdb8a) (17.08.2026) Zero-copy sender: found and fixed the root cause of a ~4 s stall
- [`baba57d`](https://github.com/NoaAizen/VailSight/commit/baba57d7ea2e8e5b5805f6afaaeaab991f30ca95) (18.08.2026) IMU sampling raised from 148 to 200 Hz; live-verified 190 s with 0 loss
- [`171beac`](https://github.com/NoaAizen/VailSight/commit/171beac4d38c682f1e6b39ba8767ec48121c7072) (18.08.2026) Thermal camera FFC flag read from the Lepton image flags
- [`e30ee4d`](https://github.com/NoaAizen/VailSight/commit/e30ee4df682a618f49a6c8abfee97be1ad9b196a) (18.08.2026) First real IMU recording: 8 static holds, 3 orientations

**Sensor API and recording tools**
- [`da7c9cc`](https://github.com/NoaAizen/VailSight/commit/da7c9cca42119de03635410c3b64892e6e3b5651) (18.08.2026) Sensor API: every call from the teammate's requirements doc, on one shared clock
- [`c179e25`](https://github.com/NoaAizen/VailSight/commit/c179e259b420abaf5c37f5be18ef017650922049) (25.08.2026) Radar detection recorder from the real radar
- [`0cc937c`](https://github.com/NoaAizen/VailSight/commit/0cc937c23c584b75e6151984c879a17df6feb159) (25.08.2026) Radar + IMU + thermal recorder on one clock

**Pose initialization and map integration**
- [`9858e61`](https://github.com/NoaAizen/VailSight/commit/9858e6157f4c08546189a92075fc32c12ff39308) (25.08.2026) pose_init v0: position and heading from radar wall returns against footprints
- [`63b4e8d`](https://github.com/NoaAizen/VailSight/commit/63b4e8d87e75efc1d4d5be3d3847e285b693e73e) (25.08.2026) Position-from-walls views in the live viewer
- [`44d9e8f`](https://github.com/NoaAizen/VailSight/commit/44d9e8f0122fb6dc48505408b4039d38bbbac910) (25.08.2026) Map layer wired into the live system

## Tech Stack

Python · C · Linux · NVIDIA Jetson · OpenMV N6 · pytest · sensor fusion · computer vision

## Team

Developed as a team project in the MAFAT B.U.I.L.D Competition.
