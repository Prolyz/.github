# Prolyz

**Built for decisions, not dashboards.**

Prolyz is an enterprise data platform that covers the whole path from source systems to a decision:
ingestion, governance, analytics and causal reasoning in one governed product, deployable inside
your own environment.

Most analytics stacks answer *what happened*. The question that costs money is *why*, and a SQL
engine is not the tool that answers it. Prolyz is built around that gap.

🌐 **[prolyz.com](https://prolyz.com)** · 📖 **[Engineering blog](https://prolyz.com/blog)**

---

## The four layers

| Layer | What it does |
|---|---|
| **Data** | Catalog every asset with column-level lineage, quality scoring, quarantine and domain ownership |
| **Sync** | Log-based CDC and ETL across 50+ connectors, multi-target routing |
| **Report** | Analytics on a built-in ClickHouse OLAP engine — no separate warehouse to provision |
| **Agent** | Causal inference over your metrics: not that a number moved, but what plausibly moved it |

Each layer is independently deployable and communicates over an event bus.

---

## How it is built

- **Services** — .NET 8 microservices behind a YARP API gateway, OAuth2/OIDC via OpenIddict,
  MassTransit event bus with idempotent consumers
- **Data path** — PostgreSQL 16 as the operational source of truth (row-level security, partitioning)
  → WAL change data capture → ClickHouse for analytical workloads; Redis for cache and sessions
- **AI** — causal inference with Pearl/DoWhy, forecasting, and retrieval over governed assets.
  **Models run locally.** Reasoning over customer data happens inside the customer's environment;
  neither data nor metadata leaves it, and no external model provider ever sees it.
- **Tenancy** — isolation at four levels: application, database, physical and resource quota
- **Observability** — OpenTelemetry into Prometheus, Tempo, Loki and Grafana
- **Deployment** — SaaS, hybrid, fully on-premises, or air-gapped

---

## Writing

We publish technical pieces on data architecture, causal inference and governance — including honest
comparisons with the tools people evaluate us against.

- [ETL and ELT: why the order of operations still matters](https://prolyz.com/blog/etl-vs-elt-order-of-operations)
- [Column-level lineage: why table lineage is not enough](https://prolyz.com/blog/column-level-lineage-impact-analysis)
- [Schema drift: the outage that never pages anyone](https://prolyz.com/blog/data-contracts-schema-drift)
- [The metric moved: correlation, causation and what to do on Monday](https://prolyz.com/blog/correlation-vs-causation-metrics)
- [RAG or fine-tuning: the wrong question for enterprise data agents](https://prolyz.com/blog/rag-vs-fine-tuning-enterprise-data-agents)

[All posts →](https://prolyz.com/blog)

---

## Repositories

Prolyz product repositories are private. This organization is public for identity and contact only.

---

## Contact

**Prolyz Ltd** — London, United Kingdom · Company No. 17386364

- Web — [prolyz.com](https://prolyz.com)
- Email — [hello@prolyz.com](mailto:hello@prolyz.com)
- LinkedIn — [linkedin.com/company/prolyz](https://www.linkedin.com/company/prolyz)
