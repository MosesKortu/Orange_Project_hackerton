<div align="center">

<!-- HEADER BANNER -->

<img src="https://capsule-render.vercel.app/api?type=waving&color=333333&height=200&section=header&text=Telco%20Customer%20Intelligence&fontSize=38&fontColor=58a6ff&fontAlignY=38" width="100%"/>

<!-- BADGES ROW 1 -->
<p>
  <img src="https://img.shields.io/badge/Python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54"/>
  <img src="https://img.shields.io/badge/SQL_Server-CC2927?style=for-the-badge&logo=microsoft-sql-server&logoColor=white"/>
  <img src="https://img.shields.io/badge/Docker-0db7ed?style=for-the-badge&logo=docker&logoColor=white"/>
  <img src="https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white"/>
  <img src="https://img.shields.io/badge/Looker_Studio-4285F4?style=for-the-badge&logo=google-cloud&logoColor=white"/>
</p>

<!-- BADGES ROW 2 -->
<p>
  <img src="https://img.shields.io/badge/status-production--ready-brightgreen?style=flat-square"/>
  <img src="https://img.shields.io/badge/ML-Random%20Forest-orange?style=flat-square"/>
  <img src="https://img.shields.io/badge/infra-ngrok%20TCP%20Tunnel-001E2B?style=flat-square&logo=ngrok"/>
  <img src="https://img.shields.io/badge/license-MIT-blue?style=flat-square"/>
</p>

<br/>

> **Turning raw telecom logs into C-level revenue strategy** — a full-scale, production-grade pipeline unifying SQL governance, predictive ML, and executive BI in one coherent data product.

<br/>

</div>

---

##  Table of Contents

