README

						Employee Attrition Prediction using Custom KNN and Ensemble Learning

1. PROJECT DESCRIPTION:

This project is part of a machine learning homework assignment aimed at predicting employee attrition (whether an employee leaves the company) using a real-world HR dataset. The core implementation includes a custom K‑Nearest Neighbors (KNN) classifier built from scratch, along with preprocessing steps like handling imbalanced classes via SMOTE + Tomek and undersampling. The notebook explores data cleaning, feature engineering, model tuning, and evaluation. Although the assignment also mentions Random Forest, Bagging, and AdaBoost, the provided code focuses on a detailed custom KNN implementation and provides a foundation for comparing these ensemble methods.

2. SKILLS AND KNOWLEDGE DEMONSTRATED:

- Data preprocessing (handling missing values, removing constant columns, label encoding, scaling)
- Handling imbalanced datasets using SMOTE and RandomUnderSampler
- Implementing a KNN classifier from scratch with Euclidean distance and majority voting
- Hyperparameter tuning (choosing optimal k for accuracy and recall)
- Model evaluation using accuracy, recall, F1‑score, confusion matrices, and classification reports
- Visualizing decision boundaries after PCA dimensionality reduction
- Detecting overfitting/underfitting by comparing train and test performance
- Correlation analysis and exploratory data visualizations (heatmaps, line plots, bar charts)
- Using Python libraries: pandas, numpy, scikit‑learn, imbalanced‑learn, matplotlib, seaborn

3. REAL‑WORLD APPLICATIONS:

- HR analytics: Identify employees at risk of leaving to enable proactive retention strategies.
- Workforce planning: Understand key drivers of turnover (e.g., job level, years at company, monthly income).
- Talent management: Reduce unexpected attrition costs and preserve institutional knowledge.
- The approach can be extended to other binary classification problems with imbalanced classes, such as fraud detection, customer churn, or disease diagnosis.

4. LIBRARIES AND TOOLS USED:

- pandas & numpy – data manipulation and numerical operations
- scikit‑learn – preprocessing (StandardScaler, LabelEncoder), train‑test split, metrics (accuracy, recall, classification_report, confusion_matrix), PCA for visualization
- imbalanced‑learn – SMOTE, SMOTETomek, RandomUnderSampler for class balancing
- matplotlib & seaborn – static and interactive visualizations (heatmaps, line plots, confusion matrices, decision region plots)

5. CODE STRUCTURE AND WORKFLOW:

- Data Loading & Exploration:

  - Display dataset info, summary statistics, missing values, target distribution.
  - Drop columns with less than 2 unique values (EmployeeCount, Over18, StandardHours).
  - Analyze MonthlyIncome vs. YearsAtCompany and department‑wise income.
  - Correlation heatmap to identify features related to attrition.

- Data Preprocessing:

  - Label encode all categorical variables.
  - Split into training (70%) and test (30%) sets with stratification.
  - Scale features using StandardScaler.
  - Apply SMOTETomek + RandomUnderSampler to balance the training set (target ratio 0.8).

- Custom KNN Implementation:

  - Class `CustomKNN` with methods `fit`, `predict`, `_predict`, `euclidean_distance`.
  - Evaluate on test set for k from 1 to 25.
  - Record best k based on accuracy and best k based on recall for the positive (attrition) class.

- Evaluation & Diagnostics:

  - Accuracy and recall curves across k values.
  - Confusion matrices and classification reports for best accuracy and best recall models.
  - Check overfitting by evaluating on original training data and resampled training data.

- Visualization:

  - Decision boundaries after PCA (2 principal components) for both best accuracy and best recall models.
  - Explain why recall is prioritized over accuracy for attrition prediction (cost of false negatives).

- Conclusion: Summarize findings, best parameters, and trade‑offs.

6. RESULTS AND OBSERVATIONS:

- Best accuracy model achieved with k = 6, accuracy ≈ 68.3%, recall for attrition ≈ 65%.
- Best recall model achieved with k = 11, recall for attrition ≈ 75.4% (accuracy lower, around 63%).
- Confusion matrices show that resampling increased true positives but also increased false positives.
- Decision boundary plots after PCA illustrate how different k values affect the classification regions.
- The project highlights the importance of choosing the right metric – recall is crucial because missing a potential leaver (false negative) is more costly than flagging a false positive.

7. CONCLUSION:

This homework successfully implements a custom KNN classifier for employee attrition prediction. It demonstrates a full machine learning pipeline: data cleaning, handling imbalance, custom algorithm implementation, hyperparameter tuning, and thorough evaluation. The analysis shows that recall can be prioritised over accuracy when the business goal is to capture as many at‑risk employees as possible. The work can be extended to compare KNN with ensemble methods (Random Forest, Bagging, AdaBoost) to improve predictive performance. The visualisations and evaluation metrics provide clear insights into model behaviour and real‑world applicability.

8. HOW TO RUN THE CODE

1. Install required libraries: `pip install pandas numpy scikit-learn imbalanced-learn matplotlib seaborn`
2. Ensure the dataset file "dataset.csv" is in the same directory as the notebook.
3. Run the notebook cells sequentially.
4. Adjust random states and sampling strategies as needed.

Author of the notebook and owner of datasets : Dr. Amirali Ghafourian Ghahraman

Programmer of the notebook and author of README: Fereshteh Zahra Hossain

License: Open for educational and portfolio use.