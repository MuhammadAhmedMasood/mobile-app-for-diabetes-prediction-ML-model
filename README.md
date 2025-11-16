# mobile-app-for-diabetes-prediction-ML-model
End-to-end Diabetes Prediction system with a trained ML model, Python API, and an Android app built using MIT App Inventor. Includes model file, backend API, and APK for real-time predictions.

---

# Diabetes Prediction App (Android + Machine Learning API)

This project is an end-to-end **Diabetes Prediction System** that combines a machine learning model, a Python API, and an Android app built using MIT App Inventor. The app allows users to input medical details and receive a real-time diabetes prediction through a backend ML model.

---

## 📌 Project Overview

This system consists of **three main components**:

### **1. Machine Learning Model**

* Developed in Python 
* Trained on a diabetes dataset and saved as
  **`diabetes_trained_model.sav`**.
* This file contains the serialized model used for inference.

### **2. Python API for Android App**

* File: **`api_for_android.py`**
* Written in Google Colab and exposed over the internet using **ngrok**.
* Provides a `/predict` endpoint that:

  * Loads `diabetes_trained_model.sav`
  * Accepts input features from the Android app
  * Returns the prediction result (0 or 1)

### **3. Android App (MIT App Inventor)**

* Built entirely using the MIT App Inventor platform.
* File: **`diabetes_prediction_app.apk`**
* The app UI collects user medical parameters.
* App sends the inputs to the Python API using the ngrok URL.
* Displays the prediction returned by the model.

---

## 📂 Repository Structure

```
.
├── diabetes_trained_model.sav         # Serialized ML model
├── api_for_android.py                 # Flask/FastAPI backend for predictions
├── diabetes_prediction_app.apk        # Android app built using MIT App Inventor
└── README.md
```

---

## 🚀 How the System Works (Flow)

1. User enters medical values into the Android app.
2. The app sends the data to the backend API using the ngrok URL.
3. The Python API loads the `.sav` model and performs prediction.
4. The API sends the result back to the Android app.
5. The app displays whether the model predicts diabetes or not.

---

## 🔧 How to Run the Backend API

1. Upload `api_for_android.py` and `diabetes_trained_model.sav` to your environment.
2. Install required packages:

   ```bash
   pip install flask numpy pandas pickle flask-cors
   ```
3. Run the API:

   ```bash
   python api_for_android.py
   ```
4. Start ngrok:

   ```bash
   ngrok http 5000
   ```
5. Copy the generated **public URL** and update it inside MIT App Inventor blocks.

---

## 📱 How to Use the Android App

1. Download **`diabetes_prediction_app.apk`** from this repository.
2. Install it on your Android device.
3. Enter the required input fields (e.g., glucose level, BMI, etc.).
4. Tap **Predict**.
5. The app sends the data to your API and shows the result.

---

## 🎯 Purpose of This Project

* Shows how to integrate a **machine learning model with a mobile app**.
* Useful for beginners learning API creation, model deployment, and app-backend communication.

