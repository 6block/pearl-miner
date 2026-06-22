# Changelog

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
