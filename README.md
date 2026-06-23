# six-pearl-miner — Pearl GPU miner

[中文](#中文) | [English](#english) | [Русский](#русский)

---

## 中文

### 简介

`six-pearl-miner` 是由 6block 开发的 Pearl GPU 矿工程序，支持 NVIDIA 30 系列及以上显卡（Ampere / Ada / Hopper）。程序通过 Stratum 协议连接矿池，单二进制内嵌所有 CUDA kernel，无需额外文件。

### 硬件要求

| GPU 架构 | 系列 | 最低 Compute Capability | 典型算力（单卡） |
|---|---|---|---|
| Ampere | RTX 3080 | sm_86 | ~104 TH/s |
| Ampere | RTX 3090 | sm_86 | ~115 TH/s |
| Ada | RTX 4090 | sm_89 | ~280 TH/s |
| Hopper | H100 | sm_90 | ~680 TH/s |

> 实际算力受 GPU 频率、功耗墙、散热及矿池难度影响，存在 ±5% 波动。

### 支持的矿池

#### Fortune Pool

| 节点 | 地址 | 端口 |
|---|---|---|
| 新加坡 | `global.pearlfortune.org` | 8888 |

Fortune Pool 使用 SRB/HeroMiners 风格的下行协议，需显式指定 `--protocol fortune`。

启动命令：

```bash
./six-pearl-miner \
  --pool global.pearlfortune.org:8888 \
  --protocol fortune \
  --wallet <你的 Pearl 地址>.<矿工名>
```

示例：

```bash
./six-pearl-miner \
  --pool global.pearlfortune.org:8888 \
  --protocol fortune \
  --wallet prl1pnjxxxxxxxxxxxxxxxxxxxx.rig
```

#### HiveOS

```json
{
    "name": "pearl - 6block",
    "isFavorite": false,
    "items": [
        {
            "coin": "PEARL",
            "pool_ssl": false,
            "dpool_ssl": false,
            "miner": "custom",
            "miner_alt": "six-pearl",
            "miner_config": {
                "url": "global.pearlfortune.org:8888",
                "miner": "six-pearl",
                "template": "%WAL%.%WORKER_NAME%",
                "install_url": "https://github.com/6block/pearl-miner/releases/download/v0.1.1/six-pearl-0.1.1.tar.gz",
                "user_config": "--protocol fortune"
            },
            "pool_geo": []
        }
    ]
}
```

#### Lucky Pool

| 节点 | 地址 | 端口 |
|---|---|---|
| 欧洲 | `pearl-eu.lproute.com` | 3365 |
| 香港 | `pearl-hk.lproute.com` | 3365 |
| 俄罗斯 | `pearl-ru.lproute.com` | 3365 |
| 新加坡 | `pearl-sg.lproute.com` | 3365 |
| 美国 | `pearl-us.lproute.com` | 3365 |

启动命令：

```bash
./six-pearl-miner \
  --pool pearl-hk.lproute.com:3365 \
  --wallet <你的 Pearl 地址>.<矿工名>
```

示例：

```bash
./six-pearl-miner \
  --pool pearl-hk.lproute.com:3365 \
  --wallet prl1pnjxxxxxxxxxxxxxxxxxxxx.rig1
```

---

## English

### Overview

`six-pearl-miner` is a Pearl GPU miner developed by 6block. It supports NVIDIA
30-series and newer GPUs (Ampere / Ada / Hopper). The miner connects to pools
via the Stratum protocol. All CUDA kernels are embedded in a single binary —
no extra files needed.

### Hardware Requirements

| Architecture | GPU | Min Compute Capability | Typical Hashrate (single GPU) |
|---|---|---|---|
| Ampere | RTX 3080 | sm_86 | ~104 TH/s |
| Ampere | RTX 3090 | sm_86 | ~115 TH/s |
| Ada | RTX 4090 | sm_89 | ~280 TH/s |
| Hopper | H100 | sm_90 | ~680 TH/s |

> Actual hashrate varies by GPU clock, power limit, cooling, and pool
> difficulty. Expect ±5% fluctuation.

### Supported Pools

#### Fortune Pool

| Location | Address | Port |
|---|---|---|
| Singapore | `global.pearlfortune.org` | 8888 |

Fortune Pool uses an SRB/HeroMiners-style downstream protocol. You must specify
`--protocol fortune`.

Command:

```bash
./six-pearl-miner \
  --pool global.pearlfortune.org:8888 \
  --protocol fortune \
  --wallet <your Pearl address>.<worker>
```

Example:

```bash
./six-pearl-miner \
  --pool global.pearlfortune.org:8888 \
  --protocol fortune \
  --wallet prl1pnjsqalxxxxxxxxxxxxx.rig
```

#### Lucky Pool

| Location | Address | Port |
|---|---|---|
| Europe | `pearl-eu.lproute.com` | 3365 |
| Hong Kong | `pearl-hk.lproute.com` | 3365 |
| Russia | `pearl-ru.lproute.com` | 3365 |
| Singapore | `pearl-sg.lproute.com` | 3365 |
| United States | `pearl-us.lproute.com` | 3365 |

Command:

```bash
./six-pearl-miner \
  --pool pearl-hk.lproute.com:3365 \
  --wallet <your Pearl address>.<worker>
```

Example:

```bash
./six-pearl-miner \
  --pool pearl-hk.lproute.com:3365 \
  --wallet prl1pnjsqalse3pxxxxxxxxxxxx.rig1 \
  2>&1 | tee lucky-pool.log
```

---

## Русский

### Обзор

`six-pearl-miner` — GPU-майнер Pearl, разработанный 6block. Поддерживает видеокарты NVIDIA 30-й серии и новее (Ampere / Ada / Hopper). Майнер подключается к пулам через протокол Stratum. Все CUDA kernel встроены в один бинарный файл — дополнительные файлы не требуются.

### Требования к оборудованию

| Архитектура | GPU | Минимальная Compute Capability | Типичный хешрейт (одна GPU) |
|---|---|---|---|
| Ampere | RTX 3080 | sm_86 | ~104 TH/s |
| Ampere | RTX 3090 | sm_86 | ~115 TH/s |
| Ada | RTX 4090 | sm_89 | ~280 TH/s |
| Hopper | H100 | sm_90 | ~680 TH/s |

> Фактический хешрейт зависит от частоты GPU, лимита мощности, охлаждения и сложности пула. Возможны колебания около ±5%.

### Поддерживаемые пулы

#### Fortune Pool

| Локация | Адрес | Порт |
|---|---|---|
| Сингапур | `global.pearlfortune.org` | 8888 |

Fortune Pool использует downstream-протокол в стиле SRB/HeroMiners. Необходимо явно указать `--protocol fortune`.

Команда запуска:

```bash
./six-pearl-miner \
  --pool global.pearlfortune.org:8888 \
  --protocol fortune \
  --wallet <ваш Pearl адрес>.<воркер>
```

Пример:

```bash
./six-pearl-miner \
  --pool global.pearlfortune.org:8888 \
  --protocol fortune \
  --wallet prl1pnjxxxxxxxxxxxxxxxxxxxx.rig
```

#### Lucky Pool

| Локация | Адрес | Порт |
|---|---|---|
| Европа | `pearl-eu.lproute.com` | 3365 |
| Гонконг | `pearl-hk.lproute.com` | 3365 |
| Россия | `pearl-ru.lproute.com` | 3365 |
| Сингапур | `pearl-sg.lproute.com` | 3365 |
| США | `pearl-us.lproute.com` | 3365 |

Команда запуска:

```bash
./six-pearl-miner \
  --pool pearl-ru.lproute.com:3365 \
  --wallet <ваш Pearl адрес>.<воркер>
```

Пример:

```bash
./six-pearl-miner \
  --pool pearl-ru.lproute.com:3365 \
  --wallet prl1pnjxxxxxxxxxxxxxxxxxxxx.rig1
```
