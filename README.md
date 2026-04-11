# Student Exam Performance Predictor

An end-to-end Machine Learning web application that predicts 
student maths scores based on various factors.

## About
This project predicts a student's maths score based on:
- Gender
- Race/Ethnicity
- Parental Level of Education
- Lunch Type
- Test Preparation Course
- Reading Score
- Writing Score

## Tech Stack
- Python
- Flask
- Scikit-learn
- XGBoost
- CatBoost
- Docker
- GitHub Actions

## How to Run
1. Clone the repository
2. Install dependencies:
   pip install -r requirements.txt
3. Run the app:
   python app.py
4. Open browser: http://localhost:80/predictdata

## Project Structure
- src/components/ - Data ingestion, transformation, model training
- artifacts/ - Trained model and preprocessor
- templates/ - HTML pages
- app.py - Flask application