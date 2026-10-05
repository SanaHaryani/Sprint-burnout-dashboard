# AI-Based Sprint Planning and Burnout Prediction System

An AI-based decision-support system designed to help Agile teams estimate sprint capacity and identify potential burnout risk using machine learning.

## 📌 Project Overview

This project presents a concept for an **AI-Based Sprint Planning and Burnout Prediction System for Agile Project Management**.

The system uses Agile workload and team-related variables to:

* Predict **sprint capacity** using regression
* Predict **burnout risk** using classification
* Provide predictions through an interactive **Streamlit dashboard**
* Support sprint planning and workload-related decision-making

The project combines **machine learning, Agile project management and data-driven decision support**.

## 🤖 Machine Learning Models

Five machine learning algorithms were evaluated for each prediction task:

* Linear Regression
* Decision Tree
* Random Forest
* Gradient Boosting
* XGBoost

The best-performing models were selected for the final system.

| Task            | Model               | Test Performance | Cross-Validation |
| --------------- | ------------------- | ---------------: | ---------------: |
| Sprint Capacity | Linear Regression   |       R² = 0.905 |       R² = 0.916 |
| Burnout Risk    | Logistic Regression | Accuracy = 0.855 | Accuracy = 0.845 |

The trained models and preprocessing objects are stored as `.pkl` files and are required to run the dashboard.

## 📊 Dataset

The system was trained on a **synthetic dataset containing 1,000 Agile sprint observations**.

The data was generated programmatically using a causal-chain approach:

**Team Characteristics → Velocity → Workload → Deadlines → Sprint Capacity / Burnout Risk**

A fixed random seed (**42**) was used to ensure reproducibility.

No real organisational or personal data was used.

## 🖥️ Interactive Dashboard

The trained models are integrated into a **Streamlit dashboard** that allows users to enter Agile sprint variables and receive model predictions.

### Dashboard capabilities

* Sprint capacity prediction
* Burnout risk prediction
* Interactive input parameters
* Model-based decision support
* Prediction visualisation

## 📁 Repository Contents

```text
├── app.py
├── sprint_capacity_model.pkl
├── burnout_classifier_model.pkl
├── scaler.pkl
├── feature_columns.pkl
├── requirements.txt
├── thesis_training.ipynb
└── README.md
```

| File                           | Description                               |
| ------------------------------ | ----------------------------------------- |
| `app.py`                       | Streamlit dashboard application           |
| `sprint_capacity_model.pkl`    | Trained Linear Regression model           |
| `burnout_classifier_model.pkl` | Trained Logistic Regression model         |
| `scaler.pkl`                   | Fitted StandardScaler                     |
| `feature_columns.pkl`          | Feature order used during training        |
| `requirements.txt`             | Python dependencies                       |
| `thesis_training.ipynb`        | Complete training and evaluation pipeline |

## 🛠️ Technologies

* **Python**
* **Scikit-learn**
* **XGBoost**
* **SHAP**
* **Pandas**
* **NumPy**
* **Matplotlib / Seaborn**
* **Streamlit**
* **Jupyter Notebook**
* **Joblib**

## 🚀 Running the Dashboard

### Requirements

Python 3.11+

### Install dependencies

```bash
pip install -r requirements.txt
```

### Run the application

```bash
streamlit run app.py
```

The dashboard will be available locally at:

`http://localhost:8501`

## 🌐 Live Demo

**Streamlit Community Cloud:**
https://sprint-burnout-dashboard-r6gfcm44bwuxze4vg8c7br.streamlit.app/

## 🔬 Reproducibility

The complete model training and evaluation pipeline is documented in the accompanying Jupyter notebook.

Using the same dataset generation process and random seed (**42**) allows the reported experiments and results to be reproduced.

