# Hospital ER Operations & Analytics Dashboard

An end-to-end analytics solution for Hospital Emergency Room operations, combining **Power BI** for reporting and analysis with an embedded **Power Apps** interface (backed by **Dataverse**) for real-time patient admission, bed allocation, and discharge management.

---

## 📌 Business Problem

Hospital ER management lacked a centralized system to track operational performance and patient flow. Stakeholders needed a way to monitor daily patient volume, wait times, service quality, and referral patterns to make faster, data-driven decisions — while operational staff needed a simple interface to record patient admissions, bed assignments, and discharges as they happened.

This project addresses both needs: a **reporting layer** (Power BI) for stakeholders and an **operational layer** (Power Apps + Dataverse) for day-to-day data entry, connected through a shared data model.

---

## 🎯 Objectives / KPI Requirements

The dashboard was built to answer the following business requirements:

- **Number of Patients** — Measure total daily ER visits and display trends over time (area sparkline) to identify peak days and seasonal patterns.
- **Average Wait Time** — Calculate average patient wait time before being attended to, with daily trend tracking to flag days requiring operational adjustments.
- **Patient Satisfaction Score** — Track daily average satisfaction to evaluate service quality and correlate dips with operational challenges or peak periods.
- **Number of Patients Referred** — Count daily referrals to specific departments and identify departments with high referral rates that may need additional resources.

---

## 🗂️ Project Structure

```
├── Dashboard Visuals/ # Dashboard screenshots (Consolidated, Monthly, Patient Details, ER System views)
├── Emergency Room Dashboard.pbix   # Power BI file (data model, DAX measures, report pages)
└── Hospital ER_Data.csv/ # Raw Kaggle dataset used for analysis
```

---

## 🧰 Tools & Technologies

| Category | Tools |
|---|---|
| Reporting & Visualization | Power BI, DAX, Power Query |
| Operational App | Power Apps (Canvas), Power Fx |
| Data Layer | Microsoft Dataverse |
| Data Source | Kaggle (public dataset) |

---

## 🔄 Project Workflow

1. **Data Sourcing** — Hospital ER dataset sourced from Kaggle (public dataset).
2. **Data Cleaning** — Cleaned and standardized raw data using Power Query (correcting data types, resolving inconsistent categorical values, handling missing fields).
3. **Data Modeling** — Built a relational Dataverse data model with four interconnected tables:
   - `Patients` — patient demographic and admission details
   - `Bed Allocations` — links patients to assigned beds
   - `Bed Availabilities` — tracks real-time bed occupancy status
   - `Patient Discharges` — records discharge details and updates bed status
4. **Power Apps Development** — Built a Canvas app for ER staff to:
   - Register new patient admissions
   - Allocate beds to admitted patients (auto-updates bed availability)
   - Process patient discharges (auto-frees the assigned bed)
5. **Power BI Reporting** — Designed a multi-page dashboard, embedding the Power Apps interface directly within a report page so staff can update records without leaving Power BI.
6. **DAX Measures** — Created measures for KPI calculations (patient volume, average wait time, satisfaction score, referral counts) with daily trend visualizations.

---

## 📊 Dashboard Views

- **Consolidated View** — Full patient-level table with filters across demographics, admission status, wait time, and department referral.
- **Monthly View** — KPI summary cards (patients, wait time, satisfaction, referrals) with trend sparklines, patient demographics (age, gender, race), department referral breakdown, and a day/hour patient traffic heatmap.
- **Patient Details View** — Drill-through view for individual patient records.
- **ER System (Power Apps)** — Embedded operational app for patient registration, bed allocation, and discharge entry, directly connected to the Dataverse data model.

---

## 🔑 Key Design Decisions

- **Dataverse over static import** — Used Dataverse as a shared data layer between Power Apps and Power BI (instead of a static Excel/SharePoint source) to model a realistic, relational hospital operations system with live data entry capability.
- **Embedded Power Apps in Power BI** — Allows report viewers to take action (update discharge/bed status) directly from the reporting layer, without switching tools.
- **Relational table design** — Separated Patients, Bed Allocations, Bed Availabilities, and Discharges into normalized tables with lookup relationships, reflecting real-world hospital data architecture rather than a single flat table.

---

## ⚠️ Notes & Limitations

- Dataset is static (sourced from Kaggle) rather than a live hospital feed; the Dataverse + Power Apps layer was built to demonstrate how the system would function with live, real-time data entry.
- Live DirectQuery integration between Power BI and Dataverse requires Power BI Premium/paid licensing, which was not available for this project; the current setup uses the dataset for reporting while the Power Apps + Dataverse layer operates independently to demonstrate the intended architecture.

---

## 👤 Author

**Rizwan Abdul Razzak**
Data Analyst | [LinkedIn](https://www.linkedin.com/in/rizwan-abdul-razzak-ab05aa236/)
