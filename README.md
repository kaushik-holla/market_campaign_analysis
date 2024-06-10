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
- [Contributing](#contributing)
- [License](#license)

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