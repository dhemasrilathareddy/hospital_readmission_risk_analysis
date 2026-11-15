# Hospital Readmission Risk Analysis

## 📌 Business Problem
Hospitals face severe financial penalties when patients are readmitted within 30 days of discharge. This project analyzes 10 years of clinical encounter data from 130 U.S. hospitals to identify specific patient cohorts, primary diagnoses, and care patterns linked to a heightened risk of 30-day readmission. The objective is to provide care teams with data-driven insights to pinpoint high-risk patients, optimize resource allocation for follow-up care, and prevent avoidable readmissions.

---

## 📊 Data & Tools
* **Dataset:** Diabetes 130-US Hospitals for Years 1999–2008 (sourced from the UCI Machine Learning Repository, CC BY 4.0). Includes $\approx 100,000$ patient encounters across 130 hospitals.
* **Database Management System:** MySQL Workbench
* **Analytical Techniques:** Common Table Expressions (CTEs), Window Functions (`RANK`, `NTILE`), `CASE`-based risk tiering, correlated subqueries, and multi-table joins.

---

## 🛠️ Approach & Methodology
1. **Exploratory Analysis:** Established baseline readmission rates across demographic and clinical features, including age brackets, admission types, and primary diagnosis categories.
2. **Advanced Analysis:** Staged a clean, reusable high-risk patient group using CTEs, applied window functions to rank patients by clinical risk tiers, evaluated medication burden patterns alongside total diagnosis counts, and isolated specific diagnosis categories operating above the population-wide average readmission rate.
3. **Findings & Translation:** Synthesized query outputs into actionable clinical insights addressing the core business problem.

---

## ⚙️ Key SQL Techniques & Features
* **CTEs (Common Table Expressions):** Used to modularize workflows and stage clean, reusable patient risk cohorts across complex multi-step queries.
* **Window Functions:** 
  * `RANK() OVER (PARTITION BY ...)` to evaluate and rank medication burden within structured age groups.
  * `NTILE(4)` to segment patient records into distinct clinical risk quartiles.
* **`CASE`-Based Tiering:** Converted continuous numerical variables (such as total lab procedures and medication changes) into business-readable risk categories.
* **Correlated Subqueries:** Leveraged subqueries paired with `HAVING` clauses to filter diagnosis categories performing above the population-wide average threshold.
* **Multi-Table Joins:** Integrated ID-mapping reference tables to convert numeric diagnostic codes into descriptive, human-readable labels.

