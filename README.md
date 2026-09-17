# Smart Lead Management

Smart Lead Management is a machine learning project focused on predicting which leads are most likely to convert into customers.

The project uses historical lead data from X Education and compares multiple classification models to support better lead prioritization.

## Project Overview

X Education receives a large number of leads from different sources, but only a portion eventually convert.

Treating every lead equally can increase sales effort without improving conversion. The objective of this project was to use historical customer and behavioural data to identify leads with a higher probability of conversion.

The project follows the CRISP DM process covering business understanding, data understanding, data preparation, modelling and evaluation.

## Dataset

The dataset contains historical lead information including customer profile, lead source, website activity and engagement information.

| Property                 |               Value |
| ------------------------ | ------------------: |
| Records                  |               9,240 |
| Initial features         |                  37 |
| Final processed features |                  75 |
| Target                   |           Converted |
| Converted leads          | Approximately 38.5% |
| Not converted leads      | Approximately 61.5% |

The dataset contains both numerical and categorical variables together with missing values that required preprocessing before modelling.

The original dataset is not included in this repository.

## Data Preparation

The notebook includes data understanding, missing value analysis, categorical feature processing, feature engineering and preparation of the final modelling dataset.

Categorical variables were transformed into machine readable features and the processed data was prepared for model training and evaluation.

Because the target classes are not perfectly balanced, model performance was evaluated using precision, recall, F1 score and ROC AUC rather than relying only on accuracy.

## Models

Three classification approaches were evaluated.

### XGBoost

XGBoost was used as an ensemble learning approach for lead conversion prediction.

The workflow includes model training, cross validation, hyperparameter tuning and evaluation using precision, recall, F1 score, ROC AUC and confusion matrices.

### Decision Tree

The Decision Tree model provides an interpretable approach to lead classification.

GridSearchCV with five fold stratified cross validation was used to tune parameters including tree depth, split criteria, minimum samples and class weighting.

The final notebook evaluation achieved approximately **93% accuracy** and a **0.963 ROC AUC** on the test set.

### Logistic Regression

Logistic Regression was used as an interpretable linear classification baseline.

The model workflow includes preprocessing, stratified cross validation and hyperparameter tuning using RandomizedSearchCV.

## Model Comparison

The three approaches produced similar overall performance, with XGBoost achieving the strongest F1 result in the project comparison.

| Model               | F1 Score |
| ------------------- | -------: |
| XGBoost             |    0.932 |
| Decision Tree       |    0.920 |
| Logistic Regression |    0.915 |

The comparison shows that all three models were able to identify useful patterns in the lead data while offering different tradeoffs between predictive performance and interpretability.

## My Contribution

My responsibility in the team project was the **Decision Tree model**.

I developed and evaluated the Decision Tree classification workflow, including baseline modelling, hyperparameter tuning with GridSearchCV, stratified cross validation, confusion matrix analysis, ROC analysis and decision path interpretation.

The model was designed not only to predict lead conversion but also to provide understandable decision rules that help explain why a lead was classified as converted or not converted.

## Technologies

Python
Pandas
NumPy
scikit learn
XGBoost
Decision Tree
Logistic Regression
GridSearchCV
RandomizedSearchCV
Matplotlib
Seaborn
Jupyter Notebook

## Repository Structure

```text
Smart-Lead-Management/
│
├── README.md
├── Smart_Lead_Management.ipynb
├── requirements.txt
├── .gitignore
│
└── docs/
    └── Project_Presentation.pdf
```

`Smart_Lead_Management.ipynb` contains the complete data preparation, modelling and evaluation workflow.

`Project_Presentation.pdf` contains the business context, methodology, model results and final project comparison.

## Running the Project

Install the required Python packages using:

```bash
pip install -r requirements.txt
```

Open the notebook using Jupyter:

```bash
jupyter notebook Smart_Lead_Management.ipynb
```

The dataset path in the notebook may need to be updated before running the project on another machine.

## Limitations

The project evaluates the models using the available historical lead dataset.

The results therefore reflect this dataset and should not be treated as guaranteed performance on future leads from a different distribution.

Deployment was discussed as future work but was not implemented as part of the completed project.

## Authors

Anjali Barvaliya
Adarsh Raj
TzuChing Lee

Hochschule Furtwangen University
Artificial Intelligence and Data Science for Digital Business Management
