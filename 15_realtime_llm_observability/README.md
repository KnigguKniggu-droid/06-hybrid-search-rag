# Real-time LLM Observability

> Real-time LLM observability with token streaming and drift detection.

Token streaming via WebSocket, P95/P99 latency tracking per model/tenant, cost tracking per request, anomaly detection on embedding drift.

**Part of [AEGIS](https://github.com/KnigguKniggu-droid/AEGIS)** — Adaptive AI Governance Infrastructure for Cyber-Physical Systems. This subsystem maps to **L7: Instrument Panel** (Real-time oscilloscope + spectrum analyzer — WebSocket streaming with TTFB/ITL/TTFT, P50/P95/P99 percentiles, token drift anomaly detection.).

---

## Architecture Position

```
AEGIS Layer: L7: Instrument Panel
ECE Mapping: Real-time oscilloscope + spectrum analyzer — WebSocket streaming with TTFB/ITL/TTFT, P50/P95/P99 percentiles, token drift anomaly detection.
```

This module is one of 15 subsystems in the AEGIS platform. See the [unified architecture](https://github.com/KnigguKniggu-droid/AEGIS#readme) for how all components interconnect.

---

## Features

- Token streaming via WebSocket; live token-by-token dashboard
- P95/P99 latency per model/tenant/endpoint with percentile aggregation
- Cost tracking per request (input/output tokens x model pricing)
- Anomaly detection on embedding drift (cosine shift > threshold)
- ClickHouse for analytics, Redis for hot data, Grafana for viz

---

## Tech Stack

`Python` | `ClickHouse` | `Redis` | `Grafana` | `OpenTelemetry` | `WebSocket` | `Streaming` | `Anomaly Detection`

---

## Quick Start

```bash
git clone https://github.com/KnigguKniggu-droid/15-realtime-llm-observability.git
cd 15-realtime-llm-observability
pip install -e .
```

Run tests:

```bash
pytest tests/ -v
```

---

## Project Structure

```
15_realtime_llm_observability/
  src/                  # Core application code
  tests/                # 43 passing tests
  .github/              # CI/CD workflows
  Dockerfile            # Container build
  pyproject.toml        # Package configuration
```

---

## Running in Docker

```bash
docker build -t 15_realtime_llm_observability .
docker run -p 8000:8000 15_realtime_llm_observability
```

---

## ECE Design Principles

This subsystem is modeled after classical electrical and computer engineering concepts:

> **Real-time oscilloscope + spectrum analyzer — WebSocket streaming with TTFB/ITL/TTFT, P50/P95/P99 percentiles, token drift anomaly detection.**

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
