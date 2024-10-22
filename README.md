
# Lead Scoring Case Study

This repository contains a case study focused on predicting lead conversion for a business using machine learning models. The primary objective is to identify key factors that lead to higher conversions and build a predictive model.

## Table of Contents

- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Installation and Setup](#installation-and-setup)
- [Data Preprocessing](#data-preprocessing)
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis)
- [Model Building](#model-building)
- [Model Evaluation](#model-evaluation)
- [Conclusion](#conclusion)
- [Graphs](#graphs)

---

## Project Overview

In this project, we aim to analyze customer lead data to predict the likelihood of a customer converting. The analysis includes exploratory data analysis (EDA), feature engineering, model building, and evaluation.

## Dataset

The dataset includes information about leads such as their email behavior, source of the lead, current occupation, and activity on the website. Key columns include:

- **Do Not Email**
- **Total Time Spent on Website**
- **Lead Source**
- **Last Activity**
- **Specialization**
- **What is your current occupation?**
- **Last Notable Activity**

## Installation and Setup

To run the notebook and reproduce the analysis, follow these steps:

1. Clone the repository:
    ```bash
    git clone https://github.com/your-repo-name/lead-scoring-case-study.git
    ```

2. Install the necessary dependencies:
    ```bash
    pip install -r requirements.txt
    ```

3. Open the Jupyter notebook:
    ```bash
    jupyter notebook lead_scoring_case_study.ipynb
    ```

## Data Preprocessing

We performed the following preprocessing steps:

1. **Missing Values Treatment**:
   Missing values in the dataset were handled by either removing them or imputing them with appropriate values.

2. **Feature Encoding**:
   Categorical variables such as `Lead Origin`, `Lead Source`, and `Specialization` were encoded using techniques such as one-hot encoding.

3. **Boolean Conversion**:
   All boolean columns were converted to integers (`0` and `1`).

4. **Feature Scaling**:
   Numerical features were standardized to ensure uniformity across the dataset.

## Exploratory Data Analysis (EDA)

We performed an EDA to understand the distribution of data and identify important patterns.

- **Graph 1**: Distribution of Total Time Spent on Website.
  
  _Label: Insert graph showing the distribution of the total time spent on the website._

- **Graph 2**: Conversion rate by Lead Source.
  
  _Label: Insert graph showing the conversion rate for each lead source._

- **Graph 3**: Conversion rate by Last Activity.
  
  _Label: Insert graph showing the conversion rate for the last activity performed by leads._

## Model Building

We used the following models to predict lead conversion:

- **Logistic Regression**:
  A baseline model for binary classification tasks.
  
- **Decision Trees**:
  To capture non-linear relationships between features.
  
- **Random Forest**:
  An ensemble technique to improve model performance.

The final dataset was split into training and testing sets. Recursive Feature Elimination (RFE) was applied for feature selection.

### Code Snippet:
Here’s how RFE was applied to select the most important features:

```python
from sklearn.feature_selection import RFE
from sklearn.linear_model import LogisticRegression

model = LogisticRegression()
rfe = RFE(model, 10)
fit = rfe.fit(X_train, y_train)
```

## Model Evaluation

We evaluated the models using the following metrics:

- **Accuracy**: The proportion of correctly classified leads.
- **Precision and Recall**: To measure the quality of positive predictions.
- **F1-Score**: A balance between precision and recall.

- **Graph 4**: ROC Curve of the models.
  
  _Label: Insert ROC curve comparison between models._

## Conclusion

Based on the analysis, we identified the following key factors that influence lead conversion:

1. **Time Spent on Website**: Leads who spent more time on the website were more likely to convert.
2. **Lead Source**: The source of the lead played a significant role in determining the likelihood of conversion.
3. **Last Activity**: Certain activities like `Olark Chat` and `SMS Sent` had higher conversion rates.

We also found that the Random Forest model performed the best, achieving the highest accuracy and F1-score.

## Graphs

Make sure to place the following graphs in the appropriate sections of the notebook:
**Note** : - 1-> Yes  -0 -> No
1. [Distribution of Total Time Spent on Website!](src/total_time_spent_on_web.png)
2. [Conversion rate by Lead Source](src/lead_source_conversion.png)
3. [Conversion rate by Last Activity](src/last_acitvity_conversion.png)
4. [ROC Curve comparison for Logistic Regression](src/ROC_Curve_Logistic_Regression.png)

---


