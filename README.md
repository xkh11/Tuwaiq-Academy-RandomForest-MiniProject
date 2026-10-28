# Breast Cancer Classification Using Random Forest

This is our mini project for Tuwaiq Academy. We used a **Random Forest Classifier** to predict whether a breast tumor is **malignant** (cancer) or **benign** (not cancer).

## Dataset

We used the [Breast Cancer Wisconsin (Diagnostic)](https://archive.ics.uci.edu/dataset/17/breast+cancer+wisconsin+diagnostic) dataset from the UCI Machine Learning Repository.

- 569 patients
- 30 numerical features that describe the cell nuclei of the tumor (like radius, area, texture and concave points)
- Target: `diagnosis` (M = Malignant, B = Benign)
- 357 benign (63%) and 212 malignant (37%), so the data is a bit imbalanced

## The Problem

Missing a cancer is much worse than a false alarm, so in this project we focused on **recall** (how many cancers the model finds), not only accuracy.

## What We Did

1- **EDA:** explored the data, checked missing values, and used plots to see how the features are different between benign and malignant tumors.

2- **Preprocessing:** removed the empty and `id` columns, encoded the target (M = 1, B = 0), checked duplicates and outliers, and split the data 80% train and 20% test.

3- **Model Training:** trained a Random Forest and tested it with 5-fold cross validation on the training set.

4- **Class Imbalance:** used `class_weight='balanced'` to give more weight to the malignant class.

5- **Hyperparameter Tuning:** used grid search to find the settings with the best recall.

6- **Evaluation:** tested the final model on the test set (used only once at the end).

7- **Model Comparison:** compared Random Forest with Decision Tree, Logistic Regression, KNN and SVM.

## Results

Final model on the test set:

| Accuracy | Precision | Recall | F1 |
|---|---|---|---|
| 97.4% | 1.000 | 0.929 | 0.963 |

## Key Insights

1- Tuning reduced the missed cancers in cross validation from 10 to 7.

2- On the test set the model had 0 false alarms and missed 3 cancers out of 42.

3- The most important features are about the size and shape of the cell nucleus (`area_worst`, `concave points_worst`, `concave points_mean`).

4- Random Forest was much better than a single Decision Tree, and as good as the best models we tried.

5- The model should help doctors, not replace them, because it can still miss some cancers.

## Files

- `Breast_Cancer_Random_Forest.ipynb`: the full notebook with all the code, plots and insights
- `data.csv`: the dataset

## How to Run

1- Open the notebook in Google Colab or Jupyter.

2- Upload `data.csv` next to the notebook.

3- Run all the cells from top to bottom.

## Team

- Khalid Alotaibi
- Ghadi Alshahrani
- Omar
- Lama
