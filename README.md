# 🎓 Student Performance Predictor


> An end-to-end Machine Learning web application that predicts a student's Mathematics score based on demographic and academic factors — built with a modular ML pipeline and deployed on Render.

🔗 **Live Demo:**(https://student-performance-ml-5mpy.onrender.com)

---

## 📌 Table of Contents

- [Overview](#-overview)
- [Demo](#-demo)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [ML Pipeline](#-ml-pipeline)
- [Models Trained](#-models-trained)
- [Installation & Setup](#-installation--setup)
- [Deployment](#-deployment)
- [Results](#-results)

---

## 🧠 Overview

This project predicts a student's **Mathematics score (0–100)** using 7 input features. It demonstrates a production-grade ML pipeline — from raw data ingestion to a live deployed web application — following software engineering best practices like modular code, custom logging, and exception handling.

---

## 🎥 Demo

| Input Form | Prediction Result |
|---|---|
| Fill in 7 student attributes | Get predicted Maths score instantly |

🔗 Try it live: [student-performance-ml-5mpy.onrender.com](https://student-performance-ml-5mpy.onrender.com)

---

## ✨ Features

- 🔄 **End-to-end ML Pipeline** — Data ingestion → transformation → training → prediction
- 🧪 **7 Models Trained & Compared** with GridSearchCV hyperparameter tuning
- 📦 **Modular Codebase** — Each component is independently structured
- 📋 **Custom Logging** — Timestamped logs for every pipeline step
- ⚠️ **Custom Exception Handling** — File name and line number in every error
- 🌐 **Flask Web App** — Clean UI for real-time predictions
- 🚀 **Deployed on Render** — Auto-redeploys on every GitHub push via CI/CD

---

## 🛠 Tech Stack

| Category | Tools |
|---|---|
| **Language** | Python 3.8+ |
| **ML Libraries** | Scikit-Learn, XGBoost, CatBoost |
| **Data Processing** | Pandas, NumPy |
| **Web Framework** | Flask |
| **Serialization** | Dill |
| **CI/CD** | GitHub Actions |
| **Deployment** | Render Cloud |
| **Containerization** | Docker |

---

## 📁 Project Structure

```
├── .github/
│   └── workflows/
│       └── main_studentperformancecheck.yml   # CI/CD pipeline
├── artifacts/                                  # Generated files (pkl, csv)
│   ├── model.pkl
│   ├── preprocessor.pkl
│   ├── train.csv
│   └── test.csv
├── notebook/
│   ├── data/
│   │   └── stud.csv                           # Raw dataset
│   ├── 1. EDA STUDENT PERFORMANCE.ipynb       # Exploratory Data Analysis
│   └── 2. MODEL TRAINING.ipynb                # Model experiments
├── src/
│   ├── components/
│   │   ├── data_ingestion.py                  # Data loading & splitting
│   │   ├── data_transformation.py             # Feature engineering
│   │   └── model_trainer.py                   # Model training & selection
│   ├── pipeline/
│   │   └── predict_pipeline.py                # Prediction pipeline
│   ├── exception.py                           # Custom exception handler
│   ├── logger.py                              # Custom logger
│   └── utils.py                              # Helper functions
├── templates/                                 # HTML templates
├── app.py                                     # Flask application
├── Dockerfile                                 # Docker configuration
├── requirements.txt                           # Python dependencies
└── setup.py                                   # Package setup
```

---

## ⚙️ ML Pipeline

```
Raw Dataset (1000 records)
        ↓
  Data Ingestion
  (80/20 Train-Test Split)
        ↓
  Data Transformation
  ┌─────────────────────────────┐
  │ Numerical Pipeline          │
  │  SimpleImputer (median)     │
  │  → StandardScaler           │
  ├─────────────────────────────┤
  │ Categorical Pipeline        │
  │  SimpleImputer (mode)       │
  │  → OneHotEncoder            │
  │  → StandardScaler           │
  └─────────────────────────────┘
        ↓
  Model Training
  (7 Models + GridSearchCV)
        ↓
  Best Model → model.pkl
  Preprocessor → preprocessor.pkl
        ↓
  Flask Web App → Prediction
```

---

## 🤖 Models Trained

| Model | Type |
|---|---|
| Linear Regression | Baseline |
| Decision Tree Regressor | Tree-based |
| Random Forest Regressor | Ensemble Bagging |
| Gradient Boosting Regressor | Ensemble Boosting |
| XGBoost Regressor | Advanced Boosting |
| CatBoost Regressor | Gradient Boosting |
| AdaBoost Regressor | Adaptive Boosting |

Best model selected based on **R² score**.

---

## 📥 Input Features

| Feature | Type | Values |
|---|---|---|
| Gender | Categorical | Male, Female |
| Race/Ethnicity | Categorical | Group A, B, C, D, E |
| Parental Education | Categorical | High school, Bachelor's, Master's, etc. |
| Lunch | Categorical | Standard, Free/Reduced |
| Test Preparation | Categorical | Completed, None |
| Reading Score | Numerical | 0–100 |
| Writing Score | Numerical | 0–100 |

**Output:** Predicted Mathematics Score (0–100)

---

## 🚀 Installation & Setup

### Prerequisites
- Python 3.8+
- Anaconda or pip

### Steps

```bash
# 1. Clone the repository
git clone https://github.com/your-username/student-performance-predictor.git
cd student-performance-predictor

# 2. Install dependencies
pip install -r requirements.txt

# 3. Install as package
pip install -e .

# 4. Run training pipeline
python src/components/data_ingestion.py

# 5. Start Flask app
python app.py
```

Open your browser at `http://localhost:5000/predictdata`

---

## ☁️ Deployment

This project is deployed on **[Render](https://render.com)** with automatic CI/CD via GitHub Actions.

| Setting | Value |
|---|---|
| Platform | Render Cloud |
| Build Command | `pip install -r requirements.txt` |
| Start Command | `python app.py` |
| Auto Deploy | On every push to `main` branch |

🔗 **Live URL:** [https://student-performance-ml-5mpy.onrender.com](https://student-performance-ml-5mpy.onrender.com)

> ⚠️ Note: The app may take 30–60 seconds to load on first visit due to Render's free tier spin-up time.

---

## 📊 Results

| Metric | Value |
|---|---|
| Best Model | CatBoost / Gradient Boosting Regressor |
| R² Score | ~0.88 |
| Interpretation | Model explains 88% of variance in Maths scores |

---

## 🙋‍♀️ Author

**Manya**

---



⭐ If you found this project helpful, please give it a star!
