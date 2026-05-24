# Cervical Cancer Risk Prediction

## Project Overview

This project applies machine learning techniques to predict cervical cancer biopsy results using the Cervical Cancer Risk Factors dataset from the UCI Machine Learning Repository.

The main goal is to build and evaluate classification models that can predict whether a patient has a positive or negative biopsy result based on medical and behavioral risk factors.

The project is implemented and presented through a Jupyter Notebook.

---

## Dataset

The dataset used in this project is:

**Cervical Cancer Risk Factors Dataset**  
Source: UCI Machine Learning Repository

The dataset contains patient risk factor information such as:

- Age
- Number of sexual partners
- First sexual intercourse
- Number of pregnancies
- Smoking history
- Hormonal contraceptive usage
- IUD usage
- STDs history
- Previous diagnoses

The selected target variable is:

```text
Biopsy
````

Where:

```text
0 = Negative biopsy result
1 = Positive biopsy result
```

---

## Project Workflow

The project follows these main steps:

1. Dataset loading and exploration
2. Data cleaning and preprocessing
3. Missing value handling
4. Target variable selection
5. Class imbalance analysis
6. Train-test split
7. Baseline model training
8. Model evaluation using multiple metrics
9. Hyperparameter tuning using GridSearchCV
10. PCA dimensionality reduction comparison
11. Feature importance analysis
12. ROC curve and AUC visualization
13. Final model selection and conclusion

---

## Data Preprocessing

The dataset contained missing values represented by `?`.

These values were replaced with `NaN`, and the columns were converted to numeric format. Missing values were then handled using median imputation.

The diagnostic columns were reviewed carefully. `Biopsy` was selected as the target variable, while the other diagnostic result columns were removed from the feature set to avoid data leakage.

---

## Class Imbalance

The target variable was highly imbalanced:

```text
Class 0: 803 samples
Class 1: 55 samples
```

This means most patients had a negative biopsy result.

Because of this imbalance, accuracy alone was not considered enough to evaluate the models. More attention was given to:

* Recall
* Precision
* F1-score
* Confusion matrix
* ROC-AUC

---

## Models Used

Several classification models were trained and compared:

* Logistic Regression
* Decision Tree
* Random Forest
* Support Vector Machine
* K-Nearest Neighbors

After baseline evaluation, hyperparameter tuning was applied to:

* Random Forest
* Logistic Regression
* SVM

GridSearchCV was used for tuning.

---

## PCA Comparison

Principal Component Analysis was applied to reduce dimensionality while preserving 95% of the variance.

The PCA results were compared with the non-PCA models to check whether dimensionality reduction improved performance.

The results showed that PCA reduced the number of features but did not improve the final model performance.

---

## Final Model Selection

The final selected model was:

```text
Tuned SVM without PCA
```

Tuned SVM was selected because it achieved the best F1-score and tied for the highest recall among the tested models.

The final tuned SVM confusion matrix showed that it detected 4 out of 11 positive biopsy cases in the test set.

Although Random Forest achieved the highest accuracy and ROC-AUC, it detected fewer positive biopsy cases, making it less suitable for this imbalanced medical classification problem.

---

## Feature Importance

Random Forest feature importance was used to understand which features contributed most to prediction.

The most important features included:

* Age
* First sexual intercourse
* Hormonal Contraceptives (years)
* Number of pregnancies
* Number of sexual partners

These results represent model-based importance and should not be interpreted as medical causation.

---

## Technologies Used

* Python
* Jupyter Notebook
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn

---

## How to Run the Project

1. Clone the repository:

```bash
git clone https://github.com/kawthar-shameseldeen/Cervical-Cancer.git
```

2. Open the project folder.

3. Install the required libraries:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn notebook
```

4. Open the Jupyter Notebook:

```bash
jupyter lab
```

or:

```bash
jupyter notebook
```

5. Run the notebook cells in order.

---

## Project Presentation

The final project is presented directly from the Jupyter Notebook.

The notebook includes:

* Dataset explanation
* Preprocessing steps
* Visualizations
* Model training
* Evaluation results
* Hyperparameter tuning
* PCA comparison
* Feature importance
* Final conclusion

---

## Conclusion

This project showed that machine learning can be used to analyze cervical cancer risk factor data and predict biopsy results.

However, the dataset was highly imbalanced, which made positive biopsy prediction challenging. The tuned SVM model gave the best balance between recall and F1-score, making it the final selected model.

Future improvements could include using a larger and more balanced dataset, applying oversampling techniques such as SMOTE, testing advanced models such as XGBoost or LightGBM, and adjusting classification thresholds to improve positive case detection.

````

---

## Good commit message

After adding it, commit with:

```text
add project README
````

Also, since you are presenting from the notebook, make sure the notebook has clean markdown titles and that outputs/graphs are visible before presenting.
