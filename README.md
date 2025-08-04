## 🚑 EmergencyDept\_PowerPivot\_Analytics.xlsx


### 📘 Overview

This workbook implements a full **Power Pivot** data model focused on emergency department analysis:

* Builds a relational model connecting patient visits, vital signs, and clinical scores.
* Defines calculated columns and **DAX measures** to compute metrics like fever rate, admission percentage, and EWS (Early Warning System) totals. ([Microsoft Support][1])
* Enables analysis of performance trends and severity levels, grouped by staff, shifts, or patient characteristics.

---

### 🔧 Core Power Pivot Techniques

#### ▪️ Data Modeling & Relationships

* Imported **admissions, discharge, and triage vitals** as separate tables in the data model.
* Created **one-to-many relationships** between them using Power Pivot’s Diagram View. ([Microsoft Support][2])

#### ▪️ Calculated Columns

* Columns like `fierra` and `afterhours` derived using row-level formulas (e.g. `IF([Temp]>=100.4,1,0)`).

#### ▪️ Measures (DAX Calculations)

* `TotalVisits = COUNTROWS(Visits)`
* `FeverRate = DIVIDE([Fever], [TotalVisits])`
* EWS Score and Scaled ESI metrics defined using nested DAX functions for aggregation. ([dax.guide][3])

#### ▪️ Time Intelligence & KPIs

* Created a Date table (or used `CALENDARAUTO()`) to support time-based analysis like month-over-month trends. ([dax.guide][4])
* Built KPIs to highlight before-threshold or alert-level performance.

---

### 🧠 Lessons Learned

* Power Pivot enables **professional-grade analytics** without leaving Excel.
* **DAX measures** adapt dynamically to slicers and fields (e.g. by ESI level, weekday/weekend). ([Microsoft Fabric Community][5], [Microsoft Support][2], [Microsoft Learn][6])
* A well-designed data model (tables + relationships + measures) allows you to pivot large datasets swiftly and correctly.

---
