Final Capstone Project
Project Overview
Final Capstone Project is an end-to-end data science and machine learning project that demonstrates how structured tabular data can be transformed into reliable, interpretable decision-support insights. Covering the complete analytics lifecycle—from problem framing and data preprocessing to exploratory analysis, predictive modeling, and stakeholder reporting—this project evaluates multiple supervised classification algorithms to identify key quantitative drivers and establish a practical, two-stage prioritization framework.
Core Objectives
Identify Key Predictive Drivers: Quantify which continuous measurement features most strongly differentiate between target classes.
Build & Compare Classifiers: Train and benchmark both linear and ensemble machine learning models using stratified cross-validation and held-out evaluation metrics.
Deliver Actionable Recommendations: Translate statistical outputs and model interpretations into clear, plain-language operational guidelines.

Dataset Overview
Structure & Volume: A cleaned, structured tabular dataset comprising 569 records and 8 continuous numerical features paired with a binary target variable.
Target Class Distribution:
Majority Class (Class 0): 357 records (62.7%)
Minority Class (Class 1): 212 records (37.3%)
Feature Set & Engineering:
Primary Scale Metrics: Three continuous size and boundary measurements that serve as the strongest individual predictors of class separation.
Secondary Structural Metrics: Five continuous shape, texture, smoothness, and symmetry measurements that provide additional discriminatory signal for borderline records.
Engineered Features: Derived ratio indicators and a four-tier categorical segmentation variable (Small, Medium, Large, Very Large) created to support group-level risk profiling.
Data Quality & Preparation:
Removed 5 duplicate rows to ensure record uniqueness.
Imputed 37 missing entries using column medians to preserve distribution stability.
Standardized target labels and verified zero residual null values prior to modeling.

Project Steps & Methodology
1. Problem Definition & Success Criteria
Framed the analytical objective around high-priority target identification, prioritizing minority-class recall alongside overall accuracy and ROC-AUC to minimize costly false-negative errors.
2. Data Preparation & Feature Engineering
Audited schema integrity, resolved duplicate and missing records, standardized categorical labels, and constructed ratio and size-tier features for downstream segmentation.
3. Exploratory Data Analysis (EDA)
Analyzed feature distributions across target classes using histograms and summary statistics to locate high-separation ranges and narrow overlap zones.
Computed pairwise Pearson correlation heatmaps to identify multicollinearity among primary scale features.
Aggregated minority-class incidence rates across categorical size tiers, revealing a consistent upward progression from 3.5% in the lowest tier to 100.0% in the highest tier.
4. Predictive Modeling & Validation
Partitioned the dataset using an 80/20 stratified train-test split (455 training records, 114 test records) to preserve class proportions.
Built reproducible preprocessing and modeling pipelines comparing two distinct algorithms:
Logistic Regression (with StandardScaler normalization) as an interpretable linear baseline.
Random Forest Classifier (200 decision trees) as a non-linear ensemble benchmark.
Evaluated stability using 5-fold stratified cross-validation on the training partition.
5. Model Evaluation & Interpretation
Compared held-out test performance across Accuracy (93.0%–93.9%), Precision (88.6%–92.7%), Recall (90.5%–92.9%), F1-Score (90.7%–91.6%), and ROC-AUC (0.982–0.985).
Inspected confusion matrices, ROC curves, standardized Logistic Regression coefficients, and Random Forest feature importances to verify that both models rely consistently on primary scale and structural irregularity features.
6. Strategic Recommendations & Documentation
Recommended a two-stage prioritization workflow: apply simple size-based thresholds for rapid initial filtering, and route ambiguous mid-range records to the interpretable Logistic Regression model and human review.
Documented limitations (sample size, lack of external validation) and outlined future enhancements, including expanded feature sets, hyperparameter tuning, probability calibration, and interactive BI dashboard integration.

Tech Stack
Programming Language: Python 3.10
Data Manipulation & Analysis: Pandas, NumPy
Machine Learning & Validation: Scikit-learn (Pipeline, StandardScaler, LogisticRegression, RandomForestClassifier, StratifiedKFold, train_test_split)
Data Visualization: Matplotlib, Seaborn
Environment & Reporting: Jupyter Notebook, Microsoft Word

Repository Structure
Final-Capstone-Project/
├── Final_Capstone_Project_Notebook.ipynb   # Reproducible Python code, EDA, visualizations, and model evaluation
├── Final_Capstone_Project_Report.docx      # Executive summary, visual findings, model comparison, and recommendations
└── README.md                               # Project documentation, methodology, and setup overview

Getting Started
Clone the Repository:
git clone https://github.com/SAMEDWORK/Final-Capstone-Project.git
cd Final-Capstone-Project
Install Dependencies:
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
Run the Analysis Notebook: Place the cleaned dataset CSV in the project root directory and launch Final_Capstone_Project_Notebook.ipynb in Jupyter Notebook, VS Code, or Google Colab to reproduce all figures and model metrics.
Review the Capstone Report: Open Final_Capstone_Project_Report.docx for the structured executive summary, visual walkthrough, and strategic recommendations.
