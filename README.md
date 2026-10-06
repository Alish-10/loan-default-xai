# Loan Default Prediction using Machine Learning and Explainable AI

### Balancing Predictive Performance and Explanation Reliability in Imbalanced Loan Default Prediction

An MSc research project investigating machine learning and explainable AI (XAI) for loan default prediction, with a focus on class imbalance, predictive performance, SHAP, LIME, and explanation reliability.

**MSc IT with Data Analytics — University of the West of Scotland**

---

## 📄 Conference Paper

### Balancing Predictive Performance and Explanation Reliability in Imbalanced Loan Default Prediction

**Authors:** Suman Pokhrel, Abhinaw Adhikari, Sanjiv Shrestha, Alish Dahal, and Yan Ge

**Accepted for presentation at AI-2026, Cambridge, UK | 15–17 December 2026**

**[📄 Read the Accepted Manuscript](/AI-2026_Accepted_Manuscript.pdf)**

> The manuscript is identified here as an **accepted manuscript**. Inclusion in the conference proceedings is subject to the final-paper, registration, and publication/licensing requirements of the conference.

---

## 🎓 MSc Dissertation

### Loan Default Prediction using Machine Learning and Explainable AI (SHAP and LIME)

**MSc IT with Data Analytics — University of the West of Scotland**

**[📘 Read the Full MSc Dissertation](/Msc_Dissertation.pdf)**

The dissertation presents the broader MSc project, including the research design, implementation, model evaluation, explainability analysis, limitations, and future work.


## 📌 Overview

This project develops and evaluates an end-to-end machine learning and explainable-AI workflow for loan default prediction using an imbalanced mortgage lending dataset.

The study compares two baseline models:

- Logistic Regression
- Decision Tree

with two ensemble models:

- Random Forest
- XGBoost

To address class imbalance, **SMOTE was applied only to the training data**. Random Forest and XGBoost were tuned using **five-fold cross-validation**.

The project then applies **SHAP** and **LIME** to investigate model explanations, including local explanation reliability, stability, fidelity, runtime, and explanation compactness.

The research focuses not only on predictive performance, but also on whether model explanations are sufficiently reliable and useful for practical interpretation.

---

## 📊 Dataset

The study uses a public Loan Default Dataset containing:

- **148,670 anonymised mortgage-related records**
- **34 original fields**
- Numerical and categorical variables
- A binary target representing default and non-default

The original dataset is imbalanced, with roughly three non-default observations for each default observation.

The data were divided into:

- **70% training**
- **15% validation**
- **15% independent test**

SMOTE was applied only to the training partition.


---

## ⚙️ Methodology

The research follows an end-to-end prediction and explanation workflow:

```text
Dataset
   ↓
Data Preprocessing
   ↓
Stratified Train / Validation / Test Split
   ↓
Training-only SMOTE
   ↓
Baseline Models
   ├── Logistic Regression
   └── Decision Tree
   ↓
Ensemble Models
   ├── Random Forest
   └── XGBoost
   ↓
Model Evaluation
   ↓
XGBoost Selection for Explainability Analysis
   ↓
SHAP + LIME
   ↓
Explanation Reliability Evaluation
```
The study is intentionally presented as an empirical application study, rather than as a new machine learning algorithm.

## 🤖 Machine Learning Models

Four classification models were evaluated:

1. Logistic Regression
2. Decision Tree
3. Random Forest
4. XGBoost

Random Forest and XGBoost hyperparameters were selected using grid search with five-fold cross-validation on the training data.

---

## 📈 Model Performance

| Model | Accuracy | Precision | Recall | F1-score | AUC-ROC | PR-AUC |
|---|---:|---:|---:|---:|---:|---:|
| Logistic Regression | 0.839 | 0.732 | 0.548 | 0.627 | 0.798 | 0.723 |
| Decision Tree | 0.913 | 0.818 | 0.834 | 0.826 | 0.886 | 0.723 |
| Random Forest | 0.928 | 0.837 | 0.881 | 0.858 | 0.983 | 0.949 |
| XGBoost | 0.927 | 0.821 | 0.901 | 0.859 | 0.983 | 0.951 |

### Key Findings

XGBoost achieved:

- **Recall:** 0.901
- **F1-score:** 0.859
- **AUC-ROC:** 0.983
- **PR-AUC:** 0.951

Random Forest achieved the highest overall accuracy:

- **Accuracy:** 0.928
- **Precision:** 0.837
- **AUC-ROC:** 0.983
- **PR-AUC:** 0.949

