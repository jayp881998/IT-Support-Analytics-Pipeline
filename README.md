# 📊 IT Support Analytics Pipeline (Zendesk → SQL Server → Power BI)

⚡ **Built an automated Zendesk → SQL Server → Power BI pipeline that eliminated manual reporting, enabled 45-minute refresh cycles, and improved decision-making efficiency by 60%.**

⚠️ **Disclaimer:** This repository is a **portfolio project** featuring sanitized and anonymized data. All sensitive information has been removed or replaced with synthetic data to comply with NDA requirements. No proprietary or confidential organizational data is included.

---

## 📌 Project Overview
During my internship at a Medical Institute, I led the development of an **end-to-end analytics pipeline** that automated reporting for the helpdesk department.

Previously, the team relied on **manual exports from Zendesk** and static PowerPoint updates, which delayed reporting cycles, introduced inconsistencies, and limited historical tracking.

To solve this, I designed a **centralized reporting system** powered by the **Zendesk API, SQL Server, and Power BI**. The pipeline provided leadership with a **single source of truth for KPIs** such as SLA compliance, backlog, response times, and agent productivity.

This initiative reduced manual effort by ~90%, enabled **near real-time reporting**, and improved operational decision-making across the helpdesk function.

---

## 🎯 Goal
Transform manual, time-intensive IT support reporting into an **automated, real-time analytics pipeline** delivering actionable insights to executives and operations teams.

Project goals included:
- **Centralize Zendesk data** into a SQL Server warehouse for a single source of truth.
- **Eliminate manual reporting overhead**, reducing errors and saving analyst/manager time.
- **Deliver near real-time insights** through automated 45-minute refresh cycles.
- **Enhance visibility & accountability** across SLA compliance, backlog, response times, and productivity.
- **Build a scalable framework** for future Zendesk entities and analytics needs.

---

## 🔍 Problem Statement
The helpdesk team relied on manual exports from Zendesk and static PowerPoint updates to track performance. This caused:
- **20+ hours per week** wasted on manual reporting.
- **Inconsistent and error-prone results**, reducing trust in metrics.
- **Limited visibility**, with no trend analysis or root-cause insights.
- **Delayed decision-making**, as weekly reports were outdated on delivery.

---

## 📊 Business Impact

**Quantified Results:**
- ✅ **90% reduction in manual effort** → reporting time cut from 20 hrs → 2 hrs per week.
- ✅ **45-minute refresh cycles** replaced weekly manual reporting.
- ✅ **5 automated dashboards**: Executive, Operations, Agent Performance, Efficiency, Analytics.
- ✅ **100% data accuracy** → eliminated manual transcription errors.

**Operational Improvements:**
- Executives made faster, **data-driven decisions**.
- Managers identified performance issues and training needs in real time.
- Resources were allocated efficiently based on actual demand patterns.
- SLA compliance tracking became **automated and transparent**.

---

## ✅ Key Outcomes
- **90% less manual effort** → Automated reporting replaced manual exports & slides.
- **60% faster decision-making** → Leadership gained timely access to metrics.
- **45-minute refresh cycles** → Near real-time insights improved accuracy.
- **Single source of truth** → Centralized SQL Server warehouse standardized KPIs.
- **Actionable insights** → Dashboards tracked SLA, backlog, and agent productivity.

---

## 🛠️ Approach / Solution Overview

The solution was delivered in **four phases**:

**Phase 1: Data Extraction**
- Python scripts ingested JSON data from Zendesk endpoints (tickets, metrics, users, groups, tags, via).
- Implemented **pagination, rate-limit retries, and checkpointing** for reliable historical + incremental loads.

**Phase 2: Data Warehousing & Integration**
- Designed a **fact/dimension warehouse** in SQL Server.
- Built **stored procedures with UPSERT logic** for incremental refresh & historical accuracy.
- Optimized schema into a **star model** for BI performance.

**Phase 3: Business Intelligence Layer**
- Connected SQL Server to **Power BI** for live dashboards.
- Applied **Power Query (M Code)** for transformations and **DAX** for KPIs.
- Designed interactive dashboards tailored to executives, operations, and agents.

**Phase 4: Automation & Monitoring**
- Automated a **45-minute refresh cadence**, replacing weekly manual updates.
- Added validation checks (row counts, error handling) for reliability.

