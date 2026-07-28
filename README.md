<div align="center">

# C0 Sort Wash Dashboard

### Track shift performance. Surface variances. Bridge the gaps.

A daily operations dashboard for Amazon Delivery Station (DS) shift reporting — built from the real **C0 Sort Wash with Bridges** template used by Area Managers to report shift performance to leadership.

Track processed volume vs plan, Sort TPH, SSP, and WIP compliance. When a process path misses by more than 5%, the **Bridges** view flags it for root cause analysis and corrective action.

![Dashboard](./dashboard.png)

**HTML** · **Excel** ·

![Formulas](https://img.shields.io/badge/Excel%20formulas-73-green)
![Errors](https://img.shields.io/badge/formula%20errors-0-success)
![No Backend](https://img.shields.io/badge/backend-none-orange)

</div>

---

## Why This Project

As an **Amazon Logistics Area Manager**, I completed a daily **C0 Sort Wash** report after every night shift — a structured document tracking volume, TPH, and quality metrics against plan, with "bridges" (root cause analysis) for any process path that missed by more than 5%.

This was done manually in a Word template: copying numbers, calculating variances by hand, and writing narrative explanations. This project automates that workflow into an interactive dashboard with live variance calculations and visual KPIs.

---

## What's Inside

![Daily Log](./daily-log.png)

Three views, all with localStorage persistence — no backend needed:

| View | Features |
| --- | --- |
| **Dashboard** | 5 KPI cards (Total Processed, Avg Sort TPH, Avg SSP, Avg WIP, Misses) + 4 charts (volume bar, TPH line, quality trend, bridge variance) |
| **Daily Log** | 14 shift records, search, color-coded status pills (Hit/Below/Miss), add/edit/delete via modal, CSV export |
| **Bridges** | 6 process paths (Unload, Induct, Pusher, P2B, Sort PS, Stow) with UPH & hours variance, auto-flagged misses, root cause prompts |

### Excel Workbook (3 sheets · 73 live formulas · 0 errors)

**Sheet 1: Dashboard**
- 4 KPI cards with SUM/AVERAGE formulas referencing Daily_Data
- 3 charts: Volume Processed vs Planned, Sort TPH Actual vs Plan, SSP & WIP trend

**Sheet 2: Daily_Data**
- 14 days of sample shift data (date, planned/processed volume, TPH plan/actual, SSP, WIP, high WIP intervals, induct BRT, notes)
- Live formula columns: Vol Variance (`=C-B`), TPH Variance (`=E-D`), Status (`=IF(OR(...),"Miss","Below","Hit")`)
- Conditional formatting: red/yellow/green status pills

**Sheet 3: Bridges**
- 6 process paths with actual vs planned UPH and labor hours
- Live variance formulas + auto root-cause text based on UPH miss threshold
- Summary totals row + horizontal bar chart

---

## Skills Demonstrated

- **Variance analysis** — actual vs planned across volume, TPH, UPH, and labor hours
- **KPI design** — defining and tracking operational metrics (SSP, WIP, BRT)
- **Root cause analysis** — bridging process path misses with structured explanations
- **Process improvement** — documenting corrective actions based on data
- **Stakeholder reporting** — building reports leadership reads daily
- **Data visualization** — charts for trends, variance, and status
- **Excel modeling** — live formulas, conditional formatting, charts

---

## Notes

- Shift data is **fictional sample data** for demonstration (realistic C0 sort volumes and variance patterns)
- Web app data lives in `localStorage`; use **Export CSV** to back up
- All Excel formulas are live — change any input and dependent cells recalculate instantly
- Shared schema between web app and Excel — CSV export bridges them
