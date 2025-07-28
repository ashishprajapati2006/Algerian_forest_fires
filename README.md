# 🔥 Forest Fire Weather Index (FWI) Prediction

[![Elastic Beanstalk](https://img.shields.io/badge/Deployed%20on-AWS%20Elastic%20Beanstalk-orange?logo=amazonaws)](http://forestfire-env.eba-34hyti9z.ap-south-1.elasticbeanstalk.com)
[![Made with Python](https://img.shields.io/badge/Made%20with-Python-blue?logo=python)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

A machine learning regression project to predict the **Fire Weather Index (FWI)** using the **Algerian Forest Fires Dataset**. The project includes data preprocessing, EDA, feature engineering, model training, Flask web app creation, and AWS cloud deployment.

🚀 [Live Project Link](http://forestfire-env.eba-34hyti9z.ap-south-1.elasticbeanstalk.com)

---

## 📌 Table of Contents
- [About the Project](#about-the-project)
- [Dataset Information](#dataset-information)
- [EDA & Feature Engineering](#eda--feature-engineering)
- [Modeling](#modeling)
- [Web Application](#web-application)
- [Deployment](#deployment)
- [Installation & Run Locally](#installation--run-locally)
- [Project Structure](#project-structure)
- [Future Improvements](#future-improvements)
- [License](#license)

---

## 🧠 About the Project

This project predicts the **Fire Weather Index (FWI)**, which is a numeric rating of fire potential in forest areas. By using weather and fire behavior indicators, the model provides a continuous FWI value to help assess fire risk.

The model is trained using regression techniques and deployed using Flask on AWS Elastic Beanstalk with a CI/CD pipeline setup via AWS CodePipeline.

---

## 📊 Dataset Information

**Name:** Algerian Forest Fires Dataset  
**Total Instances:** 244 (122 from each region: Bejaia and Sidi Bel-abbes)  
**Timeframe:** June 2012 – September 2012  
**Target:** Fire Weather Index (FWI)  

### Features:
1. Date (DD/MM/YYYY)  
2. Temperature (°C)  
3. Relative Humidity (%)  
4. Wind Speed (km/h)  
5. Rain (mm)  
6. Fine Fuel Moisture Code (FFMC)  
7. Duff Moisture Code (DMC)  
8. Drought Code (DC)  
9. Initial Spread Index (ISI)  
10. Buildup Index (BUI)  
11. Fire Weather Index (FWI) – **Target variable**  
12. Class (Fire / Not Fire) – *Used only for EDA*

---

## 📈 EDA & Feature Engineering

### Exploratory Data Analysis (EDA):
- Correlation heatmaps
- Region-wise fire distribution
- Distribution plots of all variables

### Feature Engineering:
- Dropped non-numeric and irrelevant columns
- Scaled features using `StandardScaler`
- Ensured model-ready clean dataset

---

## 🤖 Modeling

- **Algorithm Used:** Ridge Regression
- **Frameworks:** Scikit-learn, Pandas, Numpy
- **Model Export:** Serialized using `pickle`
- **Evaluation Metrics:**
  - Mean Squared Error (MSE)
  - R² Score

---

## 🌐 Web Application

- **Framework:** Flask
- **Frontend:** HTML/CSS
- Users can input weather parameters and receive the predicted FWI instantly.
- Simple and clean UI.

🖥️ [Click to Open App](http://forestfire-env.eba-34hyti9z.ap-south-1.elasticbeanstalk.com)

---

## ☁️ Deployment

- **Cloud Platform:** AWS Elastic Beanstalk  
- **CI/CD Pipeline:** GitHub → AWS CodePipeline → Elastic Beanstalk  
- **Containerization & Hosting:** Deployed directly from GitHub to EB environment  
- **URL:** `http://forestfire-env.eba-34hyti9z.ap-south-1.elasticbeanstalk.com`

---

## 🛠 Installation & Run Locally

```bash
# Clone the repository
git clone https://github.com/ashishprajapati2006/forestfire.git
cd forestfire

# (Optional) Create a virtual environment
python -m venv venv
venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Run the Flask app
python application.py
