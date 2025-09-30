# Credit Risk Modelling

This project implements a **Credit Risk Modelling** pipeline with a Streamlit UI for interactive predictions. The workflow includes data collection, exploratory data analysis (EDA), feature engineering, model training, and evaluation.

## Project Structure

```
Main.ipynb            # Main notebook for EDA, feature engineering, and model training
main.py               # Streamlit UI for predictions
prediction_helper.py  # Helper functions for prediction and scoring
artifacts/
    model_data.joblib     # Trained model and preprocessing objects
Data/
    bureau_data.csv
    customers.csv
    loans.csv
```

## Features

- **EDA**: Visualizes distributions, outliers, and relationships in customer, loan, and bureau data.
- **Feature Engineering**: Creates new features (e.g., loan-to-income ratio, delinquency ratios) and encodes categorical variables.
- **Model Training**: Trains and tunes models (Logistic Regression, XGBoost) with class imbalance handling (undersampling, oversampling).
- **Model Evaluation**: Includes ROC-AUC, Gini coefficient, KS statistic, and feature importance analysis.
- **Streamlit UI**: Interactive web interface for credit risk prediction using the trained model.

## How to Run

1. **Install dependencies**:
    ```sh
    pip install -r requirements.txt
    ```

2. **Train the model**:
    - Run all cells in [`Main.ipynb`](Main.ipynb) to perform EDA, feature engineering, and save the trained model to [`artifacts/model_data.joblib`](artifacts/model_data.joblib).

3. **Start the Streamlit UI**:
    ```sh
    streamlit run app/main.py
    ```

## Data Sources

- [`Data/customers.csv`](Data/customers.csv): Customer demographic data
- [`Data/loans.csv`](Data/loans.csv): Loan application and status data
- [`Data/bureau_data.csv`](Data/bureau_data.csv): Bureau records

## Model Details

- **Preprocessing**: MinMax scaling for numeric features, one-hot encoding for categorical features.
- **Algorithms**: Logistic Regression (with hyperparameter tuning), XGBoost (with RandomizedSearchCV and Optuna).
- **Metrics**: Classification report, ROC-AUC, Gini coefficient, KS statistic.

## Prediction Pipeline

The Streamlit UI uses [`app/prediction_helper.py`](app/prediction_helper.py) to:
- Prepare input features
- Scale and encode data
- Predict default probability and credit score
- Display risk rating

## Demo

Try the deployed app here: [https://app-credit-risk-modelling.streamlit.app/](https://app-credit-risk-modelling.streamlit.app/)

## References

- scikit-learn
- XGBoost
- Optuna
- imbalanced-learn
- Streamlit

---