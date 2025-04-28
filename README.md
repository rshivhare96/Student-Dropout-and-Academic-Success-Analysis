# 🎓 Student Dropout and Academic Success Analysis

This project analyzes student performance, demographic, and socioeconomic data to understand dropout patterns and predict academic success in a higher education setting. Using a real-world dataset, we explore various features impacting student outcomes and build predictive models to identify at-risk students and their likelihood of academic achievement.

---

## 📊 Dataset Overview

The dataset consists of **4,424 records** with **35 features** representing academic, personal, and economic variables. The target variable is a multi-class label indicating whether a student:

- 🎓 Graduated  
- 🟡 Is currently Enrolled  
- ❌ Dropped Out

### Key Features

- **Demographics**: Age at enrollment, Gender, Marital status, Nationality
- **Academic History**: Previous qualifications, Curricular unit grades and approvals
- **Family Background**: Parents’ education and occupation
- **Socioeconomic Indicators**: GDP, Inflation, Unemployment rate
- **Administrative Data**: Application details, Enrollment type, Special needs status

### Data Quality

- No missing values found.
- Categorical features were numerically encoded.
- All columns were properly cleaned and standardized for modeling.

---

## 🔍 Exploratory Data Analysis

Some important patterns discovered:

- Dropouts tend to have lower grades and approval rates across both semesters.
- Graduates are more likely to be scholarship holders and have timely tuition payments.
- Age at enrollment correlates with academic success — younger students tend to perform better.
- Economic indicators (like GDP and unemployment) may also show weak correlations with dropout rates.

---

## 🤖 Machine Learning Task: Multi-Class Classification

We used a `KNeighborsClassifier` to predict student status: *Graduate*, *Enrolled*, or *Dropout*.

### Best Model Performance (K=14):

| Metric      | Score |
|-------------|-------|
| Accuracy    | 0.73  |
| F1-Score    | 0.75 (Weighted Avg) |

### Classification Report (K=14):

| Class      | Precision | Recall | F1-score |
|------------|-----------|--------|----------|
| Dropout    | 0.79      | 0.71   | 0.75     |
| Enrolled   | 0.39      | 0.26   | 0.31     |
| Graduate   | 0.73      | 0.87   | 0.79     |

📌 The classifier performs best for predicting **graduates** and **dropouts**, but has challenges with **enrolled** students due to class imbalance and overlapping behavior.

---

## 📈 Model Tuning

Tested K-values from **1 to 100**:
- Peak accuracy reached at **K = 14**, ~0.73
- Accuracy remained stable (~0.70) for a wide range (K=5 to K=50)
- Models with K > 70 showed a slight decline in performance

---

## 💡 Insights & Recommendations

- **Early Warning**: Students with poor semester grades and evaluation rates are more likely to drop out — interventions can be introduced early.
- **Scholarship Programs**: Scholarship holders are more likely to graduate, suggesting increased funding can improve outcomes.
- **Parental Education**: Higher parental education levels correlate with better student performance.
- **Segmented Interventions**: Use clustering (future work) to create student personas for personalized support strategies.

---

## 🛠 Requirements

To install the required libraries, run:

```bash
pip install -r requirements.txt
