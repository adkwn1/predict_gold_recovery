## Predicting Gold Recovery (ML Regression Task)
Author: Andrew Kwon

## Description
This project compares three regression models (Decision Tree Regressor, Random Forest Regressor, Linear Regressor) for predicting a numerical target value. Model performance is evaluated using symmetric Mean Absolute Percentage Error (sMAPE). The main tasks completed in this project are:
- Data inspection and cleaning
- Data analysis and visualization
- Feature analysis
- Training and evaluating regression models using cross-validation and a custom scorer (sMAPE)

Python code, analysis, and solution conducted in Jupyter notebook.

## Introduction
This project was provided by Zyfra, an efficiency solutions developer for heavy industry. In this project, we are to prepare a prototype of a machine learning model that should predict the amount of gold recovered from gold ore. The model will help optimize gold production and eliminate unprofitable parameters. 

The source dataset contains all of the pertinent parameters and outputs related to the technological process for gold ore refinement. The source dataset has already been split into a training and test set. Of note, some of the features are absent in the test set and will be addressed during the project. The project goal is to find the best model according to the sMAPE metric using the predicted rougher and final concentrate recovery values.

## Dataset
We are provided data on gold ore extraction and purification in the following csv files:
- gold_recovery_train.csv
- gold_recovery_test.csv
- gold_recovery_full.csv

The 87 columns in the original dataset mostly describe concentration levels for various substances at different stages of the refining process, but will not be enumerated here. *Due to upload size limitations, each file was compressed into 7zip archives. Users will need to extract the files and place them in the appropriate directory for usage.*

## Pertinent Calucations
The formulas for the calculations are as follows, and additionally detailed in the notebook:

$\text{Recovery} = {{C \times (F-T)} \over {F \times (C-T)}} \times 100$
- C - share of gold in the concentrate right after flotation (rougher concentrate recovery), or after purification (final concentrate recovery)
- F - share of gold in the feed before flotation (rougher concentrate recovery), or after flotation (final concentrate recovery)
- T - share of gold in the rougher tails right after flotation (rougher concentrate recovery), or after purification (final concentrate recovery)

$\text{sMAPE} = {1 \over n} \displaystyle\sum_{i=1}^{n} {{|y_i - \hat{y_i}|} \over {(|y_i| + |\hat{y_i}|)/2}} \times 100$
- $y_i$: target value for observation $i$
- $\hat{y_i}$: predicted target value for observation $i$
- $n$: number of observations in the sample

$\text{Final sMAPE} = 0.25 \times \text{sMAPE(rougher)} + 0.75 \times \text{sMAPE(final)}$

## Requirements
- pandas
- numpy
- plotly.express
- plotly.graph_objects
- sklearn.metrics
- sklearn.tree
- sklearn.ensemble
- sklearn.linear_model
- sklearn.dummy
- sklearn.model_selection

## Screenshots
![feed_size_dist](https://github.com/adkwn1/predict_gold_recovery/assets/119823114/6799b490-f238-4f01-a289-9a747ba5f667)
![total_dist](https://github.com/adkwn1/predict_gold_recovery/assets/119823114/d9ec4553-14f7-475d-b1e5-2051660467bd)
![concentrate_pri](https://github.com/adkwn1/predict_gold_recovery/assets/119823114/6fff90d7-9755-434a-b39a-169f924b6965)
![concentrate_sec](https://github.com/adkwn1/predict_gold_recovery/assets/119823114/058cfc4d-e93b-4225-adfe-66bc12625c7e)



