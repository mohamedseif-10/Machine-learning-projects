
# Machine-learning-projects (OLD: 2024 at my early career)

These are small machine learning projects I did early in my career to learn and explore the field. They were training projects and I kept them even though I have better, more polished work now. I want to document these older notebooks so the experiments and lessons are preserved.

Overview
- 4 datasets used across the projects (Market basket analysis data, Telecom customer churn, Mall Customers Dataset, House prices prediction)
- 7 algorithms I experimented with across those datasets.
- Each project is implemented as one or more Jupyter Notebooks for preprocessing, model training, evaluation, and visualizations.
- The repo is intentionally lightweight and experimental think of it as a learning journal.

Quick note
These notebooks are from my early experiments. Some techniques maybe the most convinent and some are not I didn't know about topics like (data leakage, statistics and data distribution, Piplines and reproducable preprocessing for new input data, but later you will find more advanced techniques); the goal back then was to understand concepts rather than produce production-ready pipelines.

Projects and datasets
- Telecom Customer Churn (classification)
  - Algorithms used: Logistic Regression, Random Forest
  - What I learned: handling imbalanced classes, working with categorical variables, model evaluation (ROC, confusion matrix), and feature importance.
  - See: [Classification Task](https://github.com/mohamedseif-10/Machine-learning-projects/tree/main/Classification%20Task) — includes a detailed README for the churn project.

- Car Prices (regression)
  - Algorithms used: Random forest Regressor
  - What I learned: feature selection, baseline vs. complex models, evaluation with RMSE/MAE/R², and simple model interpretation.

- Mall Customer Segmentation (clustering)
  - Algorithms used: KMeans, DBSCAN
  - What I learned: how to standardize features for clustering, selecting k (elbow, silhouette), dimensionality reduction for visualization (PCA / t-SNE), and interpreting clusters.

- Market-basket / Groceries (association rules)
  - Algorithms used: Apriori (frequent itemset mining and association rules)
  - What I learned: transforming transactional data, mining frequent patterns, interpreting support/confidence/lift, and extracting actionable rules.

(That list totals 7 core algorithms I focused on across the 4 datasets: Logistic Regression, Random Forest Regressor and Classifier, KMeans, DBSCAN, FPGrowhs and Apriori.)

Implementation techniques, tools and patterns I used
- Data cleaning
  - Missing-value strategies (drop, simple imputation, KNN imputation where appropriate)
  - Duplicate removal and basic sanity checks
    
- Encoding categorical variables
  - Label encoding, binary mapping for two-level categoricals, and one-hot encoding for multilevel categories
- Feature engineering and transformations
  - Creating derived features, converting types (e.g., `TotalCharges` → numeric), binning where useful
- Scaling & dimensionality reduction
  - StandardScaler / MinMaxScaler, PCA and t-SNE for visualization and noise reduction
- Imbalance handling
  - SMOTE from imbalanced-learn for classification experiments
- Model training & evaluation
  - Train / test split, cross-validation (K-fold), GridSearchCV for simple hyperparameter tuning
  - Metrics: accuracy, precision, recall, F1, ROC-AUC for classification; RMSE, MAE, R² for regression; silhouette score for clustering
- Model pipelines and reproducibility
  - scikit-learn Pipelines to combine preprocessing and modeling steps
  - Saving models with joblib/pickle when needed
- Visualization and interpretation
  - matplotlib, seaborn plots for EDA and model diagnostics (confusion matrices, ROC curves, feature importances)
- Association rules-specific
  - Transaction encoding (one-hot), Apriori algorithm and filtering rules by support/confidence/lift
- Libraries I used commonly
  - pandas, numpy, scikit-learn, imbalanced-learn, mlxtend (for Apriori), matplotlib, seaborn, joblib/pickle, scipy

Why I kept these projects
- They were my hands-on introduction to:
  - The end-to-end ML workflow (EDA → preprocessing → modeling → evaluation)
  - The practical quirks of real datasets (dirty types, missing values, imbalance)
  - Basic model selection and simple hyperparameter tuning
- Even though the code is not state-of-the-art, the notebooks capture the learning process and are useful reference material.
- 
Tips when reproducing results
- Install the packages in the versions the notebooks were written for, or be prepared to adjust minor deprecated API calls/ Libraries - methods.
- Some notebooks may include cells that download or reference datasets externally you can find it in the data folder.
- If you want deterministic results, set random_state seeds in modeling and sampling calls.
