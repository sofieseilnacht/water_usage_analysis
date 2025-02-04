# Water Usage Analysis

This project analyzes water flow data across District Metered Areas (DMAs) to identify anomalies and understand water usage patterns. The study focuses on detecting irregularities in water flow that may indicate leaks, inefficiencies, or sensor errors. By utilizing data-driven visualizations and machine learning models, we provide actionable insights for water management.

## Overview

The purpose of this script is to:

- Train an ML model to classify text into predefined categories (Hate Speech, Offensive Language, Neutral).
- Apply NLP techniques such as tokenization, class reweighting, and word embeddings to improve classification accuracy.
- Experiment with Hugging Face models, including DistilBERT, to optimize text processing and classification.
- Evaluate model performance using key metrics: precision, recall, F1-score, and accuracy.

## Table of Contents

1. [Overview](#overview)
2. [Getting Started](#getting-started)
3. [Dependencies](#dependencies)
4. [Dataset](#dataset) 
5. [Class Imbalance](#class-imbalance)
6. [How It Works](#how-it-works)
7. [Data Preprocessing](#data-preprocessing)
8. [Model Training & Optimization](#model-training-&-optimization)
9. [Evaluation](#evaluation)
10. [Challenges in Hate Speech Classification](#challenges-in-hate-speech-classification)
11. [Future Improvements](#future-improvements)

# Getting Started

To run this code, you just need to run each cell within the Jupyter Notebook, ensuring that you have the proper csv file name/path to upload the data.

## Dataset

The dataset is a CSV file containing 974,934 rows of water flow data. The data includes some missing values and features the following column headers:

|Column Name	| Description	| Data Type |
|-------------|---------------|-----------|
| DATA_SOURCE | The company that owns the DMA. A District Metered Area (DMA) is a manageable sector of the water distribution network used for monitoring and leak detection. | String |
| DATE/TIME_STAMP | Date and time of the measured net flow. (Note: Ignore the time.) | DateTime (UTC) |
| DMA_ID | The unique identity of the DMA. Used to guide water providers in detecting leaks or inefficiencies within specific areas. | String |
| CENTROID_X | The X-coordinate of the DMA centroid. | Decimal |
| CENTROID_Y | The Y-coordinate of the DMA centroid. | Decimal |
|ACTUAL_MIN_NIGHT_FLOW | The lowest recorded net flow between 12 a.m. and 6 a.m. | Float |
| MIN_NIGHT_FLOW | The averaged 15-minute flow between 3 a.m. and 4 a.m., when customer demand is at its lowest, enabling the detection of potential leaks. | Float |
| UNITS | The unit of measurement for flow. | String | 


## Class Imbalance


# How It Works

## Data Preprocessing



## Model Training & Optimization:


## Evaluation:


# Challenges in Hate Speech Classification


#### Context Dependence:


#### Detection of Sarcasm & Irony:


#### Class Imbalance & Label Ambiguity:



#### Challenges with Coded & Subtle Hate Speech:


# Future Improvements
 


# Data-Driven Insights: Anomaly Detection and Water Usage Patterns


Data Exploration and Preprocessing

Initial data exploration focused on basic statistics and anomaly identification, including handling missing values and negative flow values that could signal sensor malfunctions or system inefficiencies. These steps were crucial for ensuring data integrity before applying machine learning models.

Visualizations

To better understand the data and highlight key patterns, several visualizations were generated:

Actual vs. Expected Minimum Night Flow Scatterplot – Highlights deviations from expected values, which may indicate leaks or inefficiencies.

Index vs. Actual Minimum Night Flow Plot – Identifies and visualizes negative flow values, showing their frequency and distribution.

Geographic Distribution of DMAs with Negative and Missing Flow – Maps out areas experiencing persistent negative or missing flow values.

High and Medium Priority Regions Map – Displays regions where negative flow values occur frequently, helping prioritize investigation.

Map of Missing Data Locations – Pinpoints geographic areas with missing data, which may be due to faulty sensors or data collection issues.

These visuals provide clear spatial and temporal insights into water anomalies, enabling targeted analysis of key problem areas.

Model Selection

For anomaly detection and water usage analysis, Random Forest Classification (RFC) was chosen due to its ability to:

Handle complex, non-linear relationships in the data.

Provide feature importance insights, helping prioritize key variables.

Resist overfitting, which is particularly important given the imbalance in the dataset.

Be easy to implement and flexible, making it a practical choice within project constraints.

To address class imbalance, oversampling techniques were used to ensure fair representation of anomalies in the dataset.

Anomaly Detection Model Results

The anomaly detection model achieved 100% accuracy.

Despite the high accuracy, the dataset was highly imbalanced, with significantly more normal flow instances than anomalies.

The model handled this imbalance well, but further validation on diverse datasets is needed to confirm robustness and prevent overfitting.

Feature importance analysis showed that actual flow was the most significant factor, contributing 67.3% to the model’s decisions.

Consumer Water Usage Model Results

The water usage classification model achieved 97.67% accuracy, consistently predicting high or low usage patterns.

A small number of misclassifications occurred, but the model remained robust.

Averaged flow was identified as the most influential feature, contributing 92.3% to predictions.

Future improvements could involve incorporating temporal factors to capture broader seasonal or hourly usage trends.

Limitations

While the models performed well, there are some key limitations:

The models rely heavily on flow data, which may not fully capture external factors like weather conditions, infrastructure changes, or seasonal variations.

The anomaly detection model may be prone to overfitting due to the class imbalance and needs further validation with additional datasets.

The water usage model could be enhanced by considering time-series data and exploring alternative algorithms for improved performance.

Conclusion and Recommendations

Both models provided valuable insights into water anomalies and usage patterns, highlighting potential inefficiencies in the system. Future work should include:

Implementing time-series analysis to capture long-term usage patterns.

Experimenting with alternative machine learning models, such as gradient boosting, to enhance predictive accuracy.

Validating results with external datasets to ensure model generalizability and robustness.