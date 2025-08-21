# Australian Weather Rain Prediction

## Overview
This project implements machine learning models to predict rainfall in Australia using historical weather data. The goal is to accurately forecast whether it will rain tomorrow based on various meteorological features.

## Dataset
- **Source**: Australian Weather Dataset (`weatherAUS.csv`)
- **Size**: 145,460 records with 23 features
- **Target Variable**: RainTomorrow (Binary: Yes/No)
- **Features**: Temperature, Humidity, Pressure, Wind Direction, Rainfall, etc.

## Features
- **MinTemp/MaxTemp**: Daily temperature range
- **Rainfall**: Amount of rainfall
- **Humidity**: Morning and afternoon humidity levels
- **WindGustDir/WindGustSpeed**: Wind gust direction and speed
- **WindDir9am/WindDir3pm**: Wind direction at 9 AM and 3 PM
- **WindSpeed9am/WindSpeed3pm**: Wind speed at 9 AM and 3 PM
- **Cloud9am/Cloud3pm**: Cloud coverage at 9 AM and 3 PM
- **Location**: Australian city/location
- **RainToday**: Whether it rained today

## Data Preprocessing
1. **Missing Value Treatment**: 
   - Numerical features: Filled with mean values
   - Categorical features: Filled with mode values
2. **Feature Engineering**:
   - Label encoding for categorical variables
   - Removed redundant features (Date, duplicate temperature/humidity readings)
3. **Outlier Detection**: Z-score method to remove statistical outliers
4. **Duplicate Removal**: Eliminated 410 duplicate records

## Models Implemented

### 1. Decision Tree (sklearn)
- **Accuracy**: 77.39%
- **F1-Score**: 47.80%
- **Precision**: 46.24%
- **Recall**: 49.47%

### 2. Random Forest (sklearn)
- **Accuracy**: 84.99%
- **F1-Score**: 55.26%
- **Precision**: 73.45%
- **Recall**: 44.29%

### 3. XGBoost Random Forest
- **Accuracy**: 85.55%
- **F1-Score**: 59.24%
- **Precision**: 72.31%
- **Recall**: 50.18%

### 4. XGBoost Decision Tree
- **Accuracy**: 85.42%
- **F1-Score**: 58.28%
- **Precision**: 72.69%
- **Recall**: 48.63%

## Key Findings
- **Best Performing Model**: XGBoost Random Forest (85.55% accuracy)
- **Class Imbalance**: Dataset has more "No Rain" predictions than "Rain" predictions
- **Feature Importance**: Temperature and humidity are key predictors
- **Model Comparison**: XGBoost implementations consistently outperformed sklearn models

## Technologies Used
- **Python**: Primary programming language
- **Pandas**: Data manipulation and analysis
- **NumPy**: Numerical computations
- **Scikit-learn**: Machine learning algorithms
- **XGBoost**: Gradient boosting framework
- **Matplotlib/Seaborn**: Data visualization
- **Missingno**: Missing data visualization

## Project Structure
```
├── Rain Pred (RF,DT).ipynb    # Main Jupyter notebook
├── weatherAUS.csv             # Dataset
├── README.md                  # Project documentation
└── linkedin_description.txt   # LinkedIn project description
```

## Usage
1. Clone the repository
2. Install required dependencies:
   ```bash
   pip install pandas numpy scikit-learn xgboost matplotlib seaborn missingno
   ```
3. Open `Rain Pred (RF,DT).ipynb` in Jupyter Notebook
4. Run all cells to reproduce the analysis

## Author
**Ayush Kumar**


## Future Improvements
- Implement deep learning models (Neural Networks)
- Add feature selection techniques
- Try ensemble methods combining multiple models
- Implement cross-validation for better model evaluation
- Add real-time prediction capabilities

