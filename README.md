# Pima Indians Diabetes Prediction Using Machine Learning
NAME:RAMKISHOR M B
CSE - MEDICAL EMGINEERING
RA2411077050004
**Course:** Machine Learning in Medicine  
**Course Code:** 21CSC207J  
**Institution:** SRM Institute of Science and Technology, Tiruchirappalli  
**Assessment:** Task 2 — Machine Learning Model Implementation

## 1. Project Overview

This project implements and evaluates supervised machine learning models using the Pima Indians Diabetes Dataset to classify the dataset's diabetes outcome.

The objective is to study how clinical measurements and patient-related attributes can be used by machine learning algorithms to distinguish between the two outcome classes.

The project compares Logistic Regression and Random Forest using appropriate classification metrics and visualization techniques.

**Disclaimer:** This project is developed for academic and educational purposes only. It is not a clinically validated diagnostic system and must not be used to make medical decisions.

## 2. Problem Statement

Diabetes is an important healthcare concern, and identifying patterns associated with diabetes status is a relevant machine learning application.

This project investigates the following question:

**How effectively can supervised machine learning models classify the diabetes outcome using the available features in the Pima Indians Diabetes Dataset?**

The task is framed as a binary classification problem.

## 3. Dataset Description

The project uses the Pima Indians Diabetes Dataset.

The initial dataset inspection identified 768 records and nine columns: eight input features and one target column.

### Input features

- Pregnancies
- Glucose
- BloodPressure
- SkinThickness
- Insulin
- BMI
- DiabetesPedigreeFunction
- Age

### Target variable

- `Outcome = 0`: Negative outcome class in the dataset
- `Outcome = 1`: Positive outcome class in the dataset

The initial class distribution was:

| Outcome | Number of records | Percentage |
|---|---:|---:|
| 0 | 500 | 65.1% |
| 1 | 268 | 34.9% |
| Total | 768 | 100% |

The dataset contains zero values in some medical measurement columns. These require careful handling during preprocessing.

The dataset file is not included in this repository by default. Use the same dataset version selected for Task 1.

## 4. Machine Learning Models

### Logistic Regression

Logistic Regression is used as a baseline classification algorithm. It estimates the probability of belonging to a particular outcome class.

The pipeline includes median imputation and feature standardization.

### Random Forest Classifier

Random Forest is an ensemble learning algorithm that combines multiple decision trees. It can model nonlinear relationships between input features and the target.

The pipeline includes median imputation and class weighting.

Both models are evaluated using the same training and held-out test split.

## 5. Methodology

The workflow consists of the following stages:

1. Dataset loading and validation.
2. Inspection of data types, missing values, duplicate records and outcome distribution.
3. Removal of exact duplicate rows and invalid target records, where applicable.
4. Treatment of zero values in selected medical measurement columns as missing values, based on a documented dataset-specific assumption.
5. Stratified train/test split, using 80% of the data for training and 20% for testing.
6. Five-fold stratified cross-validation on the training data.
7. Median imputation fitted within each model pipeline.
8. Feature scaling within the Logistic Regression pipeline.
9. Model training and evaluation.
10. Visualization and export of evaluation results.

A fixed random seed of 42 is used to make the experiment more reproducible.

Preprocessing is fitted within the training pipelines to reduce the risk of data leakage.

## 6. Model Evaluation

The models are evaluated using the following metrics:

- **Accuracy:** Overall proportion of correct predictions.
- **Precision:** Proportion of positive predictions that are correct.
- **Recall:** Proportion of actual positive cases correctly identified.
- **F1-score:** Harmonic mean of precision and recall.
- **ROC-AUC:** Ability of the model to rank positive cases above negative cases across classification thresholds.

Confusion matrices and ROC curves are used to further inspect model performance.

Recall and false-negative errors receive particular attention because incorrectly classifying a positive case may have healthcare implications.

## 7. Experimental Results

The numerical results must be populated from the actual Google Colab execution.

The model comparison includes:

| Metric | Logistic Regression | Random Forest |
|---|---|---|
| Cross-validation accuracy | To be added | To be added |
| Cross-validation ROC-AUC | To be added | To be added |
| Test accuracy | To be added | To be added |
| Test precision | To be added | To be added |
| Test recall | To be added | To be added |
| Test F1-score | To be added | To be added |
| Test ROC-AUC | To be added | To be added |

The final discussion will compare the two models, examine their false-positive and false-negative errors, and identify the limitations of the experiment.

**Important:** Replace all placeholder values with the metrics generated by the completed notebook before submitting the repository.

## 8. Project Structure

The repository is organized as follows:

- `Pima_Diabetes_ML_Task2.ipynb` — Google Colab notebook containing data inspection, preprocessing, training and evaluation.
- `README.md` — Project documentation.
- `requirements.txt` — Python dependencies.
- `results/` — Generated metrics, experiment summary, predictions and evaluation plots.
- `.gitignore` — Files and folders excluded from Git tracking.

The actual filenames and paths should match the files uploaded to the repository.

## 9. How to Run the Project

### Google Colab

1. Open the notebook in Google Colab.
2. Upload the `diabetes.csv` dataset when prompted, or place it at the path expected by the notebook.
3. Run the notebook cells in order.
4. Inspect the generated evaluation metrics and plots.
5. Save the notebook with its completed outputs.
6. Upload the notebook and the relevant generated results to GitHub.

### Python environment

Install the dependencies listed in `requirements.txt`:

```bash
python -m pip install -r requirements.txt
```

The complete experiment can be reproduced by opening the notebook in Google Colab or a compatible Jupyter environment, providing the dataset and running the cells in sequence.

## 10. Limitations and Ethical Considerations

- The dataset has a limited population scope, so results may not generalize to other populations.
- Zero-value treatment is a preprocessing assumption that can influence model performance.
- A single held-out test split does not establish clinical validity.
- Cross-validation on the training data does not replace independent external validation.
- The project does not establish clinical safety, fairness, calibration or real-world usefulness.
- Predictions must not be used for diagnosis, screening or treatment decisions.

## 11. Conclusion

This project provides an experimental comparison of Logistic Regression and Random Forest for diabetes outcome classification using the Pima Indians Diabetes Dataset.

The completed evaluation will help assess the strengths and weaknesses of the two approaches using multiple classification metrics rather than accuracy alone.

The findings are limited to this academic experiment and should not be interpreted as evidence of clinical effectiveness.

## 12. Author

Developed as part of the Machine Learning in Medicine course at SRM Institute of Science and Technology, Tiruchirappalli.
