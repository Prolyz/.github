# Prolyz

**Your company's Decision Brain**

Prolyz is an enterprise decision intelligence platform. One governed product covers the whole path
from source systems to a decision: real-time change data capture, a catalog with column-level
lineage, built-in OLAP analytics and causal AI. It can run as SaaS or entirely inside your own
environment, including air-gapped.

Most analytics stacks answer *what happened*. The question that costs money is *why*, and a SQL
engine is not the tool that answers it. Prolyz is built around that gap.

🌐 **[prolyz.com](https://prolyz.com)** · 📖 **[Docs](https://docs.prolyz.com)** · ✍️ **[Blog](https://prolyz.com/blog)**

---

## The four layers

| Layer | What it does |
|---|---|
| **Sync** | Log-based CDC, streaming and incremental pipelines, schema-drift handling, 50+ connectors for databases, ERP, CRM, SaaS apps, APIs and files |
| **Data** | Catalog with column-level lineage, metadata management, quality scoring and quarantine, PII tokenization, audit trail, data products |
| **Report** | Analytics on a built-in ClickHouse OLAP engine, real-time dashboards, ML forecasting, trend and anomaly detection, with no separate warehouse to run |
| **Agent** | Causal inference over your metrics, what-if simulation, recommendations, and a root-cause agent for pipeline failures |

Each layer is independently deployable and communicates over an event bus.

---

## How it is built

- **Services**: .NET 8 microservices behind a YARP API gateway, OAuth2/OIDC via OpenIddict,
  MassTransit event bus with idempotent consumers
- **Data path**: PostgreSQL 16 as the operational source of truth (row-level security, partitioning)
  → WAL change data capture → ClickHouse for analytical workloads; Redis for cache and sessions
- **AI**: a local open-weight LLM by default (Qwen3 served with Ollama or vLLM), causal inference with
  DoWhy, long-horizon forecasting with Chronos-2, and retrieval over governed assets. Agent actions go
  through a contract with dry-run by default, signed human approval and an audit log. By default,
  reasoning over customer data stays inside the customer's environment
- **Tenancy**: isolation at four levels: application, database, physical and resource quota
- **Observability**: OpenTelemetry into Prometheus, Tempo, Loki and Grafana
- **Deployment**: SaaS, hybrid, fully on-premises, or air-gapped

---

## Writing

Technical pieces on data architecture, causal inference, local AI and governance, including honest
comparisons with the tools people evaluate us against.

- [Decision intelligence platforms in 2026: a buyer's guide](https://prolyz.com/blog/decision-intelligence-platforms-2026-buyers-guide)
- [Fivetran alternatives in 2026: when you need more than pipelines](https://prolyz.com/blog/fivetran-alternatives-2026-catalog-olap-causal-ai)
- [MCP goes stateless: the 2026-07-28 spec and the approval gate data agents need](https://prolyz.com/blog/mcp-2026-07-28-spec-stateless-approval-gate)
- [Choosing an on-premise LLM in late 2026: the licence check](https://prolyz.com/blog/on-prem-llm-q4-2026-qwen-deepseek-license-checklist)
- [TimesFM-3 vs Chronos-2: choosing a forecasting foundation model](https://prolyz.com/blog/timesfm-3-vs-chronos-2-demand-forecasting)
- [Column-level lineage: why table lineage is not enough](https://prolyz.com/blog/column-level-lineage-impact-analysis)

**Comparisons:** [Fivetran](https://prolyz.com/blog/prolyz-vs-fivetran) ·
[Airbyte](https://prolyz.com/blog/prolyz-vs-airbyte) ·
[Informatica](https://prolyz.com/blog/prolyz-vs-informatica) ·
[dbt](https://prolyz.com/blog/prolyz-vs-dbt) ·
[Snowflake](https://prolyz.com/blog/prolyz-vs-snowflake) ·
[Power BI & Fabric](https://prolyz.com/blog/prolyz-vs-power-bi-microsoft-fabric) ·
[Cognite](https://prolyz.com/blog/prolyz-vs-cognite)

[All posts →](https://prolyz.com/blog)

---

## Repositories

Prolyz product repositories are private. This organization is public for identity and contact.

---

## Find us

**Prolyz Ltd**, London, United Kingdom · Company No. 17386364

- Web: [prolyz.com](https://prolyz.com) · Email: [hello@prolyz.com](mailto:hello@prolyz.com)
- [LinkedIn](https://www.linkedin.com/company/prolyz) · [X](https://x.com/prolyz) ·
  [G2](https://www.g2.com/products/prolyz/reviews) · [Capterra](https://www.capterra.com/p/10182050/Prolyz/) ·
  [Crunchbase](https://www.crunchbase.com/organization/prolyz) · [Product Hunt](https://www.producthunt.com/products/prolyz) ·
  [Trustpilot](https://www.trustpilot.com/review/prolyz.com)
