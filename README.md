# Predicting Mental Health Treatment Needs in the Workplace

## 📌 Project Overview
This project analyzes the **OSMI Mental Health in Tech Survey** dataset to identify key workplace and demographic factors associated with mental health treatment-seeking behavior. The goal is to provide data-driven insights that can help employers design more effective mental health support systems.

**Author:** Shen Hongshan  
**Date:** November 2025  
**Course:** HKU COMP2501

## 🎯 Research Questions
1. What are the most significant demographics and workplace features associated with employees seeking mental health treatment?
2. Based on these associations, what targeted interventions can employers prioritize?

## 📂 Files in This Repository

- `2501report_ShenHongshan_Version2.Rmd` – Full R Markdown analysis with code, visualizations, and commentary.
- `2501 pre.pdf` – Presentation slides summarizing key findings and recommendations.
- `survey.csv` – The original dataset (not included here; available on Kaggle).
- `README.md` – This file.

## 📊 Dataset

**Source:** [OSMI Mental Health in Tech Survey on Kaggle](https://www.kaggle.com/datasets/osmi/mental-health-in-tech-survey/data)  
**Description:** Anonymous survey responses from tech industry employees covering:
- Demographics (age, gender, etc.)
- Workplace factors (company size, remote work, mental health benefits, etc.)
- Mental health history and treatment status

## 🛠️ Methodology

### 1. Data Cleaning & Preparation
- Removed irrelevant columns (`Timestamp`, `Country`, `comments`, `state`)
- Standardized gender categories (Male, Female, Transgender/Non-binary/Others)
- Filtered unrealistic age values (18–100)
- Combined related mental health support variables into `mental_care`

### 2. Exploratory Data Analysis (EDA)
- Visualized treatment rates by age, gender, family history, work interference, and workplace support
- Identified key patterns and correlations

### 3. Modeling
- **Model:** Logistic Regression (binary outcome: seeking treatment or not)
- **Predictors:** 17 features including age, gender, family history, work interference, and workplace support variables
- **Evaluation:** Train/test split (70/30), ROC-AUC, confusion matrix, feature importance

### 4. Interaction Analysis
- Explored how factors like `work_interfere` and `family_history` interact
- Investigated gender-specific responses to different types of mental health support

## 🔑 Key Findings

### Strongest Predictors of Treatment-Seeking
1. **Work Interference** – The strongest signal; frequent interference → higher treatment rates.
2. **Family History** – Increases likelihood by ~35%.
3. **Workplace Support** – Access to benefits, anonymity, and supportive culture increases treatment engagement.
4. **Gender** – Women and gender-diverse individuals show higher treatment rates than men.

### Gender-Sensitive Insights
- **Women:** More responsive to financial benefits for mental health care.
- **Men:** More responsive to direct, accessible care options at work.
- **Both genders:** Most effective is a comprehensive program combining multiple supports.

### Interaction Effects
Employees with **both** family history and frequent work interference are at the highest risk (>90% treatment rate).

## 📈 Model Performance
- **AUC:** 0.85 (good discrimination)
- **Accuracy:** 80.23%
- **Specificity:** 91.91% (good at identifying those in treatment)
- **Sensitivity:** 59.27% (lower at identifying those not in treatment)

## 🧠 Limitations & Future Work

### Limitations
- Self-reported data may include response bias.
- Correlation ≠ causation; cannot prove interventions work.
- Model sensitivity is low, meaning it may miss some at-risk individuals.

### Future Improvements
- Use advanced ML models (Random Forest, XGBoost) for better prediction.
- Collect longitudinal data to establish causal relationships.
- Include more diverse industry samples beyond tech.

## 📋 How to Run This Analysis

### Prerequisites
- R (>= 4.0)
- RStudio (recommended)

### Required R Packages
```r
install.packages(c(
  "tidyverse", "caret", "broom", "car", "pROC", 
  "patchwork", "corrplot", "reshape2", "Hmisc"
))
```

### Steps
1. Download the dataset from Kaggle and save as `survey.csv` in the same directory.
2. Open `2501report_ShenHongshan_Version2.Rmd` in RStudio.
3. Knit the document to generate the full report (HTML, PDF, or Word).

---

## 📬 Contact
For questions or collaborations, please contact:  
**Shen Hongshan** – sunnie22shen@connect.hku.hk

---

## 📚 References
- OSMI Mental Health in Tech Survey – Kaggle
- James, G., et al. *An Introduction to Statistical Learning*
---

*This project was completed as part of COMP2501 – Introduction to Data Science and Engineering.*
