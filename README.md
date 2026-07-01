<!-- ═══════════════════════════════════════════════════════ -->
<!--           CHIRAG VENKATESHAIAH — Profile README          -->
<!-- ═══════════════════════════════════════════════════════ -->

<h1 align="center">Chirag Venkateshaiah</h1>

<p align="center">
  <strong>Data Engineer &nbsp;|&nbsp; Cloud Engineering &nbsp;·&nbsp; DevOps &nbsp;·&nbsp; SRE</strong>
</p>

<p align="center">
  Building data platforms. Operating them under real failure. Deploying them to production.
</p>

<p align="center">
  📍 India &nbsp;·&nbsp; 🎯 Targeting Canada &nbsp;(Toronto &nbsp;·&nbsp; Vancouver &nbsp;·&nbsp; Remote)
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white"/>
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonaws&logoColor=white"/>
  <img src="https://img.shields.io/badge/Databricks-FF3621?style=flat-square&logo=databricks&logoColor=white"/>
  <img src="https://img.shields.io/badge/Apache_Spark-E25A1C?style=flat-square&logo=apachespark&logoColor=white"/>
  <img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white"/>
  <img src="https://img.shields.io/badge/dbt-FF694B?style=flat-square&logo=dbt&logoColor=white"/>
  <img src="https://img.shields.io/badge/Ansible-EE0000?style=flat-square&logo=ansible&logoColor=white"/>
</p>

---

## About

**4.5 years as an Integration Business Analyst in FinTech** — including six months onsite at First Abu Dhabi Bank (UAE) — gave me the domain depth. I understand the financial data that flows through the systems I build, not just the pipelines that carry it.

Now I'm building the infrastructure and operational depth to match: production-deployed platforms, real incident response, real cost-managed cloud architectures. I run a structured 20-week engineering programme. Every project has a correctness constraint, a live deployment, and a postmortem when something breaks.

**Open to:** Data Engineer · Cloud Data Engineer · Platform Engineer · DevOps roles in Canada

---

## What I'm Building

<table>
<tr>
<td valign="top" width="50%">

### [novapay-sre](https://github.com/ChiragVenkateshaiah/novapay-sre)
`Go` `PostgreSQL` `systemd` `Ansible` `EC2` `Linux`

A production-style payments platform serving as a live SRE simulation. Enforces a
double-entry accounting invariant on every transaction — no exceptions.

Built and operated two real incidents:
- **OOM kill ordering** hardened via cgroup-v2 MemoryHigh/MemoryMax + three-tier
  OOMScoreAdjust (stub → API → Postgres — ledger dies last)
- **Disk-fill defence** via logrotate (50M, 7 compressed rotations, SIGHUP reopen)
  + journald SystemMaxUse cap — zero charge data loss

All decisions in Architecture Decision Records. Deployed on EC2, managed via Ansible.

</td>
<td valign="top" width="50%">

### [cerberus](https://github.com/ChiragVenkateshaiah/cerberus)
`AWS` `EMR Serverless` `Athena` `S3 Iceberg` `dbt` `Airflow` `OpenTofu`

Serverless-first AWS data engineering platform running in `ap-south-1`.

Replaced an EC2-based architecture after cost analysis proved a 2× runway extension
on fixed AWS credits — EMR Serverless bills at $0 when idle, vs. continuous EBS
billing even for a stopped EC2.

Infrastructure provisioned with OpenTofu. Budget alerts ($10 warn / $15 ceiling)
and CloudWatch observability wired from the first commit, not as an afterthought.

</td>
</tr>
<tr>
<td valign="top" width="50%">

### [novalake](https://github.com/ChiragVenkateshaiah/novalake)
`Databricks` `PySpark` `Delta Lake` `Lakeflow` `Vector Search` `Genie`

Databricks lakehouse built as the analytical counterpart to NovaPay. The same
synthetic payment event stream feeds this platform end-to-end:

**Bronze → Silver → Gold → Serving → GenAI (RAG + support-assist agent)**

