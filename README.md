# Healthcare Machine Learning Project

**Author:** Jay  
**Institution:** Fresno State — BS Computer Science, Cybersecurity Specialization  
**Course:** Machine Learning  
**Due Date:** April 26, 2026

---

## Project Overview

This project applies supervised machine learning to three real-world healthcare datasets using Python and scikit-learn. The goal was to demonstrate the complete ML workflow — from data loading and preprocessing, through model training, hyperparameter tuning, and evaluation, to comparison against published academic benchmarks.

Two datasets are binary classification tasks and one is a regression task, giving full coverage of both classification and regression metrics.

---

## Datasets

| Dataset | Task | Rows | Features | Target |
|---|---|---|---|---|
| Pima Indians Diabetes | Classification | 768 | 8 | Diabetic (1) / Not (0) |
| Cleveland Heart Disease | Classification | 297 | 13 | Disease (1) / No Disease (0) |
| Medical Insurance Costs | Regression | 1,338 | 6 | Annual charges ($) |

All three datasets were sourced from [Kaggle](https://www.kaggle.com).

---

## Models Used

**Pima Indians Diabetes**
- Logistic Regression
- Random Forest Classifier
- MLP Neural Network

**Cleveland Heart Disease**
- K-Nearest Neighbors (KNN)
- Decision Tree Classifier
- Naive Bayes

**Medical Insurance Costs**
- Linear Regression
- Decision Tree Regressor
- Random Forest Regressor

All models were tuned using `GridSearchCV` or `RandomizedSearchCV` with 5-fold cross-validation.

---

## Results Summary

**Classification — Pima Diabetes (best model: Random Forest)**

| Model | Accuracy | F1 | ROC-AUC |
|---|---|---|---|
| Logistic Regression | 0.773 | 0.657 | 0.828 |
| Random Forest | 0.799 | 0.693 | 0.851 |
| MLP Neural Network | 0.786 | 0.676 | 0.839 |

**Classification — Heart Disease (best model: Naive Bayes)**

| Model | Accuracy | F1 | ROC-AUC |
|---|---|---|---|
| KNN | 0.797 | 0.781 | 0.864 |
| Decision Tree | 0.780 | 0.767 | 0.780 |
| Naive Bayes | 0.814 | 0.790 | 0.876 |

**Regression — Insurance Costs (best model: Random Forest)**

| Model | MAE | RMSE | R² |
|---|---|---|---|
| Linear Regression | $2,641 | $4,181 | 0.771 |
| Decision Tree | $2,895 | $4,730 | 0.738 |
| Random Forest | $2,427 | $3,745 | 0.863 |

---

## Repository Structure

```
healthcare-ml-project/
│
├── healthcare_ml_project.ipynb   # Main Jupyter notebook — all code, outputs, and analysis
├── healthcare_ml_report.docx     # Summary report — methods, results, literature comparison
├── healthcare_ml_slides.pptx     # 9-slide presentation deck
├── speaker_notes.docx            # Speaker notes for the 10-minute presentation
│
├── diabetes.csv                  # Pima Indians Diabetes dataset
├── heart_cleveland_upload.csv    # Cleveland Heart Disease dataset
├── insurance.csv                 # Medical Insurance Costs dataset
│
└── README.md                     # This file
```

---

## How to Run the Notebook

1. Clone or download this repository
2. Make sure the three CSV files are in the same folder as the notebook
3. Install dependencies if needed:
   ```bash
   pip install pandas numpy scikit-learn matplotlib seaborn
   ```
4. Open `healthcare_ml_project.ipynb` in Jupyter Notebook or JupyterLab
5. Run all cells from top to bottom — `Kernel → Restart & Run All`

The notebook is fully self-contained. All plots are generated inline and all metrics are printed directly in the output cells.

---

## Literature References

1. Kavakiotis, I., Tsave, O., Salifoglou, A., Maglaveras, N., Vlahavas, I., & Chouvarda, I. (2017). Machine Learning and Data Mining Methods in Diabetes Research. *Computational and Structural Biotechnology Journal*, 15, 104–116.

2. Detrano, R., Janosi, A., Steinbrunn, W., et al. (1989). International application of a new probability algorithm for the diagnosis of coronary artery disease. *American Journal of Cardiology*, 64(5), 304–310.

3. Rashid, T. A., & Abdulrahman, A. (2022). Healthcare insurance cost prediction using machine learning. *International Journal of Online and Biomedical Engineering*, 18(3).

4. Pedregosa, F., et al. (2011). Scikit-learn: Machine Learning in Python. *Journal of Machine Learning Research*, 12, 2825–2830.

---

## Key Findings

- Random Forest was the top-performing model on all three datasets
- Zero imputation preprocessing on the Diabetes dataset had a more noticeable effect on results than hyperparameter tuning alone
- All results fell within or at the top of the ranges reported in the cited literature
- Smoker status was the single most important predictor in the Insurance regression task, consistent with Rashid & Abdulrahman (2022)
