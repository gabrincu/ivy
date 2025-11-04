# 🌿 Ivy Roadmap

> **Project Goal:**  
> Ivy is an open-source **scalable data acquisition framework** built in Python — designed for **targeted, reliable, and large-scale web scraping**.  
> It enables enterprises and developers to build, manage, and monitor hundreds of scrapers efficiently, with first-class observability, scheduling, and extensibility.
> It also spreads around like an ivy.

---

## 🧭 Vision

Ivy aims to provide:
- A **modular and pluggable** scraping framework — combining YAML-based declarative scrapers and Python SDKs.  
- **Scalable execution** across distributed workers.  
- **Enterprise-grade observability**, governance, and data quality management.  
- **Developer delight** — through elegant APIs, CI integration, and local debugging tools.

---

## 🗓️ Timeline Overview

| Phase | Duration | Milestone | Focus |
|--------|-----------|-----------|--------|
| **Phase 1** | Months 0–2 | **v0.1 — Core SDK & Local Runner** | Local SDK, CLI, YAML scraper engine, logging, and CI |
| **Phase 2** | Months 3–5 | **v0.2 — Distributed Execution** | Worker orchestration, queues, S3 storage, Prometheus metrics |
| **Phase 3** | Months 6–8 | **v0.3 — Scraper Management Platform** | Web dashboard, schema registry, Git integration |
| **Phase 4** | Months 9–12 | **v1.0 — Enterprise Ivy** | Multi-tenancy, secrets, proxy pool, plugin SDK, RBAC |

---

## 🧩 Phase 1 — Core SDK & Local Runner (v0.1)

**Timeline:** Month 0–2  
**Goal:** Make Ivy usable locally for building and running scrapers.

### Deliverables
- **Core SDK (`ivy_core`)** with async architecture  
- **Declarative YAML scraper engine**  
- **CLI (`ivy_cli`)** with commands: `init`, `run`, `list`  
- **Structured logging and configuration system**  
- **Local scheduler** (cron-like)  
- **JSONL item output**  
- **CI/CD pipeline** with linting, tests, and pre-commit  
- **Developer documentation**

### Success Criteria
- Developers can `ivy init` and `ivy run` a scraper locally  
- Example scraper runs end-to-end  
- CI/CD green, coverage ≥80%  
- Docs published via GitHub Pages  

---

## ⚙️ Phase 2 — Distributed Execution (v0.2)

**Timeline:** Month 3–5  
**Goal:** Run scrapers at scale across distributed workers.

### Deliverables
- **Job queue** using Redis Streams or Kafka  
- **Worker service** (`ivy_worker`) for distributed execution  
- **Artifact storage** abstraction (S3 / MinIO)  
- **Schema registry** for datasets  
- **Basic observability stack:**  
  - Prometheus metrics  
  - Grafana dashboards  
  - Structured logs
- **Docker & Helm templates** for K8s deployment  

### Success Criteria
- Scrapers can be scheduled and executed via multiple workers  
- Metrics available at `/metrics` endpoint  
- Job retries, throttling, and error handling working  
- End-to-end integration tests passing  

---

## 🧠 Phase 3 — Scraper Management Platform (v0.3)

**Timeline:** Month 6–8  
**Goal:** Build a developer-friendly management layer and UI.

### Deliverables
- **Ivy Web Dashboard** (FastAPI + React)
- **Scraper registry and Git integration**
- **Job monitoring & logs UI**
- **Template library** (listing → detail scrapers)
- **API authentication (API keys / OAuth)**
- **Connectors for Postgres, S3, and ClickHouse**
- **Data catalog** with schema validation and samples

### Success Criteria
- Users can browse scrapers, view runs, inspect logs  
- Git-based scraper versioning enabled  
- Schema registry validating items  
- Frontend and API integrated  

---

## 🏢 Phase 4 — Enterprise Ivy (v1.0)

**Timeline:** Month 9–12  
**Goal:** Enterprise-ready scalability, governance, and extensibility.

### Deliverables
- **Multi-tenancy & RBAC**
- **Secrets management (Vault integration)**
- **Proxy pool management & anti-bot plugins**
- **Incremental crawling + deduplication**
- **Alerting & SLO dashboards**
- **Plugin SDK for custom fetchers, renderers, sinks**
- **Audit logs & governance framework**
- **Enterprise deployment docs (Helm, Terraform)**

### Success Criteria
- Ivy supports large-scale, multi-tenant scraping  
- Stable plugin API  
- Alerting and SLA metrics implemented  
- Compliance and data governance features validated  

---

## 🧰 Technical Stack Summary

| Layer | Technology | Purpose |
|--------|-------------|----------|
| **Language** | Python 3.11+ | Core SDK and services |
| **Async HTTP** | `httpx`, `aiohttp` | Non-blocking requests |
| **Rendering** | `playwright` | Headless browser scraping |
| **Task Queue** | `aiokafka` / `arq` | Job scheduling |
| **Storage** | S3 / MinIO, Postgres, ClickHouse | Artifacts, metadata, data warehouse |
| **Schema & Config** | `pydantic`, `jsonschema`, `dynaconf` | Validation and configuration |
| **CLI & Logging** | `typer`, `structlog`, `rich` | Developer tools and logs |
| **Testing** | `pytest`, `pytest-asyncio` | Unit/integration tests |
| **Observability** | `prometheus_client`, Grafana | Metrics |
| **Docs** | `mkdocs-material` | Developer documentation |
| **DevOps** | GitHub Actions, Docker, Helm | CI/CD and deployment |

---

---

## 🧩 Long-Term Ideas (Post v1.0)

| Feature | Description |
|----------|--------------|
| 🌐 Webhooks / Streaming | Real-time data emission to Kafka or WebSocket |
| 🧬 ML-Assisted Extraction | ML-based content extraction from structured layouts |
| 🔄 Self-Healing Scrapers | Detect and auto-fix selector changes |
| 📊 Data Quality Dashboard | Metrics for freshness, completeness, and change tracking |
| ☁️ Managed Ivy Cloud | Hosted enterprise offering |
| 🧰 SDK Plugins Marketplace | Community-driven plugin & scraper repository |

---

## 🏁 Contribution Goals

- **Open Source First:** Apache License 2.0 gives us transparency and keeps everything open, transparent roadmap, and public backlog.  
- **Community Driven:** Encourage plugin and scraper contributions.  
- **Reliable Core:** Automated tests, code coverage, and stable APIs.  
- **Enterprise Friendly:** RBAC, observability, compliance baked in.

---

## 📚 Resources

- [Contributing Guide](CONTRIBUTING.md)  
- [GitHub Project Board](https://github.com/gabrincu/ivy/projects)  
- [Issue Tracker](https://github.com/gabrincu/ivy/issues)