Every transformation is hand-written before any orchestration abstraction is
introduced. Each layer is understood before it is adopted. No tutorial shortcuts.

</td>
<td valign="top" width="50%">

### [aegis](https://github.com/ChiragVenkateshaiah/aegis)
`Python` `Claude (Anthropic) APIs` `PostgreSQL` `Streamlit`

AI co-pilot for SME credit underwriting. Reduces memo preparation time from
~6 hours to ~8 minutes.

Extracts financial data from messy borrower documents via Claude vision + OCR
fallback, runs cross-document reconciliation to catch inconsistencies, computes
key ratios against lender thresholds, and generates a fully cited draft memo.

**Target buyers:** Community banks ($5B–$50B assets) and SME lending fintechs
across the US and Canada.

</td>
</tr>
</table>

---

## Portfolio

Foundational projects demonstrating the data engineering and analytics skills that underpin the active builds above.

| Project | Stack | What it demonstrates |
|---|---|---|
| [NYC Taxi Analytics Platform](https://github.com/ChiragVenkateshaiah/nyc-taxi-analytics-platform) | Databricks · PySpark · Delta Lake | End-to-end batch ingestion pipeline; Bronze→Silver→Gold Medallion; query-optimised Delta tables for analytics consumers |
| [Music Streaming Web App](https://github.com/ChiragVenkateshaiah/music-streaming-web-app) | Python · PostgreSQL · REST APIs | Full-stack application built end-to-end — secure backend APIs, cloud database integration, byte-range audio delivery, real-time frontend visualiser |
| [DVD Rental Analytics](https://github.com/ChiragVenkateshaiah/dvdrental-project) | PostgreSQL · SQL | Business-metric query library: window functions, aggregations, KPI design — translating business questions into reporting-layer SQL |

---

## Technical Stack

**Data Engineering**

| | |
|---|---|
| Processing | PySpark · SQL · dbt · Delta Lake · Apache Iceberg |
| Orchestration | Apache Airflow · Databricks Lakeflow · Declarative Pipelines |
| Ingestion | Batch ETL/ELT · REST API · Event-driven · Streaming |
| Modelling | Medallion architecture · Star/Snowflake schema · Dimensional modelling |

**Cloud & Infrastructure**

| | |
|---|---|
| AWS | EMR Serverless · Athena · S3 · Glue · CloudWatch · Budgets · IAM |
| Databricks | Unity Catalog · Delta Live Tables · Vector Search · Genie · AI/BI |
| IaC | Ansible · OpenTofu |
| Compute | EC2 · systemd · cgroup-v2 resource management |

**Systems & Reliability**

| | |
|---|---|
| Languages | Go · Python |
| Databases | PostgreSQL (pgx/v5 · connection pooling · ACID transactions) · SQLite |
| Observability | journald · logrotate · structured logging · audit trails |
| Reliability | Incident response · postmortems · runbooks · full-jitter exponential backoff |

**AI Engineering**

| | |
|---|---|
| Claude APIs | Vision · tool use · structured extraction · citation-grounded generation |
| Local AI | Ollama (llama3.2 · nomic-embed-text) · vector similarity search · RAG |
| Evaluation | Gold-standard benchmarks · extraction quality measurement · LLM eval harnesses |

---

## Certifications & Path

| Certification | Status |
|---|---|
| AWS Solutions Architect Associate (SAA) | 📅 Target: Week 12 |
| Anthropic CCF-A — Claude Certified Foundations Architect | Completed |
| SRE / DevOps / Platform Engineering — discipline decision | 📍 Week-20 checkpoint |

---

## Connect

<p>
  <a href="https://www.linkedin.com/in/chiragvenkateshaiah">💼 LinkedIn</a>
  &nbsp;·&nbsp;
  <a href="mailto:chiragvenkateshaiah95@gmail.com">📧 chiragvenkateshaiah95@gmail.com</a>
  &nbsp;·&nbsp;
  <a href="https://github.com/ChiragVenkateshaiah?tab=repositories">🐙 All Repositories</a>
</p>