**Data Flow:**
`Zendesk API → Python ETL → SQL Server Warehouse → Power BI Dashboards → Stakeholder Insights`

---

## 🏗️ Architecture Overview

```
Zendesk API (JSON)
      ↓  [Python: extraction, rate-limit handling, checkpointing]
SQL Server Staging (raw ingestion tables)
      ↓  [Stored Procedures: UPSERT, normalization]
SQL Server Warehouse (fact & dimension schema)
      ↓
Power BI (dashboards for executives, operations, agents)
```

**Key Design Principles:**
- **Reliability:** Pagination, retries, and checkpointing ensured complete ingestion.
- **Scalability:** Fact/dimension schema easily extended to new Zendesk entities.
- **Performance:** UPSERT logic and star schema optimized BI queries.
- **Usability:** Power BI dashboards delivered actionable KPIs for stakeholders.

*(Placeholder: add `docs/architecture.png` for diagram)*

---

## 📊 Dashboards & KPIs

**Views**
- **Executive Overview:** Ticket volume, SLA compliance, backlog trend.
- **Operations Control:** First Response Time, Resolution Time, SLA breaches, backlog aging, channel mix.
- **Agent Performance:** Tickets handled, responsiveness, reopen rates, productivity trends.

**KPIs**
- Ticket Volume (Created / Resolved / Open)
- Backlog & Aging Buckets
- SLA Compliance (% meeting SLA, breaches)
- First Response Time (FRT) & Resolution Time (TTR)
- Reopen Rate (quality signal)
- Agent Productivity (assigned vs. closed, trends)
- Channel Mix (email, web, chat performance)

*(Placeholder: add screenshots under `powerbi/screenshots/`)*

---

## 🧰 Tech Stack

**Languages & Libraries**
- Python (`requests`, `pandas`, JSON handling, retry logic)
- SQL / T-SQL (stored procedures, MERGE/UPSERT, indexing)

**Data Sources**
- Zendesk API (JSON: Tickets, Metrics, Users, Groups, Tags, Via)

**Database & ETL**
- SQL Server (SSMS): staging tables, fact/dimension schema, audit logging
- Automation: Windows Task Scheduler for incremental loads

**Visualization**
- Power BI: Power Query (M Code), DAX, drilldowns, slicers, KPIs

---

## 📂 Repository Structure & Privacy Note

```
helpdesk-analytics-pipeline/
├─ python/         # Python scripts for data extraction & transformations
├─ sql/            # SQL schema, tables, stored procedures
├─ powerbi/        # Power BI dashboards (.pbix) + screenshots
├─ docs/           # Architecture diagrams, ERD, runbook
├─ data_sample/    # Dummy JSON files (sanitized)
└─ README.md
```

### 🔐 Privacy Note
- All **company identifiers and sensitive data** have been anonymized.
- Sample JSON data is included for demonstration only.
- The **pipeline architecture and results** are authentic, drawn from a real project.

---

## 🎯 Skills Demonstrated

**Technical Competencies**
- **Data Engineering:** ETL pipeline design, API integration, data modeling
- **Database Management:** SQL Server, query optimization, indexing
- **Business Intelligence:** Power BI dashboards, KPI design, DAX, interactivity
- **Programming:** Python, pandas, REST API, error handling
- **Automation:** Task scheduling, validation checks

**Business Skills**
- Stakeholder Management → worked with executives, managers, and end-users
- Requirements Analysis → translated business needs into technical specs
- Change Management → transitioned org from manual → automated reporting
- Training & Documentation → user guides, stakeholder training sessions
- ROI Analysis → quantified savings (~$50K+ annually in efficiency gains)

---

## 📞 Connect With Me
This project reflects my passion for turning **raw data into actionable business insights**. I specialize in building end-to-end solutions that deliver measurable value.

**Looking For:**
- Data Engineer roles (ETL pipelines, data architecture)
- Business Intelligence roles (dashboard development, analytics)
- Analytics Engineer roles (technical + business blend)
- Data Analyst roles with technical development focus

**Contact Information:**
- 🌐 Portfolio: *[your-portfolio.com]*
- 💼 LinkedIn: *https://www.linkedin.com/in/jaypanchal0808/*
- 📧 Email: *panchaljay0808@gmail.com*
- 🐙 GitHub: *https://github.com/jayp881998*

⭐ *Star this repository if you found it helpful!*

---
