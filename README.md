# 🚘 BMW Hackathon — Sensor Impact Analysis (2023)

## 📝 Overview
This project was developed during the **BMW Hackathon 2023**.

**Objective:** Identify which sensors most strongly influence defective parts (NOK) to inform predictive maintenance and improve production quality. The focus is on **sensor impact ranking**, not just predicting part quality (OK vs NOK).

The workflow includes **EDA, preprocessing, feature engineering, imputation, and model preparation** for XGBoost-based feature importance extraction.

> ⚠️ Note: Model training was halted due to the inclusion of the identifier column (`physical_part_id`). Once fixed, the pipeline will produce a ranked list of the most impactful sensors.

---

## ❓ Problem Statement
- Identify sensors most correlated with defective parts (NOK).  
- Business impact: Optimize maintenance and calibration, reduce NOK rates, and minimize unplanned downtime.

---

## 🔬 Methodology
1. **Exploratory Data Analysis (EDA)**  
   - Analyzed distributions of part types, shifts, weekdays, correlations, and missing data patterns across ~400 sensors.

2. **Feature Engineering**  
   - One-hot encoding for categorical features (`physical_part_type`).  
   - Cyclical encoding for temporal variables (`weekday`, `shift`).  
   - Converted timestamps to numeric epoch values.

3. **Missing Data Imputation**  
   - Planned use of `IterativeImputer` to preserve multivariate relationships in sensor readings.

4. **Modeling for Sensor Impact**  
   - **Model:** XGBoost classifier for high-dimensional structured data.  
   - **Goal:** Rank features by importance to identify sensors most predictive of NOK outcomes.  
   - **Issue:** Inclusion of `physical_part_id` caused training failure.

---

## 🛠️ Skills Demonstrated
- Preprocessing high-dimensional sensor data (~400 features).  
- Encoding categorical and temporal variables.  
- Advanced imputation strategies (`IterativeImputer`).  
- ML pipeline design for interpretable feature importance extraction.  
- Use of XGBoost for structured data analysis.

---

## 📊 Expected Outcomes
- Once corrected, XGBoost will provide a **ranking of sensors by impact**.  
- Business value: Focus monitoring and maintenance on the **top-ranked sensors** to reduce defects and improve line reliability.

---

## 🚀 Next Steps
Solve the error
