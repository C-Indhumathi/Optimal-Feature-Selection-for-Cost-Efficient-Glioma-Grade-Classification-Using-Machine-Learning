🧠 GLIOMA TUMOR GRADE CLASSIFICATION 📝 Project Overview This project
focuses on developing a robust and parsimonious (minimal) classification
model to accurately distinguish between Lower Grade Glioma
(LGG) and Glioblastoma (GBM). The classification utilizes a blend of
clinical features (Age, Gender, Race) and a panel of 20 common molecular
mutation markers. The primary goal is to identify the optimal, minimal
feature subset required to achieve high predictive performance.

1.  Data Analysis and Key Clinical & Molecular Findings Initial
    Exploratory Data Analysis (EDA) revealed critical relationships for
    classifying tumor grade: 1.1. Key Clinical Findings  1.2. Key
    Molecular Findings 

2.  Feature Selection Methodology A rigorous, two-stage feature
    selection pipeline was implemented to refine the initial set of 23
    candidate features: Stage 1: Random Forest Ranking  Method: A Random
    Forest Classifier assigned an importance score to all features.
    Result: The ranking was dominated by Age_at_diagnosis ( importance)
    and IDH1 mutation status ( importance). Output: The search space was
    reduced to the Top 15 ranked features. Stage 2: Optimal Subset
    Selection (Cross-Validation)  Method: Sequential testing using a
    Logistic Regression model with 5-Fold Cross-Validation (CV)
    maximized the Macro F1-Score. Result: The highest F1-Score () was
    achieved with  features. Output: Features beyond this point were
    deemed redundant.

3.  The Optimal Feature Set and Model Foundation The final model is
    based on the following 8 features: Verification: Target
    Correlation: Confirmed that IDH1 (LGG) and Age_at_diagnosis (GBM)
    provide the necessary strong, opposing signals to distinguish the
    grades. Multicollinearity: The subset is stable and free of
    redundancy due to low inter-feature correlation (maximum ).

4.  Model Evaluation and Final Selection Three different classifiers
    were trained and evaluated on the optimal 8-feature subset using a
    hold-out test set (N=168). 4.1. Overall Performance  4.2. Detailed
    Performance Metrics (Logistic Regression)  4.3. Final Selection
    Rationale The Logistic Regression model was selected as the final
    classifier  because: Highest Performance: It achieved the highest
    overall Macro F1-Score (0.88) and Accuracy (0.8750). Balanced
    Prediction: It demonstrated the best balance of class performance,
    achieving excellent Recall for GBM (0.94) while maintaining
    strong Precision for LGG (0.95). Interpretability (Primary
    Factor): Logistic Regression provides direct, linear coefficients,
    which is essential in a clinical application. This allows clinicians
    to easily interpret the model's output.
