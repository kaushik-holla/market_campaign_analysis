# market_campaign_analysis
This repository contains the analysis and predictive modeling of marketing campaigns aimed at predicting future donations. The project involves classification and regression tasks to improve the effectiveness of marketing campaigns.

## Table of Contents

- [Introduction](#introduction)
- [Folder Structure](#folder-structure)
- [Data Description](#data-description)
- [Installation](#installation)
- [Usage](#usage)
- [Models and Techniques](#models-and-techniques)
- [Results](#results)
- [Recommendations for Improvement](#recommendations-for-improvement)


## Introduction
<b>Problem Statement:</b> Effectively Identifying Donors for mailing campaigns and forecast/predict the expected total donations receivable from these campaigns <br>
<br>
# Goals:
<b>1. Targeting Donors: </b>Identifying donars who are most likely to donate in response to a mailing campaign <br>
<b>2. Donation Prediction: </b>Estimating the total revenue from the mailing campaign <b>
<br>

## Folder Structure
- `data/`: Contains the datasets.
- `notebooks/`: Contains Jupyter Notebooks for each step of the analysis.
- `scripts/`: Contains .py scripts used for data processing, analysis and building predictive models.
- `models/`: Contains saved models.
- `results/`: Contains generated figures and results from the analysis.

## Data Description

The dataset used in this project contains information about past marketing campaigns and donor behaviors. The main columns in the dataset include:

- `donated`: Binary target variable indicating donor (1) or non-donor (0) which was feature engineered considering other donations.
- `TARGET_D6`, `TARGET_D12`, `TARGET_D18`, `TARGET_D24`: Target variables indicating the amount of donation over 6, 12, 18, and 24 months, respectively.
- Various features such as demographic information, past donation behavior, and campaign interactions.

## Installation

To set up the project environment, follow these steps:

1. Clone the repository:

```bash
git clone https://github.com/kaushik-holla/market_campaign_analysis.git
cd market_campaign_analysis
```

2. Create a virtual environment and activate it:

```bash
python -m venv venv
source venv/bin/activate 
```

3. Install the required dependencies:

```bash
pip install -r requirements.txt
```

## Usage

The notebooks folder contains Jupyter notebooks that guide you through the different stages of the Market Campaign Analysis project. To get the most comprehensive understanding, it is recommended to read through the notebooks in the following order:

1. data_prep.ipynb:
This notebook covers the initial data preparation steps, including data loading, handling missing values, and data cleaning processes. It ensures that the dataset is in a suitable format for analysis and modeling.

2. EDA.ipynb:
The Exploratory Data Analysis (EDA) notebook delves into the data to uncover patterns, relationships, and insights. This notebook includes various visualizations and statistical summaries that help understand the underlying structure and distribution of the data.

3. Modeling.ipynb:
This notebook focuses on the development and evaluation of classification models to identify donors. It includes feature engineering, model training, hyperparameter tuning, and evaluation metrics. Techniques to handle class imbalance, such as SMOTE and downsampling, are also explored.

4. regression.ipynb:
The final notebook addresses the regression tasks aimed at predicting future donation amounts over different time periods (6, 12, 18, and 24 months). It covers model training and performance evaluation using metrics like Mean Squared Error (MSE) and R² score.


## Models and Techniques
#### Classification

XGBoost Classifier: Used to classify donors and non-donors with a focus on maximizing recall.
Tried SMOTE and Downsampling, Techniques used to handle class imbalance.

#### Regression
XGBoost Regressor: Used to predict the amount of donations over different periods (6, 12, 18, and 24 months).


## Results
The results of the classification and regression models, including evaluation metrics like precision, recall, F1-score, MSE, and R² score, are documented in the respective Jupyter notebooks and the results section of the project.

### Classification Report

The classification report provides detailed metrics on the performance of the classification model. The metrics include precision, recall, F1-score, and support for each class. Below is an example of a classification report generated from the model:

```mathematica
              Precision    Recall  F1-score   Support

           0       0.98      0.69      0.81      3782
           1       0.12      0.79      0.20       197

    accuracy                           0.69      3979
   macro avg       0.55      0.74      0.51      3979
weighted avg       0.94      0.69      0.78      3979
```

##### Classification model Conclusion:

1. Metric:
    From the dataset, we observed that only about 5% of the individuals are donors. To ensure that our mailing campaign effectively reaches these potential donors, I prioritized recall as our primary evaluation metric.

2. Model Performance:
    The model was trained with a focus on increasing recall. On an unseen dataset, the model achieved a recall of 79% for the donor class. This means that the model successfully identified 79% of the actual donors.
    The model also demonstrated a high precision of 98% for the non-donor class, effectively rejecting non-donors while capturing the majority of donors.

3. Trade-off Between Precision and Recall:
    While there is a trade-off with precision for the donor class (12%), the model's ability to capture the majority of actual donors (recall of 79%) makes it a valuable tool for enhancing our donor targeting strategy.
    This trade-off can be acceptable given the critical need to maximize donor engagement and increase donations. By capturing a higher percentage of potential donors, we can significantly enhance the effectiveness of our mailing campaigns.

### Regression Report
The regression task aimed to predict future donations over different time periods (6, 12, 18, and 24 months) based on historical donor data and various features.

```mathematica
6-months : MSE = 157799.96906646877, R2 = -0.30142331260039
12-months: MSE = 1274562.6688466398, R2 = -0.12804561817273719
18-months: MSE = 2958108.4606587244, R2 = -0.2996013075000741
24-months: MSE = 2821463.0745740645, R2 = -0.008328069304253782
```
##### Regression model Conclusion:

1. High MSE Values: 
    The high MSE values indicate that the predicted donation amounts are significantly deviating from the actual donation amounts. This suggests that the models are not accurately capturing the patterns in the data to make precise predictions.

2. Negative R² Scores: 
    The negative R² scores across all time periods indicate that the models are performing worse than a simple mean prediction. An R² score of 1 is ideal, 0 indicates the model is as good as a mean prediction, and negative values suggest the model is worse than using the mean as the prediction.

3. Model Ineffectiveness: 
    The regression models, as they currently stand, are ineffective for predicting future donations. The high MSE and negative R² scores suggest that the currently used models are not able to capture the underlying relationships between the features and the target variables.

## Recommendations for Improvement
