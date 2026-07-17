# Production Log Dataset Generator

> Turn live LLM traffic into training data.

Ingests from ClickHouse/Kafka, redacts PII with Presidio, applies schema registry with evolution rules, exports to HuggingFace datasets, Parquet, and JSONL.

**Part of [AEGIS](https://github.com/KnigguKniggu-droid/AEGIS)** — Adaptive AI Governance Infrastructure for Cyber-Physical Systems. This subsystem maps to **L3: Multi-Modal Signal Processing** (Sensor fusion + signal conditioning — multi-source ingestion with PII filtering is analogous to analog front-end signal conditioning before digitization.).

---

## Architecture Position

```
AEGIS Layer: L3: Multi-Modal Signal Processing
ECE Mapping: Sensor fusion + signal conditioning — multi-source ingestion with PII filtering is analogous to analog front-end signal conditioning before digitization.
```

This module is one of 15 subsystems in the AEGIS platform. See the [unified architecture](https://github.com/KnigguKniggu-droid/AEGIS#readme) for how all components interconnect.

---

## Features

- Ingests from ClickHouse/Kafka; PII redaction with Microsoft Presidio
- Schema registry (Avro/Protobuf) with evolution rules
- Exports: HuggingFace datasets, Parquet (partitioned), JSONL
- Differential privacy (epsilon=1.0) option for sensitive domains
- Full lineage: every record traces to request_id, model_version, prompt_template

---

## Tech Stack

`Python` | `ClickHouse` | `Presidio` | `Avro/Protobuf` | `HuggingFace Datasets` | `Parquet`

---

## Quick Start

```bash
git clone https://github.com/KnigguKniggu-droid/13-prod-log-dataset-generator.git
cd 13-prod-log-dataset-generator
pip install -e .
```

Run tests:

```bash
pytest tests/ -v
```

---

## Project Structure

```
13_prod_log_dataset_generator/
  src/                  # Core application code
  tests/                # 33 passing tests
  .github/              # CI/CD workflows
  Dockerfile            # Container build
  pyproject.toml        # Package configuration
```

---

## Running in Docker

```bash
docker build -t 13_prod_log_dataset_generator .
docker run -p 8000:8000 13_prod_log_dataset_generator
```

---

## ECE Design Principles

This subsystem is modeled after classical electrical and computer engineering concepts:

> **Sensor fusion + signal conditioning — multi-source ingestion with PII filtering is analogous to analog front-end signal conditioning before digitization.**

The AEGIS platform applies safety-critical engineering principles from integrated circuit design to LLM deployment, ensuring production reliability in autonomous vehicles, power grids, and medical devices.

---

## Related Projects

All 15 AEGIS subsystems:

| # | Project | Layer | ECE Mapping |
|---|---------|-------|-------------|
| 01 | [Model Regression Detection](https://github.com/KnigguKniggu-droid/AEGIS) | L5 | SPC |
| 02 | [LLM Cost Autopilot](https://github.com/KnigguKniggu-droid/AEGIS) | L1 | DVFS |
| 03 | [Failure Forensics](https://github.com/KnigguKniggu-droid/AEGIS) | L4 | BIST+ATPG |
| 04 | [Self-Healing Docs](https://github.com/KnigguKniggu-droid/AEGIS) | L6 | ECO |
| 05 | [Output Arbitration](https://github.com/KnigguKniggu-droid/AEGIS) | L4 | TMR |
| 06 | [Hybrid Search RAG](https://github.com/KnigguKniggu-droid/AEGIS) | L3 | Sensor Fusion |
| 07 | [Semantic Cache](https://github.com/KnigguKniggu-droid/AEGIS) | L2 | CAM |
| 08 | [SQL Guardrails](https://github.com/KnigguKniggu-droid/AEGIS) | L4 | MPU/MMU |
| 09 | [A/B Testing](https://github.com/KnigguKniggu-droid/AEGIS) | L5 | SPRT |
| 10 | [LoRA Pipeline](https://github.com/KnigguKniggu-droid/AEGIS) | L1 | SVD |
| 11 | [API Gateway](https://github.com/KnigguKniggu-droid/AEGIS) | L2 | Token Bucket |
| 12 | [Feature Flags](https://github.com/KnigguKniggu-droid/AEGIS) | L5 | FPGA Reconfig |
| 13 | [Dataset Generator](https://github.com/KnigguKniggu-droid/AEGIS) | L3 | Signal Conditioning |
| 14 | [Workflow Orchestrator](https://github.com/KnigguKniggu-droid/AEGIS) | L6 | FSM Sequencer |
| 15 | [LLM Observability](https://github.com/KnigguKniggu-droid/AEGIS) | L7 | Oscilloscope+SA |

---

## License

MIT