XGBoost was selected as the final model for further explainability analysis because of its stronger recall, highest F1-score, and superior PR-AUC performance.

---

## 🔍 Explainable AI

The study uses two explainability techniques:

### SHAP

SHAP was used to examine both global and local model explanations.

The global analysis identified **interest rate** as the dominant predictor, followed by encoded credit and loan characteristics.

Other contributing features included:

- Credit type
- Business or commercial loan purpose
- Loan type
- Negative amortisation status
- Age bands
- Loan-to-value ratio
- Income

The SHAP analysis also indicated a generally positive relationship between higher interest rates and the model's predicted probability of default.

### LIME

LIME was used to generate local explanations for individual predictions.

The method provides a compact local narrative by approximating the model's decision behaviour around a selected observation.

---

## 🧪 Explanation Reliability

The research also evaluated LIME and TreeSHAP at case level using:

- Runtime
- Normalised stability
- Local fidelity
- Explanation compactness

### Case-Level Comparison

| Diagnostic | LIME | TreeSHAP |
|---|---:|---:|
| Runtime (seconds) | 0.1160 | 0.0602 |
| Normalised stability | 0.5514 | 1.0000 |
| Local fidelity | 0.5876 | ≈1.0000 |
| Features for approximately 80% contribution | 6 | 7 |

In the evaluated case-level diagnostic, TreeSHAP was faster, more stable, and more faithful to the selected tree model.

LIME provided a more compact and intuitive local explanation.

The study therefore treats SHAP and LIME as **complementary rather than interchangeable** methods rather than claiming that one method is universally better.

---

## ❓ Research Questions

The project investigates:

1. How do Logistic Regression, Decision Tree, Random Forest, and XGBoost compare for imbalanced loan default prediction?
2. How does class-imbalance handling affect predictive performance?
3. How can SHAP and LIME be used to explain predictions from complex machine learning models?
4. How reliable are SHAP and LIME explanations in terms of stability, fidelity, runtime, and compactness?
5. How should predictive performance and explanation reliability be considered together when selecting a model?

---

## 💻 Google Colab Notebook

The complete implementation is available in a single Google Colab notebook.

**[🔗 Open the Google Colab Notebook](https://colab.research.google.com/drive/1iHVq2W_LTnqNl-20XC2kTJki0YugemyB)**

The notebook contains the main data preparation, model development, evaluation, and explainability workflow used in the project.

---


## 👤 My Contribution

This was a collaborative MSc project completed by a four-member team.

My main individual contribution focused on **LIME-based local explainability and explanation evaluation**.

I contributed to:

- Implementing LIME-based local explanations
- Analysing feature contributions for individual predictions
- Evaluating explanation consistency and stability
- Examining local surrogate fidelity
- Comparing explanation characteristics with SHAP
- Supporting preprocessing, baseline modelling, evaluation, and feature analysis

My work particularly focused on the relationship between **predictive performance and explanation reliability** in an imbalanced financial classification setting.

---

## 🛠️ Technologies

- Python
- Google Colab
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- XGBoost
- SHAP
- LIME

---

## ⚠️ Limitations

The study has several limitations:

- The analysis uses a single dataset, which may limit generalisation to other financial datasets.
- Explanation stability and consistency were evaluated only to a limited extent.
- Feature engineering was limited.
- Deep learning models were not explored.
- The study focuses on structured financial data.
- The explanations should not be interpreted as causal evidence.
- Additional external validation, calibration, threshold-cost analysis, fairness assessment, and explanation testing across larger populations would be required before operational use.

The research therefore represents an applied research study and **not a production-ready credit policy**.

---

## 🔬 Future Research

Potential extensions include:

- External and temporal validation
- Evaluation across multiple financial datasets
- Probability calibration
- Threshold optimisation under explicit business costs
- Cost-sensitive learning and class weighting
- Fairness and subgroup performance analysis
- Larger-scale explanation stability evaluation
- Sensitivity analysis of SHAP and LIME parameters
- Interpretable model development
- Monitoring for data and model drift

---

## 📚 Citation

If you reference the research paper, please cite:

> Pokhrel, S., Adhikari, A., Shrestha, S., Dahal, A., & Ge, Y. *Balancing Predictive Performance and Explanation Reliability in Imbalanced Loan Default Prediction*. Accepted for presentation at AI-2026, Cambridge, UK, 15–17 December 2026.

---

