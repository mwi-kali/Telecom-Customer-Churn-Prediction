# Telecom Customer Churn Prediction

An analysis for predicting customer churn in a telecommunications dataset.  This repository covers data ingestion, exploratory data analysis (EDA), feature engineering, hyperparameter tuning, model training, and final evaluation of several machine-learning algorithms, culminating in a serialized XGBoost model ready for deployment.

---

##  Project Structure

```
Telecom-Customer-Churn-Prediction/
│
├── models/
│   └── xgboost_churn.pkl                            # Saved XGBoost model
│
├── notebooks/
│   ├── catboost_info/                               # Supporting CatBoost analysis files
│   ├── Telecom_Customer_Churn_Prediction_Exploratory_Data_Analysis.ipynb
│   ├── Telecom_Customer_Churn_Prediction_Feature_Engineering.ipynb
│   └── Telecom_Customer_Churn_Prediction_Model_Training.ipynb
│
├── .gitignore                                       # Ignored files and folders
├── requirements.txt                                 # Python dependencies
└── README.md                                        # This file
```

---

##  Installation

1. **Clone the repository**  
   ```bash
   git clone https://github.com/your-username/Telecom-Customer-Churn-Prediction.git
   cd Telecom-Customer-Churn-Prediction
   ```

2. **Create & activate a virtual environment**  
   ```bash
   python3 -m venv venv
   source venv/bin/activate
   ```

3. **Install Python dependencies**  
   ```bash
   pip install -r requirements.txt
   ```

4. **(Optional) Configure Kagglehub**  
   The EDA notebook can download the raw CSV via Kagglehub.  If you’d like to enable that, set your Kaggle API credentials:  
   ```bash
   export KAGGLE_USERNAME=your_kaggle_username
   export KAGGLE_KEY=your_kaggle_key
   ```

---

##  Usage

All of the heavy lifting is performed in the three Jupyter notebooks under `notebooks/`.  Execute them in sequence:

1. **Exploratory Data Analysis**  
   ```bash
   jupyter lab notebooks/Telecom_Customer_Churn_Prediction_Exploratory_Data_Analysis.ipynb
   ```
   - Ingests raw data, audits quality, and produces univariate/multivariate visualizations.

2. **Feature Engineering**  
   ```bash
   jupyter lab notebooks/Telecom_Customer_Churn_Prediction_Feature_Engineering.ipynb
   ```
   - Cleans missing values, encodes categoricals, creates tenure buckets, service-count, revenue-per-service, and a rich set of interaction terms.

3. **Model Training & Evaluation**  
   ```bash
   jupyter lab notebooks/Telecom_Customer_Churn_Prediction_Model_Training.ipynb
   ```
   - Applies SMOTE, tunes six models (LightGBM, XGBoost, CatBoost, RandomForest, ExtraTrees, LogisticRegression) with Optuna, compares validation/test performance, and saves the best XGBoost model to `models/xgboost_churn.pkl`.

---
