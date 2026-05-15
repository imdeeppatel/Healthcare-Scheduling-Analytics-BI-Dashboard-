# Healthcare Scheduling Analytics & BI Dashboard

**Kaiser Permanente Internal Initiative**

A full-stack analytics pipeline and business intelligence solution that transforms raw EHR scheduling data into real-time patient flow visibility across clinical departments — directly supporting a 25% wait time reduction initiative.

---

## Overview

This project delivers an end-to-end data pipeline and Tableau dashboard suite for monitoring and optimizing patient scheduling operations. By connecting raw Electronic Health Record (EHR) data to structured SQL transformations and interactive visualizations, the solution gives clinical and operational leadership actionable insight into scheduling performance, resource utilization, and patient throughput.

---

## Key Features

- **EHR Data Ingestion** — Extracts raw scheduling data from source EHR systems across 5+ clinical departments
- **SQL Transformation Layer** — Cleans, normalizes, and enriches raw data into structured, analytics-ready tables
- **KPI Framework** — Defines and tracks metrics aligned with clinical and operational goals (wait times, appointment utilization, no-show rates, etc.)
- **Tableau Dashboards** — Real-time dashboards providing patient flow visibility to clinical and administrative stakeholders
- **Stakeholder Collaboration** — KPIs and metrics defined jointly with clinical staff and IT teams to ensure operational relevance

---

## Tech Stack

| Layer | Technology |
|---|---|
| Data Source | EHR Scheduling System |
| Transformation | SQL (stored procedures / views) |
| Visualization | Tableau |
| Collaboration | Cross-functional (Clinical + IT) |

---

## Pipeline Architecture

```
EHR Scheduling Data
        │
        ▼
  Raw Data Extraction
        │
        ▼
  SQL Transformations
  (cleaning, joins, aggregations)
        │
        ▼
  Analytics-Ready Data Layer
        │
        ▼
  Tableau Dashboards
  (real-time patient flow, KPIs)
        │
        ▼
  Clinical & Operational Stakeholders
```

---

## KPIs Tracked

- **Average Patient Wait Time** — Scheduled vs. actual appointment start time
- **Department Throughput** — Patients seen per hour / per day by department
- **Appointment Utilization Rate** — Booked slots vs. available capacity
- **No-Show & Cancellation Rate** — Trends by department, time of day, and provider
- **Scheduling Lead Time** — Days between booking and appointment date

---

## Impact

- Enabled **real-time patient flow visibility** across 5+ departments for clinical and operational teams
- Contributed to a **25% reduction in patient wait times** by surfacing scheduling inefficiencies
- Translated complex EHR data into **actionable metrics** through close collaboration with clinical and IT stakeholders

---

## Project Structure

```
healthcare-scheduling-analytics/
├── sql/
│   ├── raw_to_staging.sql        # Initial data cleaning and normalization
│   ├── staging_to_analytics.sql  # KPI calculations and aggregations
│   └── views/                    # Reusable views for Tableau connection
├── dashboards/
│   └── patient_flow_dashboard.twbx  # Tableau packaged workbook
├── docs/
│   ├── kpi_definitions.md        # Definitions and business logic for each KPI
│   └── data_dictionary.md        # Field-level documentation for all tables
└── README.md
```

---

## Setup & Usage

### Prerequisites

- Access to the EHR scheduling data source (internal credentials required)
- SQL Server / PostgreSQL environment (adjust dialect as needed)
- Tableau Desktop or Tableau Server

### Steps

1. **Run SQL transformations** in order:
   ```sql
   -- Step 1: Raw to staging
   source sql/raw_to_staging.sql

   -- Step 2: Staging to analytics layer
   source sql/staging_to_analytics.sql
   ```

2. **Connect Tableau** to the analytics layer tables/views produced in step 1.

3. **Open the dashboard** (`dashboards/patient_flow_dashboard.twbx`) and publish to Tableau Server for stakeholder access.

---

## Stakeholders

| Group | Role |
|---|---|
| Clinical Staff | KPI definition, metric validation |
| IT / Data Team | Pipeline development, data access |
| Operations Leadership | Dashboard consumers, decision-makers |

---

## Notes

- All data used in this project is internal to Kaiser Permanente and subject to HIPAA compliance requirements. No patient PII is exposed in dashboards or transformation outputs.
- Refresh cadence and data retention policies follow Kaiser Permanente's internal data governance standards.

---

*Internal initiative — Kaiser Permanente*
