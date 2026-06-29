# Changelog

## v0.1.4 - 2026-06-29

- Fixed a memory leak introduced in v0.1.3 that could cause OOM failures during long-running sessions.

## v0.1.3 - 2026-06-29

- Improved stability and utilization for multi-GPU mining rigs.
- Further reduced CPU usage to improve hashrate drops in containers and low-end machines.
- Reduced per-GPU VRAM usage, saving about `1.25GB` per GPU under the default configuration.
- Optimized startup and job-switching performance to reduce stalls and improve overall hashrate.
- Improved hashrate stability during long-running sessions.
- Added clearer pool difficulty information in logs.

## v0.1.2 - 2026-06-27

- Fixed hashrate performance loss in some cloud-platform Docker environments where providers apply CPU throttling.
- If you do not experience performance issues, you can continue using v0.1.1.

## v0.1.1 - 2026-06-22

- Fixed share submission failures caused by unstable network connections.

## v0.1.0 - 2026-06-18

Initial release of `six-pearl-miner`, a Pearl GPU miner developed by 6block.

### Performance

| Architecture | GPU | Min Compute Capability | Typical Hashrate (single GPU) |
|---|---|---|---|
| Ampere | RTX 3080 | sm_86 | ~104 TH/s |
| Ampere | RTX 3090 | sm_86 | ~115 TH/s |
| Ada | RTX 4090 | sm_89 | ~280 TH/s |
| Hopper | H100 | sm_90 | ~680 TH/s |

> Actual hashrate varies by GPU clock, power limit, cooling, and pool difficulty. Expect ±5% fluctuation.

### Features

- Supports NVIDIA 30-series and newer GPUs (Ampere / Ada / Hopper).
- Connects to mining pools via the Stratum protocol.
- Embeds all CUDA kernels in a single binary; no extra files are required.
- Supports Fortune Pool with explicit `--protocol fortune` configuration.
- Supports Lucky Pool endpoints in Europe, Hong Kong, Russia, Singapore, and the United States.
- Provides documentation in Chinese, English, and Russian.
