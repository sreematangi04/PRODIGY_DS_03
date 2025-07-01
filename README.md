# Task 3: Decision Tree Classification on the Bank Marketing Dataset

## Objective
The objective of this task is to analyze the Bank Marketing dataset and build a Decision Tree Classifier to predict whether a client will subscribe to a term deposit. Two types of decision tree algorithms are implemented and compared: ID3 (based on entropy) and CART (based on Gini index).

The project covers data preprocessing, exploratory data analysis (EDA), class balancing using SMOTE, model training, evaluation, and visualizations to assess performance.

---

## Dataset Overview
The dataset used is `bank-additional-full.csv`, which contains both categorical and numerical variables related to client information and outcomes from previous marketing campaigns.

The target variable is `y`, indicating whether the client subscribed to a term deposit (`yes` or `no`).

---

## Data Preprocessing
- The `duration` column was removed as advised in the dataset documentation.
- Categorical features were encoded using one-hot encoding.
- SMOTE (Synthetic Minority Over-sampling Technique) was applied to address class imbalance in the target variable.

---

## Exploratory Data Analysis (EDA)
To understand the data distribution and relationships, several visualizations were created:

- **Target variable distribution:** Showed class imbalance in subscription (`y`).
- **Subscription rates by job, marital status, and education level.**
- **Age distribution:** Displayed a concentration of clients in certain age groups.
- **Correlation heatmap:** Identified relationships among encoded numerical features.

**Insights from EDA:**
- Subscription rates varied significantly across job types. For instance, retired and student clients had higher subscription rates.
- Education level was positively associated with subscription probability.
- Contact type, campaign outcomes, and recent economic variables were potential predictors.

---

## Model 1: ID3 Decision Tree (Entropy)
- Parameters: `max_depth=5`, `min_samples_split=20`, `min_samples_leaf=10`, `class_weight='balanced'`
- Trained on SMOTE-balanced dataset
- Evaluated using:
  - Cross-validation accuracy: **0.759**
  - Classification report
  - Confusion matrix
  - ROC curve and AUC
  - Feature importance plot

**Performance:**
- Provided good interpretability and balanced accuracy after handling class imbalance.
- Important features included `poutcome`, `contact`, and campaign-related metrics.

---

## Model 2: CART Decision Tree (Gini)
- Same parameters as the ID3 model but using `criterion='gini'`
- Evaluated using:
  - Cross-validation accuracy: **0.758**
  - Classification report
  - Confusion matrix
  - ROC curve and AUC
  - Feature importance plot

**Observations:**
- Performed comparably to the ID3 tree.
- Feature splits were slightly different but core insights remained consistent.

---

## Model Comparison

| Metric                 | ID3 (Entropy) | Gini (CART) |
|------------------------|---------------|-------------|
| Cross-Validation Accuracy | 0.759         | 0.758       |
| ROC-AUC Score          | Moderate      | Moderate    |
| Tree Depth             | 5             | 5           |
| Number of Leaves       | Similar       | Similar     |

---

## Conclusion
- Both decision tree models showed similar performance and provided interpretable results.
- The slight difference in accuracy and feature splitting reinforces the consistency of influential predictors.
- Future improvements could involve feature engineering or ensemble learning to further improve performance.

---

## Potential Extensions
- Hyperparameter tuning using GridSearchCV.
- Explore ensemble models like Random Forest or Gradient Boosting.
- Integrate external economic indicators for enhanced context.
- Apply SHAP for advanced interpretability.

---

## Tools and Libraries Used
- Python 3.11
- pandas
- matplotlib
- seaborn
- scikit-learn
- imbalanced-learn (SMOTE)
- graphviz

---

## Acknowledgement
This project was developed as part of Task 3 for the Data Science Internship at Prodigy Infotech.