- [Project Vision](#-project-vision)
- [Pipeline Architecture](#-pipeline-architecture)
- [The Data Value Chain](#-the-data-value-chain)
- [Key Features](#-key-features)
- [Repository Structure](#-repository-structure)
- [Getting Started](#-getting-started)
- [Author](#-author)

---

##  Project Vision

This repository showcases a **full-scale Performance & Consumer Insights platform** built specifically for the telecom industry.

By combining **SQL governance**, **Python machine learning**, and **executive BI visualization**, the project goes far beyond traditional reporting — it delivers **proactive business strategy** that directly impacts key revenue levers:

| Business Lever | How This Pipeline Addresses It |
|---|---|
| 📉 Churn Reduction | ML-scored propensity model + prioritized outreach lists |
| 📈 ARPU Uplift | Segmentation by product density & upgrade funnel |
| 💰 Revenue Stability | At-Will vs. Contractual classification |
| 🎯 Targeted Marketing | Next-Best-Action recommendations per subscriber |

---

## 🏗️ Pipeline Architecture

```
┌─────────────────────────────────────────────────────────────────────┐
│                    TELCO INTELLIGENCE PIPELINE                      │
└─────────────────────────────────────────────────────────────────────┘

  ┌──────────────┐    ┌──────────────────┐    ┌─────────────────────┐
  │  RAW LOGS    │───▶│  ETL / INGESTION │───▶│  SQL SERVER (Docker)│
  │  (Source)    │    │  ingest_data.py  │    │  Dockerized Instance│
  └──────────────┘    └──────────────────┘    └──────────┬──────────┘
                                                         │
                               ┌─────────────────────────▼──────────┐
                               │     KPI GOVERNANCE LAYER (SQL)      │
                               │   VW_Subscriber_Master_Insights      │
                               │   Single Source of Truth             │
                               └─────────────────┬───────────────────┘
                                                 │
                  ┌──────────────────────────────▼──────────────────────┐
                  │              PREDICTIVE MODELING (Python)            │
                  │          churn_prediction.py  │  Random Forest       │
                  │       Churn Score 0.0 → 1.0   │  Target List + NBA   │
                  └──────────────────────────────┬──────────────────────┘
                                                 │
                              ┌──────────────────▼──────────────────┐
                              │       ngrok TCP TUNNEL (:1433)       │
                              │  Bridges local DB ↔ Cloud BI layer   │
                              └──────────────────┬───────────────────┘
                                                 │
                            ┌────────────────────▼────────────────────┐
                            │       LOOKER STUDIO DASHBOARDS          │
                            │   CEO Strategic Views │ Executive KPIs  │
                            └─────────────────────────────────────────┘
```

> 📸 *See `/assets/pipeline_architecture.png` for the full visual diagram.*

---

## 🔗 The Data Value Chain

The pipeline mirrors real-world enterprise telecom environments — a clean, auditable data flow from raw logs to C-level decision making.

### `01` · Ingestion & ETL

- Automated data loading via **`ingest_data.py`**
- Targets a **Dockerized SQL Server** for portability, consistency, and environment parity
- Schema-validated inserts with error logging

### `02` · KPI Governance & Metric Layer

- Central SQL view **`VW_Subscriber_Master_Insights`** serves as the **Single Source of Truth**
- Ensures reporting accuracy and financial reconciliation across the organization
- Powers all downstream ML and BI layers from one governed definition

### `03` · Predictive Churn Modeling

- **Random Forest classifier** trained on behavioral and demographic features
- Produces a **Churn Propensity Score (0.0 – 1.0)** for every active subscriber
- Generates an export-ready **Marketing Target List** with Next-Best-Action tags

### `04` · Executive Visualization

- Interactive **Looker Studio** dashboards engineered for the CEO Office and leadership team
- Surfaced via a secure **ngrok TCP tunnel** connecting the local DB to the cloud BI layer

---

##  Key Features

<details>
<summary><strong> &nbsp;KPI Governance & Metric Layer (SQL)</strong></summary>

<br/>

A powerful SQL metric layer transforming raw technical data into high-value commercial KPIs:

| Feature | Description |
|---|---|
| 🗺️ Infrastructure Mapping | Converts technical service types to commercial offerings (e.g., Fiber → 4G) |
| 📊 Revenue Stability Segmentation | Classifies subscribers as **At-Will** vs. **Contractual** to quantify baseline revenue risk |
| 🔗 Product Density Score | Measures customer "stickiness" across Voice, Data, VAS, and MoMo |
| 📅 Tenure Deciles | Buckets the subscriber base into 10% lifecycle cohorts for LTV analysis |

</details>

<details>
<summary><strong> &nbsp; Churn Propensity Modeling (Python / scikit-learn)</strong></summary>

<br/>

Advanced ML focused on **Customer Affinity Detection**:

-  **Random Forest Classification** — uncovers behavioral patterns preceding churn
-  **Churn Propensity Score** (0.0 – 1.0) assigned to every active subscriber
- Prioritized **Marketing Target List** with **Next-Best-Action** recommendations:
  - `"Immediate Outbound Call"` → high-value, high-risk
  - `"Retention Offer"` → mid-risk, contractual
  - `"Monitor"` → low-risk, stable

</details>

<details>
<summary><strong> &nbsp; Connectivity Infrastructure — ngrok TCP Tunnel</strong></summary>

<br/>

**The Challenge:** Cloud-based BI tools cannot natively access `localhost` or private network databases due to firewall and IP restrictions.

**The Solution:** An `ngrok tcp 1433` tunnel exposes the local SQL Server port through a secure, temporary public endpoint.

**The Impact:** A seamless automated reporting pipeline — cloud dashboards query local "Big Data" sets in real-time, with zero VPN or static IP configuration overhead.

```bash
# Initiate the tunnel
ngrok tcp 1433
# → Forwarding tcp://0.tcp.ngrok.io:XXXXX → localhost:1433
```

</details>

<details>
<summary><strong> &nbsp; CEO Strategic Dashboards (Looker Studio)</strong></summary>

<br/>

Executive-ready visualizations designed to act as a **trusted business partner** to leadership:

| Dashboard | What It Shows |
|---|---|
| 🔵 Strategic Value Quadrant | Bubble chart: ARPU vs. Churn Risk — identify defend vs. upsell cohorts |
| 📡 4G Migration Funnel | Quantifies revenue opportunity from upgrading 3G subscribers |
| 🟥 Revenue Weight Treemap | Highlights which segments drive the majority of total revenue |

</details>

---

## 📂 Repository Structure

```bash
telco-customer-intelligence/
│
├── 📁 automation/
│   └── ingest_data.py               # ETL pipeline — raw logs → SQL Server
│
├── 📁 sql/
│   └── master_view_insights.sql     # KPI governance & metric layer (SSOT)
│
├── 📁 models/
│   └── churn_prediction.py          # Random Forest churn propensity model
│
├── 📁 assets/                       # Dashboard screenshots, architecture diagrams
│
├── docker-compose.yml               # Dockerized SQL Server setup
├── requirements.txt                 # Python dependencies
└── README.md                        # You are here
```

---

##  Getting Started

### Prerequisites

```bash
# Python 3.9+
pip install -r requirements.txt

# Docker Desktop installed and running
```

### 1 · Spin Up the Database

```bash
docker-compose up -d
# SQL Server available at localhost:1433
```

### 2 · Ingest the Data

```bash
python automation/ingest_data.py
```

### 3 · Open the Tunnel (for Looker Studio)

```bash
ngrok tcp 1433
# Copy the forwarding address → paste into Looker Studio data source
```

### 4 · Run the Churn Model

```bash
python models/churn_prediction.py
# Outputs: churn_scores.csv + target_list.csv
```

### 5 · Connect Looker Studio

Point your Looker Studio SQL Server connector to the ngrok endpoint and open the executive dashboard.

---

## 👤 Author

<div align="center">

<br/>

**Moses Bargue Kortu, Jr.**

*Analytics Engineer · ML Practitioner · Telecom Analytics Specialist*

<br/>

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/moses-bargue-kortu/)
[![X / Twitter](https://img.shields.io/badge/X_(Twitter)-000000?style=for-the-badge&logo=x&logoColor=white)](https://twitter.com/MosesKortu)

<br/>

</div>

---

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:16213e,50:1a1a2e,100:0d1117&height=100&section=footer" width="100%"/>

*Built with precision. Designed for impact.*

</div>
