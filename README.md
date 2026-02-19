📌 Overview

AltCredAI is an AI-powered alternate credit scoring framework designed to expand lending access to unbanked individuals and MSMEs. Traditional credit scoring systems rely heavily on bureau histories, excluding borrowers with thin or no credit files.

This project uses machine learning models to estimate Probability of Default (PD) from alternative financial signals and converts PD into an interpretable credit score with fairness auditing and explainability.

🎯 Objective

To build a scalable, explainable, and fair AI-based credit risk model that:

Predicts Probability of Default (PD)

Converts PD into standardized credit score (300–900 scale)

Optimizes decision thresholds using expected loss principles

Ensures fairness through bias auditing

Provides SHAP-based explanations for transparency

🏗 System Architecture

Alternative Data Sources
→ Data Ingestion
→ Preprocessing & Feature Engineering
→ Machine Learning Engine
→ Risk Scoring & Threshold Optimization
→ Explainability & Fairness Module
→ Decision Output

⚙️ Tech Stack

Python 3.10+

Jupyter Notebook

pandas

numpy

scikit-learn

XGBoost

imbalanced-learn (SMOTE)

SHAP

matplotlib

seaborn

📊 Methodology
1️⃣ Data Processing

Missing value imputation

Feature scaling

Removal of protected attributes

SMOTE for class imbalance correction

2️⃣ Model Training

Logistic Regression (baseline)

Random Forest (feature importance)

XGBoost (primary model)

5-fold cross-validation

3️⃣ Risk Scoring

Probability of Default (PD):

PD = P(Default | Features)

Credit Score Mapping:

Score = 900 − (PD × 600)

Expected Loss:

EL = PD × EAD × LGD

Threshold optimized to minimize expected loss.

📈 Model Performance (Benchmark – Give Me Some Credit Dataset)

Logistic Regression AUC: ~0.77

Random Forest AUC: ~0.80

XGBoost AUC: ~0.82

Primary metric: AUC-ROC
Secondary metrics: Recall, F1-score

🔎 Explainability

SHAP (SHapley Additive Explanations) used for:

Global feature importance

Local per-customer explanation

Regulatory transparency

⚖️ Fairness & Bias Mitigation

Removal of protected attributes

Disparate Impact Ratio (Four-Fifths Rule)

Subgroup performance validation

Target:

DI ≥ 0.8
No significant accuracy gap across groups

🚀 Scalability

Modular pipeline

Configurable dataset switching

XGBoost supports distributed training (Dask integration)

Deployment-ready via FastAPI (future extension)

📂 Repository Structure
AltCredAI/
│
├── AltCredAI.ipynb
├── README.md
├── data/ (if applicable)
└── outputs/ (plots, metrics)

🔐 Compliance & Governance

Designed to align with:

RBI Fair Practices Code

GDPR / DPDP

EU AI Act transparency standards

💡 Future Enhancements

Real-time API scoring

Federated learning for privacy

Graph-based risk modeling

Risk-based pricing integration

📌 Status

Prototype pipeline designed for hackathon submission.
Deployment-ready architecture planned for production adaptation.
