# 🩺 Diabetes Prediction

A beginner-friendly machine learning classification project that predicts whether a person has diabetes using multiple classification algorithms and compares their performance to select the best model.

## 📌 Project Overview

The goal of this project is to build a classification model capable of predicting whether an individual has diabetes based on health-related features such as glucose level, blood pressure, BMI, insulin, age, and other medical measurements.

Instead of relying on a single algorithm, several classification models are trained, evaluated, and compared using accuracy and 5-fold cross-validation.

## 📊 Dataset

The dataset contains health-related information about individuals, including:

- Glucose
- Blood Pressure
- Skin Thickness
- Insulin
- BMI
- Age
- Pregnancies
- Diabetes Pedigree Function

**Target variable:** `Outcome`

- `0` → Non-Diabetic
- `1` → Diabetic

**Dataset source:**  
Kaggle Diabetes Dataset

## 🤖 Models Used

The following classification models are compared:

- Logistic Regression
- K-Nearest Neighbors (KNN)
- Support Vector Machine (SVM)
- Kernel SVM
- Naive Bayes
- Decision Tree Classification
- Random Forest Classification

## 🔧 Project Workflow

1. Load and explore the dataset
2. Understand the dataset structure and statistics
3. Check for missing values and duplicates
4. Identify invalid zero values
5. Replace invalid zero values with missing values
6. Handle missing values using median imputation
7. Detect and cap outliers using the IQR method
8. Separate features and target
9. Split the data into training and test sets
10. Apply feature scaling where needed
11. Train multiple classification models
12. Evaluate the initial model performance
13. Apply 5-fold cross-validation
14. Compare the models
15. Select the best-performing model based on cross-validation accuracy
16. Generate a confusion matrix for the best model
17. Evaluate the final model on the test set

## ⚙️ Data Preprocessing

Several preprocessing steps are applied before training the models.

### Handling Invalid Zero Values

Some medical measurements contain zero values that are not medically meaningful, such as:

- Glucose
- Blood Pressure
- Skin Thickness
- Insulin
- BMI

These zero values are replaced with `NaN` and then filled using the median value of each feature.

### Outlier Handling

Outliers are detected using the **Interquartile Range (IQR)** method.

Instead of removing the outliers, their values are capped at the calculated lower and upper IQR boundaries.

### Feature Scaling

Feature scaling is applied using `StandardScaler`.

Scaling is used for:

- Logistic Regression
- KNN
- SVM
- Kernel SVM

Scaling is not required for:

- Naive Bayes
- Decision Tree
- Random Forest

## 📊 Evaluation

The models are initially evaluated using **Accuracy** on the test set.

The models are then evaluated using **5-fold cross-validation** on the training data.

### Accuracy

**Accuracy** measures the percentage of predictions that the model classified correctly.

Higher accuracy indicates better classification performance.

### Confusion Matrix

A confusion matrix is generated for the model with the highest mean cross-validation accuracy.

It contains:

- **True Positive (TP):** Predicted diabetic and actually diabetic
- **True Negative (TN):** Predicted non-diabetic and actually non-diabetic
- **False Positive (FP):** Predicted diabetic but actually non-diabetic
- **False Negative (FN):** Predicted non-diabetic but actually diabetic

## 🏆 Best Model (KNN)

The best model is selected based on the **highest mean accuracy from 5-fold cross-validation**.

The notebook automatically identifies the best-performing model and generates a confusion matrix for its test-set predictions.

### Cross-Validation Results

The notebook compares the following models using 5-fold cross-validation:

| Model | Mean CV Accuracy |
|---|---:|
| K-Nearest Neighbors (KNN) | **77.77%** |
| Support Vector Machine (SVM) | 77.08% |
| Random Forest | 76.55% |
| Logistic Regression | 76.21% |
| Naive Bayes | 76.20% |
| Kernel SVM | 75.51% |
| Decision Tree | 72.56% |

The model with the highest **Mean CV Accuracy** is selected as the final model.

### Final Test Results

The selected model is then evaluated on the unseen test set.

| Metric | Score |
|---|---:|
| Test Accuracy | **75.52%** |

## 🛠️ Technologies & Libraries

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Google Colab

## 📂 Project Structure

```text
Diabetes-Prediction/
│
├── Diabetes_Prediction.ipynb
└── README.md
```

## 🚀 How to Run

1. Clone or download this repository.
2. Open `Diabetes_Prediction.ipynb` in Google Colab or Jupyter Notebook.
3. Make sure the `diabetes.csv` dataset is available.
4. Run the cells from top to bottom.
5. Review the model evaluation and comparison results.
6. Examine the confusion matrix of the best-performing model.

## 🎯 What I Learned

Through this project, I practiced:

- Data exploration
- Data preprocessing
- Handling invalid values
- Handling missing values
- Outlier detection and capping
- Feature scaling
- Classification modeling
- Model evaluation
- Accuracy measurement
- Cross-validation
- Confusion matrix analysis
- Model comparison
- Selecting a final machine learning model

## 📌 Conclusion

This project demonstrates a complete beginner-level machine learning classification workflow, from data exploration and preprocessing to model training, cross-validation, model comparison, and final evaluation.

Seven different classification algorithms were tested, and **5-fold cross-validation accuracy** was used to determine the best-performing model.

The selected model is then evaluated on the unseen test set, and its predictions are analyzed using a confusion matrix.

---

**Built as a machine learning practice project.**
