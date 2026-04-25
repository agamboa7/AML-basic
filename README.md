# Applied Machine Learning (Basic) — Breast Cancer Wisconsin Classification Model

This repository contains the final project developed for the **Applied Machine Learning (Basic)** course at the **University of Bologna**.

The project applies a complete supervised machine learning workflow to the **[Breast Cancer Wisconsin (Diagnostic)](https://archive.ics.uci.edu/dataset/17/breast+cancer+wisconsin+diagnostic)** dataset from the UCI Machine Learning Repository. The objective is **binary classification** of tumors as **malignant** vs **benign** using 30 cell nucleus features extracted from fine needle aspiration (FNA) biopsies.

The workflow includes data exploration and quality checks, handling moderate class imbalance through stratified evaluation, addressing feature redundancy/correlation via feature selection, comparing common classification models (Logistic Regression, SVM, kNN), and improving performance through **SVM (RBF) hyperparameter tuning**.

---

## Project workflow
0. **Setup**
   - Import libraries, set `RANDOM_STATE`, configure plotting.

1. **Load data**
   - Download dataset using `ucimlrepo` following the procedure shown on the dataset website.
   - Convert labels (B/M) to numeric target (0/1).

2. **Exploratory Data Analysis (EDA)**
   - Data quality checks (missing values, duplicates, types).
   - Class balance visualization.
   - Feature distribution plots (histograms and boxplots).
   - Correlation analysis (heatmap + highly correlated pairs).

3. **Data preparation**
   - Define model-ready feature matrix and target.
   - Stratified train/test split.
   - Feature selection.

4. **Baseline model**
   - Logistic Regression pipeline.

5. **Evaluation**
   - Confusion matrix, classification report, ROC-AUC, ROC curve, Precision–Recall curve.
  
6. **Cross-validation**
   - Stratified 5-fold cross-validation (mean ± std).
  
7. **Feature Importance**
   - Feature names and coefficients from the trained baseline model.

8. **Model comparison**
   - Compare Logistic Regression vs SVM (RBF) vs kNN using Stratified CV across multiple metrics.

9. **Hyperparameter tuning**
   - Tune **SVM (RBF)** with **GridSearchCV** over `C` and `gamma` (optimized for accuracy).

10. **Final test evaluation and comparison**
    - Evaluate tuned SVM on the test set and compare against the baseline SVM.

---

## Key results
- Hyperparameter tuning improved overall performance mainly by **reducing false positives**:
- Accuracy increased (baseline SVM → tuned SVM)
- Malignant precision improved up to **1.00**
- Malignant recall remained high (FN remained small)

---

## How to run
This project was developed in **Google Colab**.

1. Open the notebook in Colab (or locally with Jupyter).
2. Run the cells from top to bottom.
3. The dataset is downloaded automatically via `ucimlrepo`.

---

> This is an educational project intended to demonstrate a standard applied ML workflow in a healthcare-related classification setting.
