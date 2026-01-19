# heart-disease-prediction
# Heart Disease Prediction System

## 🔍 1. Problem Statement

Heart disease is a
significant public health issue globally. Early detection is crucial to prevent severe health outcomes. The goal of this project is to develop a **machine learning model** that predicts whether a patient has heart disease based on clinical features such as age, blood pressure, cholesterol, and exercise-induced changes. The system is trained and evaluated on the UCI Heart Disease dataset and deployed as an interactive web application for easy use.

---

## 📁 2. Project Overview

This project implements an end-to-end machine learning pipeline with the following stages:

1. **Data Understanding** – Exploratory data analysis and visualization.
2. **Data Preparation** – Handling missing values, feature scaling, and class imbalance via SMOTE.
3. **Modeling** – Training classical ML algorithms (Logistic Regression, Decision Tree, Random Forest, SVM).
4. **Evaluation** – Comparing models using Accuracy, F1, and ROC-AUC; visualizing performance.
5. **Deployment** – Creating a Gradio web UI to interact with the trained model.
6. **Docker Support** – Enables containerized deployment for reproducibility.

---

## 📊 3. Dataset

- **Dataset Source**: UCI Heart Disease dataset (Kaggle)
- **File Used**: `heart_prediction.csv`
- **Target Variable**: `num` (converted to binary: 0 = no heart disease, 1 = disease present)
- **Features Included**:
  - age, trestbps, chol, thalch, oldpeak, ca

---

## 🧠 4. Key Features

| Feature       | Description                                        |
|---------------|----------------------------------------------------|
| age           | Age of patient                                     |
| trestbps      | Resting blood pressure (mm Hg)                     |
| chol          | Serum cholesterol (mg/dl)                          |
| thalch        | Maximum heart rate achieved                        |
| oldpeak       | ST depression induced by exercise                  |
| ca            | Number of major vessels detected by fluoroscopy    |

The model predicts heart disease risk based on these clinical indicators.

---

## 🔧 5. How to Run (Google Colab)

1. Open each notebook in the `notebooks/` directory in order:
   - `01_data_understanding.ipynb`
   - `02_data_preparation.ipynb`
   - `03_modeling.ipynb`
   - `04_evaluation.ipynb`
   - `05_deployment.ipynb`
2. Run all cells sequentially.
3. In the deployment notebook, launch the Gradio interface to test predictions.

---

## 🚀 6. Live Demo (Gradio)

You can try the deployed model with a simple web form here:

👉 https://4864cc2f5ece1b18bd.gradio.live

Enter values for the clinical features and receive a heart disease prediction.

---

## 🧾 7. Results & Evaluation

The Random Forest model performed best among the classical models based on:

- **Accuracy**: Balanced overall correctness
- **F1 Score**: Balances precision and recall
- **ROC-AUC**: Measures separability between classes

Confusion matrices and ROC curves are available in the Evaluation notebook and reports.

---

## 🐙 8. Docker Deployment (Optional)

A `Dockerfile` is included for containerized deployment:

```dockerfile
FROM python:3.10

WORKDIR /app

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

CMD ["python", "app.py"]
Build the Docker image:
docker build -t heart-disease-app .

Run the Docker container:
docker run -p 7860:7860 heart-disease-app
heart_disease_project/
├── data/
│   └── raw/heart_prediction.csv
├── data/processed/
├── models/
│   ├── best_model.pkl
│   └── scaler.pkl
├── notebooks/
├── reports/
│   └── plots/
├── app.py
├── requirements.txt
├── Dockerfile
└── README.md
> Live Demo: https://4864cc2f5ece1b18bd.gradio.live  
> Built with 🔥 classical ML models
