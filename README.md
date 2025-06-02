# Abalone Age Prediction - Machine Learning Exercise

This is a comprehensive machine learning exercise focused on **predicting the age of abalone** (a type of marine mollusk) based on physical measurements. The primary objective is to apply and explore various regression techniques to estimate the number of rings in an abalone shell, which correlates with its age, thereby eliminating the need for the time-consuming manual counting process.

##  Problem Statement

The age of an abalone is traditionally determined by cutting the shell through the cone, staining it, and counting the number of rings under a microscope — a time-consuming and destructive process. This project attempts to **predict the number of rings (i.e., the age)** using machine learning techniques based on easily measurable physical attributes.

##  Key Results

| Model | MSE | RMSE | R-squared |
|-------|-----|------|-----------|
| **KNN (k=6)** | **4.737** | **2.176** | **0.534** |
| Linear Regression | 4.786 | 2.188 | 0.529 |
| Linear Regression + Volume Feature | 4.773 | 2.185 | 0.530 |
| Baseline (Mean Predictor) | 10.183 | 3.191 | -0.003 |

**Best Model:** K-Nearest Neighbors (k=6) achieved the highest R² score of 0.534, meaning it explains approximately 53.4% of the variance in abalone age prediction.

##  Installation & Setup

### Prerequisites
- Python 3.7+
- Jupyter Notebook or JupyterLab

### Required Dependencies

Refer to the [requirements.txt](./requirements.txt) file for the dependencies.

##  Project Structure
```
abalone-age-prediction-ml/
├── notebook.ipynb          # Main analysis notebook
├── README.md               # Project documentation
└── environment.yml         # Environment file
```

##  How to Run

1. **Clone the repository:**
   ```bash
   git clone <repository-url>
   cd abalone-age-prediction-ml
   ```

2. **Install dependencies:**
   ```bash
   conda env update -f environment.yml
   conda activate ml
   ```

3. **Launch Jupyter Notebook:**
   ```bash
   jupyter notebook notebook.ipynb
   ```

4. **Run all cells** to reproduce the analysis and results.

##  Methodology

### 1. Data Exploration (EDA)
- Dataset overview and statistical summaries
- Feature distribution analysis
- Missing value assessment
- Multicollinearity investigation using VIF analysis

### 2. Data Preprocessing
- One-hot encoding for categorical variables (Sex)
- Feature scaling using StandardScaler
- Train-test split (70-30 ratio)
- Feature engineering (Volume calculation)

### 3. Models Implemented
- **K-Nearest Neighbors (KNN):** k=5, k=6
- **Linear Regression:** Standard and with feature scaling
- **Feature Engineering:** Added volume feature (Length × Diameter × Height)
- **Baseline Model:** Mean predictor for comparison

### 4. Model Evaluation
- **Metrics Used:**
  - Mean Squared Error (MSE)
  - Root Mean Squared Error (RMSE)
  - R-squared score
- **Comparison:** All models compared against baseline

##  Dataset Information

The dataset used is the classic [Abalone dataset](https://archive.ics.uci.edu/ml/datasets/abalone) from the UCI Machine Learning Repository.

### Features (8 predictors):
- **Sex** (categorical): M (Male), F (Female), I (Infant)
- **Length** (continuous): Longest shell measurement (mm)
- **Diameter** (continuous): Perpendicular to length (mm)
- **Height** (continuous): With meat in shell (mm)
- **Whole weight** (continuous): Whole abalone weight (grams)
- **Shucked weight** (continuous): Weight of meat (grams)
- **Viscera weight** (continuous): Gut weight after bleeding (grams)
- **Shell weight** (continuous): After being dried (grams)

### Target Variable:
- **Rings** (integer): Number of rings (age ≈ rings + 1.5 years)

### Dataset Statistics:
- **Total samples:** 4,177
- **No missing values**
- **Target range:** 1-29 rings (mean: 9.93)

##  Key Findings

1. **Model Performance:** KNN (k=6) slightly outperformed Linear Regression with an R² of 0.534
2. **Feature Scaling:** Minimal impact
3. **Feature Engineering:** Adding volume feature provided marginal improvement
4. **Multicollinearity:** High correlation detected between physical measurements (expected)
5. **Prediction Accuracy:** RMSE ≈ 2.18 rings suggests predictions within ±2 rings on average


##  Limitations & Future Work

### Current Limitations:
- R² of 0.534 indicates 46.6% of variance remains unexplained
- High multicollinearity between physical measurements
- Limited hyperparameter tuning performed

### Suggested Improvements:
- **Advanced Models:** Random Forest, XGBoost, or Neural Networks
- **Regularization:** Ridge/Lasso regression to handle multicollinearity
- **Cross-Validation:** More robust model evaluation
- **Feature Selection:** Systematic approach to reduce multicollinearity
- **Hyperparameter Tuning:** Bayesian optimization

##  References
- [UCI Abalone Dataset](https://archive.ics.uci.edu/ml/datasets/abalone)
- [Scikit-learn Documentation](https://scikit-learn.org/stable/user_guide.html)