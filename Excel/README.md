# 📊 ExcelPro Analytics & Assessment Project

<img width="1024" height="559" alt="image" src="https://github.com/user-attachments/assets/f8517747-e119-46a1-882f-bee133231935" />


### 🖱️ Click the Image Above
<p align="center">
  <a href="#-project-overview">
    🎯 <b>PROJECT OVERVIEW</b>
  </a>
  &nbsp;&nbsp; ➜ &nbsp;&nbsp;
  <a href="#-data-processing--cleaning-steps">
    🔄 <b>DATA CLEANING & LOOKUP</b>
  </a>
  &nbsp;&nbsp; ➜ &nbsp;&nbsp;
  <a href="#-summary--pivot-analysis">
    📊 <b>SUMMARY & PIVOT ANALYSIS</b>
  </a>
  &nbsp;&nbsp; ➜ &nbsp;&nbsp;
  <a href="#%EF%B8%8F-key-formula-reference">
    🛠️ <b>KEY FORMULA REFERENCE</b>
  </a>
</p>
This documentation provides comprehensive guidelines and a complete `README.md` overview for the `excelpro.xlsx` project, based on its raw data sheets, cleaning workflows, summary metrics, and visual artifacts.

---

## 📌 Project Overview
**ExcelPro** is a Student Assessment and Course Performance Analytics platform. Its primary goal is to evaluate candidate performance, monitor attendance percentages, calculate pass/fail status, and uncover department-level trends over time.

---

## 📌 Executive Summary

`excelpro.xlsx` processes assessment evaluation metrics across various departments (**Business** and **Technology**) and learning batches (**Morning**, **Evening**, **Weekend**). It automates data enrichment using dynamic Excel lookup formulas and provides aggregate metrics on assessment passing rates and monthly performance trends.

---

## 🔄 Data Processing & Cleaning Steps

<img width="1024" height="559" alt="image" src="https://github.com/user-attachments/assets/890a2bd9-7304-48a5-9e73-9f8ffcebe370" />

1. **Deduplication**:
   * *Before Removal*: 13 Records
   * *After Removal*: 12 Unique Records (The duplicate record for Assessment ID `12` was purged).
2. **Department Enrichment**:
   * Mapped `Department` using the `courses(lookup)` sheet based on the `course_id` field (`C1`, `C2`, `C3`, `C4`).
   * **C1 (Excel)** & **C2 (PowerBI)** ➔ *Business*
   * **C3 (SQL)** & **C4 (Python)** ➔ *Technology*

---

## 📊 Dataset Preview (`Clean`)

| Assessment ID | Month | Course ID | Batch | Score | Attendance % | Department | Pass Flag |
|---|---|---|---|---|---|---|---|
| 1 | Jan | C1 | Morning | 72 | 90% | Business | 1 |
| 2 | Jan | C2 | Evening | 45 | 70% | Business | 0 |
| 3 | Jan | C3 | Morning | 65 | 85% | Technology | 1 |
| 4 | Jan | C4 | Weekend | 38 | 60% | Technology | 0 |
| 5 | Feb | C1 | Evening | 80 | 95% | Business | 1 |
| 6 | Feb | C2 | Weekend | 55 | 80% | Business | 1 |
| 7 | Feb | C3 | Morning | 48 | 75% | Technology | 0 |
| 8 | Feb | C4 | Evening | 68 | 88% | Technology | 1 |
| 9 | Mar | C1 | Weekend | 90 | 98% | Business | 1 |
| 10 | Mar | C2 | Morning | 60 | 82% | Business | 1 |
| 11 | Mar | C3 | Evening | 75 | 92% | Technology | 1 |
| 12 | Mar | C4 | Weekend | 42 | 65% | Technology | 0 |

---

## 📁 Workbook Structure & Data Pipeline

The workbook consists of 4 main sheets structured into a sequential data flow:
..
### 1. `assessments(Row)` — Raw Data Sheet
Contains raw assessment-level logs, including score, attendance percentage, and automated pass/fail flags.
* **Columns:** `assessment_id`, `month`, `course_id`, `batch`, `score`, `attendance_pct`, `pass_flag`
* **Formulas:**
  * `pass_flag`: `=IF(score >= 50, 1, 0)`

---

### 2. `courses(lookup)` — Lookup Master
A dimension table mapping course codes to full course titles and their respective organizational departments.
* **Columns:** `course_id`, `course`, `department`
* **Data Mapping:**
  * `C1` ➔ Excel *(Department: Business)*
  * `C2` ➔ PowerBI *(Department: Business)*
  * `C3` ➔ SQL *(Department: Technology)*
  * `C4` ➔ Python *(Department: Technology)*

---

### 3. `Clean` — Enriched & Deduplicated Dataset
Combines evaluation records with course metadata using advanced dynamic Excel lookups and tracks record deduplication statistics.
* **Columns:** `assessment_id`, `month`, `course_id`, `batch`, `score`, `attendance_pct`, `Department`, `pass_flag`
* **Formulas:**
  * `Department`: `=INDEX('courses(lookup)'!$C$2:$C$5, MATCH(course_id, 'courses(lookup)'!$A$2:$A$5, 0))`
  * `pass_flag`: `=IF(score >= 50, 1, 0)`
* **Audit Tracking:** Includes a duplicate tracking table (Original count: **13**, Deduplicated count: **12**).

---

### 4. `Summary` — Aggregate Dashboard & Pivot Analysis
Aggregates performance metrics using multi-criteria conditional counting and Pivot Tables.

#### A. Batch-wise Passing Assessments
Uses conditional aggregation to calculate passing assessments per batch:
* **Formula:** `=COUNTIFS(Clean!$D$2:$D$13, batch_name, Clean!$H$2:$H$13, 1)`

| Batch | Passing Assessments |
| :--- | :---: |
| **Morning** | 3 |
| **Evening** | 3 |
| **Weekend** | 2 |

#### B. Department Average Score Trend (Pivot View)

| Department | Jan | Feb | Mar | Grand Total |
| :--- | :---: | :---: | :---: | :---: |
| **Business** | 58.5 | 67.5 | 75.0 | **67.0** |
| **Technology** | 51.5 | 58.0 | 58.5 | **56.0** |
| **Grand Total** | **55.0** | **62.75** | **66.75** | **61.5** |

<img width="1191" height="627" alt="image" src="https://github.com/user-attachments/assets/141020c2-b035-49dc-b68c-5c02fa519259" />

---

## 🛠️ Key Formula Reference

| Purpose | Excel Formula |
| :--- | :--- |
| **Department Lookup** | `=INDEX('courses(lookup)'!$C$2:$C$5, MATCH(C2, 'courses(lookup)'!$A$2:$A$5, 0))` |
| **Pass/Fail Logic** | `=IF(E2 >= 50, 1, 0)` |
| **Conditional Counting** | `=COUNTIFS(Clean!$D$2:$D$13, A2, Clean!$H$2:$H$13, 1)` |

---

## 🚀 How to Use

1. **View Raw Records:** Open `assessments(Row)` to review or append new raw evaluation entries.
2. **Update Metadata:** Manage new course codes or department mappings in `courses(lookup)`.
3. **Inspect Clean Data:** Check the `Clean` tab for auto-populated department fields and audit notes.
4. **Analyze Insights:** Navigate to `Summary` for batch-wise totals and monthly department average scores.
