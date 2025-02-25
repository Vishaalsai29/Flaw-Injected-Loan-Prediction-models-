# Flaw-Injected Loan Prediction Models (Model Risk Management)

## 📌 Project Overview  
This project explores the impact of **intentional flaws in machine learning models** used for **loan approval predictions**. We introduce **data imbalances, mislabeled training samples, and feature selection biases** to assess their effects on model performance and risk assessment. By applying a **Red Team-Blue Team strategy**, we identify vulnerabilities in AI-driven financial decision-making.

## 🔍 Key Objectives  
- Develop **loan prediction models** using **Random Forest** and **XGBoost** to classify loans as **fully paid or charged off (defaulted)**.  
- Introduce **controlled flaws** such as **class imbalance, label flipping, and multicollinearity** to analyze model weaknesses.  
- Evaluate **risk management strategies** to **enhance model robustness and fairness** in financial applications.  

## 🗃 Dataset & Preprocessing  
- **Source:** Lending Club public loan dataset (~2M records, reduced to 200K samples).  
- **Data Cleaning:** Removed irrelevant/missing data and filtered loans issued after **August 2012** to avoid policy shifts.  
- **Feature Engineering:** Included **financial metrics (FICO score, loan amount, debt-to-income ratio)** and applied **categorical encoding**.  
- **Handling Missing Data:** Mean imputation for numerical values, mode imputation for categorical values (introducing potential biases).  
- **Data Splitting:** **70-30% train-test split**, ensuring class balance for evaluation.

## ⚠️ Flaws Introduced & Impact  
| **Flaw Type** | **Implementation** | **Impact on Model** |
|--------------|------------------|--------------------|
| **Class Imbalance** | Oversampled **fully paid** loans (95%) while undersampling **charged off** loans (5%) in training data. | Model **favored the majority class**, leading to **low recall** for defaulted loans. |
| **Label Flipping** | Randomly flipped 10% of training labels. | **Degraded model accuracy**, misleading feature importance scores. |
| **Multicollinearity** | Kept redundant FICO score features (high correlation). | **Reduced model interpretability**, inflated feature importance. |

## 🎯 Risk Management Strategies  
- **Addressing Class Imbalance:** Implement **SMOTE (Synthetic Minority Over-Sampling), weighted loss functions, or cost-sensitive learning**.  
- **Mitigating Label Flipping Impact:** Use **data validation techniques and uncertainty-aware modeling**.  
- **Handling Multicollinearity:** Apply **correlation heatmaps, Variance Inflation Factor (VIF) analysis, and feature reduction techniques (PCA, LASSO regression)**.  
- **Bias & Fairness Audits:** Conduct **Fairlearn or SHAP-based analyses** to detect discriminatory biases in model predictions.

## 🚀 Conclusion  
This project highlights the risks of **data biases and flawed ML modeling in financial decision-making**. The **XGBoost classifier** emerged as the most **robust model**, but **further improvements are needed** to address fairness and predictive reliability. The insights gained from **flaw injection techniques** reinforce the importance of **model risk management and validation in AI-driven finance**.
