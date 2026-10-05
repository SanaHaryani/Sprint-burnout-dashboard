# AI-Based Sprint Planning and Burnout Prediction System

Master's Thesis — IU University of Applied Sciences
Programme: MSc. Computer Science

Overview

This repository contains the full implementation for the thesis "Concept for an AI-Based Sprint Planning and Burnout Prediction System for Agile Project Management." The system uses machine learning to predict sprint capacity (regression) and burnout risk (classification) from Agile workload variables, and exposes predictions through an interactive Streamlit dashboard.

Repository Contents
├── app.py                          # Streamlit dashboard application
├── sprint_capacity_model.pkl       # Trained Linear Regression model
├── burnout_classifier_model.pkl    # Trained Logistic Regression model
├── scaler.pkl                      # Fitted StandardScaler (must match models)
├── feature_columns.pkl             # Feature column order used during training
├── requirements.txt                # Python dependencies
└── README.md                       # This file

Models
Task	Model	Test Performance	CV Mean
Sprint Capacity (Regression)	Linear Regression	R² = 0.905	R² = 0.916
Burnout Risk (Classification)	Logistic Regression	Accuracy = 0.855	Accuracy = 0.845

Both models were selected through a systematic comparison of five candidate algorithms per task (Linear Regression, Decision Tree, Random Forest, Gradient Boosting, XGBoost). All four .pkl files must be present in the same directory as app.py for the dashboard to run correctly.

Running the Dashboard

Requirements: Python 3.11+

Install dependencies:

bash
pip install -r requirements.txt

Run the app:

bash
streamlit run app.py

The dashboard will open automatically in your browser at http://localhost:8501.

Live Demo

Deployed on Streamlit Community Cloud

Dataset

The system was trained on a synthetic dataset of 1,000 Agile sprint observations generated using a causal-chain process (team characteristics → velocity → workload → deadlines → sprint capacity / burnout risk). All data was generated programmatically with a fixed random seed (42) for full reproducibility. No real organisational or personal data was used.

Reproducibility

The full training pipeline is documented in the accompanying Jupyter notebook. Running all cells top to bottom with the same random seed (42) will reproduce all results reported in Chapter 4 of the thesis exactly.

Dependencies
Library	Purpose
streamlit	Dashboard interface
scikit-learn	Model training, preprocessing, evaluation
xgboost	Additional ensemble benchmark
shap	Explainability (SHAP values)
numpy	Numerical computation
pandas	Data manipulation
matplotlib / seaborn	Visualisation
joblib	Model serialisation
Citation

License

This project was developed for academic research purposes only. The models and dashboard are proof-of-concept implementations and are not intended for production deployment without further validation on real organisational data.
