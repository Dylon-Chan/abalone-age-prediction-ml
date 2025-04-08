# Abalone Age Prediction - Machine Learning Exercise

This is an exercise on the **Abalone Age Prediction**! This repository contains a Jupyter notebook-based machine learning exercise focused on predicting the age of abalone (a type of marine mollusk) based on physical measurements. The primary objective is to apply and explore various regression techniques to estimate the number of rings in an abalone shell, which correlates with its age.

## Problem Statement

The age of an abalone is traditionally determined by cutting the shell through the cone, staining it, and counting the number of rings under a microscope — a time-consuming process. This project attempts to **predict the number of rings (i.e., the age)** using machine learning techniques based on easily measurable physical attributes.

## Technique Used:
- Brief Data Exploration (EDA)
- Data Preprocessing and Cleaning
- Models used:
    - KNN Regressor
    - Linear Regression
- Model Evaluation:
    - MSE
    - RMSE
    - R-squared score

## Dataset

The dataset used is the classic [Abalone dataset](https://archive.ics.uci.edu/ml/datasets/abalone) from the UCI Machine Learning Repository. It include the following features:
- **Sex** (categorical: M, F, I)
- **Length**
- **Diameter**
- **Height**
- **Whole weight**
- **Shucked weight**
- **Viscera weight**
- **Shell weight**
- **Rings** (target variable)

The age of the abalone is approximately calculated as:
```
Age = Rings + 1.5
```


## Reference:
- [UCI Abalone Dataset](https://archive.ics.uci.edu/ml/datasets/abalone)
- [Scikit-learn documentation](https://scikit-learn.org/stable/user_guide.html)
