## Student Admission Conversion Prediction

## Objective

The objective of this mini project is to perform data preprocessing and exploratory data analysis for an AI-based student admission conversion prediction system. The project predicts whether an education lead is likely to convert into an admitted/enrolled student.

## Dataset

This project uses a Kaggle lead/admission conversion CSV file uploaded manually to Google Colab.

It is suitable for an admission conversion prediction project if the target variable is `Converted`, where:

- `0` means the lead did not convert
- `1` means the lead converted

Useful columns may include lead origin, lead source, last activity, lead tags, current occupation, total visits, total time spent on website, page views, and conversion status. The code automatically uses the columns available in your uploaded CSV.

## Files Included

- `admission_conversion_prediction.ipynb`: Main Google Colab/Jupyter notebook with EDA, preprocessing, and a baseline model.
- `admission_conversion_prediction_colab.py`: Google Colab friendly code for loading the dataset, EDA, preprocessing, and baseline model training.
- `README_admission_conversion_prediction.md`: Project documentation.

## EDA Steps

The notebook/script covers the following EDA steps:

- Load the uploaded Kaggle CSV file in Google Colab
- Check dataset shape, columns, data types, and sample records
- Analyze missing values
- Check duplicate records and unique values
- Study the target variable distribution
- Visualize converted vs not converted leads
- Analyze top categories in lead origin, lead source, last activity, tags, and occupation
- Compare conversion rate across categorical features

## Preprocessing Steps

The preprocessing workflow includes:

- Renaming columns into clean Python-friendly names
- Filling missing categorical values
- Removing the unique prospect ID from model training
- Grouping rare categories as `Other`
- Splitting data into training and testing sets using stratification
- Applying one-hot encoding to categorical features
- Applying median imputation and scaling to numerical features, if numerical columns are present
- Building a reusable `ColumnTransformer` preprocessing pipeline

## Baseline Model

A simple Logistic Regression model is included as a baseline AI/ML model. Logistic Regression is a good first model for this project because it is easy to understand and works well for binary classification problems.

Note: In a real admission CRM, columns such as lead tags or last activity may be updated after counselor follow-up. If those fields are created after the final admission decision, remove them before model training to avoid data leakage.

The model is evaluated using:

- Accuracy
- Precision
- Recall
- F1 Score
- ROC AUC
- Confusion Matrix

## How to Run in Google Colab

1. Open Google Colab.
2. Upload `admission_conversion_prediction.ipynb`, or upload/copy `admission_conversion_prediction_colab.py` into a new notebook.
3. Run the notebook cells from top to bottom.
4. When Colab shows the upload button, upload your Kaggle CSV file.

If you already uploaded the CSV to Colab manually, set `CSV_FILE_PATH` near the top of the notebook. Example:

```python
CSV_FILE_PATH = "/content/Lead Scoring.csv"
```

The script will also save cleaned train and test CSV files:

- `admission_conversion_train_clean.csv`
- `admission_conversion_test_clean.csv`

## Suggested Project Title

**AI-Based Student Admission Conversion Prediction System**

## Suggested Problem Statement

Educational institutions receive many student leads from websites, social media, referrals, and campaigns. Not every lead converts into an admitted student. This project analyzes lead behavior and builds a preprocessing pipeline that can help predict whether a student lead is likely to convert, allowing admission teams to prioritize high-potential leads.
