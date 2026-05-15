# Employee Belonging & Engagement Analysis
### IBM HR Analytics Dataset | Statistical Modelling | Python

> **Analytical Statement:** *"Employees who feel a sense of belonging are more engaged"*  
> Investigated through a full three-stage statistical pipeline as part of the
> 
---

## 📁 Project Overview

This project applies descriptive, inferential, and predictive statistical 
analysis to evaluate whether workplace belonging predicts employee engagement, 
using the IBM HR Analytics dataset (1,470 employees, 35 variables).

---

## 📊 Dataset

- **Source:** [IBM HR Analytics – Kaggle](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset)
- **Size:** 1,470 employees × 35 columns
- **Type:** Secondary dataset — survey-style workplace responses
- **Key columns used:** RelationshipSatisfaction, EnvironmentSatisfaction,
  JobInvolvement, JobSatisfaction, Attrition, OverTime, Department

---

## ⚙️ Feature Engineering

Two composite scores were created to represent the core constructs:

| Score | Formula | Represents |
|---|---|---|
| BelongingScore | (RelationshipSatisfaction + EnvironmentSatisfaction) / 2 | Sense of connection and inclusion |
| EngagementScore | (JobInvolvement + JobSatisfaction) / 2 | Job commitment and satisfaction |

---

## 🔬 Analysis Pipeline

### 1. Data Preparation
- No missing values or duplicate rows found
- Removed 3 constant columns (EmployeeCount, Over18, StandardHours)
- Encoded Attrition and OverTime from Yes/No to 1/0
- Engineered BelongingScore and EngagementScore

### 2. Descriptive Analysis
- Summary statistics (mean, median, std) for both composite scores
- Histograms with mean/median overlays
- Box plots grouped by Department, Gender, and Attrition
- Scatter plot with jitter and Pearson correlation

### 3. Inferential Analysis
| Test | Result |
|---|---|
| Pearson Correlation (Belonging vs Engagement) | r = −0.002, p = 0.953 → No significant relationship |
| t-test: BelongingScore (Stayed vs Left) | t = 4.06, p < 0.001 → Significant difference |
| t-test: EngagementScore (Stayed vs Left) | t = 6.17, p < 0.001 → Significant difference |

### 4. Predictive Modelling
| Model | Accuracy | ROC-AUC |
|---|---|---|
| Logistic Regression | 86.1% | 0.792 |
| Decision Tree | 85.0% | 0.754 |

- Target variable: Attrition (0 = Stayed, 1 = Left)
- Features: BelongingScore, EngagementScore, WorkLifeBalance,
  OverTime, JobLevel, YearsAtCompany
- BelongingScore coefficient: −0.530 (higher belonging → less likely to leave)
- EngagementScore coefficient: −0.710 (higher engagement → less likely to leave)

---

## 📌 Key Finding

Belonging and engagement show **no direct linear relationship** at the 
individual level (r ≈ 0). However, both scores are **significantly lower** 
in employees who left the organisation (p < 0.001), and both independently 
**reduce attrition risk** in the predictive model.

> The statement is **partially supported** — belonging and engagement are  
> not cause and effect, but co-indicators of overall workplace wellbeing.

---

## 🛠️ Tools & Libraries

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Google Colab](https://img.shields.io/badge/Google%20Colab-F9AB00?style=flat&logo=googlecolab&logoColor=white)

- `pandas`, `numpy` — data manipulation
- `matplotlib`, `seaborn` — visualisation
- `scipy.stats` — Pearson correlation, t-tests
- `sklearn` — Logistic Regression, Decision Tree, model evaluation

---

## 👥 Team — Group KND_08

| Name | Role |
|---|---|
| [Patali Tennakoon] | Descriptive Analysis |
| [Nithya Waidyarathne] | Data Preparation & Feature Engineering |
| [Ashani Mahagamage] | Inferential Analysis |
| [Punsara Rathnayake] | Predictive Modelling |

---

## 📄 License
This project is for academic purposes. Dataset sourced from Kaggle under
public domain use.
