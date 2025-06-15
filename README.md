![actual_vs_predicted_patient_22_week_0](https://github.com/user-attachments/assets/74e9812c-495a-4f20-bfc6-f87445852eb7)
# Personalized Insulin Dosage Prediction Using Hybrid LSTM-GRU Model

## 🧠 Project Overview

This project focuses on predicting personalized regular insulin dosages for diabetic patients using a hybrid deep learning model combining Long Short-Term Memory (LSTM) and Gated Recurrent Unit (GRU) layers. Leveraging the **AIM94 diabetes management dataset**, the model utilizes temporal glucose readings, food intake, and physiological event data to capture individual patterns in insulin requirements. Through comprehensive preprocessing and time-sequence modeling, the system aims to assist in personalized diabetes care by providing accurate insulin dose recommendations.

---

## 🔑 Key Highlights

- **Hybrid LSTM-GRU Architecture**: Integrates both LSTM and GRU layers to effectively capture short- and long-term dependencies in patient glucose-insulin dynamics.
- **Raw Data Preprocessing**: Transforms the raw AIM94 event-based logs into a usable time-series format by pivoting codes, encoding time features cyclically, and generating lagged variables.
- **Time Window Sequence Modeling**: Generates input sequences using a sliding window approach to feed multivariate time-series data into the model.
- **Clinical Impact**: Aims to provide a data-driven support system for insulin dose planning, improving glycemic control and reducing the risk of hypo/hyperglycemia in real-world scenarios.

---

## 🎯 Objectives

- Predict regular insulin dosages using historical glucose readings, food intake, and physiological events with high precision.
- Capture temporal patterns in diabetes management using hybrid recurrent architectures.
- Preprocess raw medical records into meaningful temporal sequences for modeling.
- Contribute toward building personalized decision-support tools in diabetic care.

---

## 🧪 Preprocessing Pipeline

- **Data Cleaning**: Handled missing values, removed irrelevant codes, and standardized timestamp formats.
- **Event Pivoting**: Transformed AIM94 dataset event codes into structured columns for:
  - Glucose
  - Insulin types (Regular, NPH, UltraLente)
  - Food Intake
  - Hypoglycemia
  - Exercise
- **Feature Engineering**:
  - Cyclic encoding for time-of-day (sine/cosine of Hour and Minute)
  - Lag features for past glucose and insulin values
  - Temporal indicators (morning/afternoon/evening)
  - Binary flags for event occurrence (food, exercise, symptoms)
- **Sequence Generation**: Formed multivariate input sequences of fixed window length with corresponding target outputs for next-step insulin dosage prediction.
- **Normalization**: Applied Min-Max scaling to all continuous variables to improve convergence during training.

---

## 🏗️ Model Architecture

Our hybrid model consists of stacked LSTM and GRU layers followed by dense layers to predict insulin dosage:
![image](https://github.com/user-attachments/assets/31c96ea4-9e36-4a85-bb1a-42362e52eddf)

## 🔭 Future Work

- **Multi-output Prediction**: Extend to predict other insulin types (e.g., NPH, UltraLente).
- **Attention Mechanism**: Introduce Transformer or attention layers for better interpretability and performance.
- **Cross-Dataset Testing**: Validate the model on other real-world diabetes datasets.
- **Deployment**: Package the solution into a web app using Flask or Django for clinical testing and real-world usability.

---

## 📌 Final Hybrid Model

The final model integrates both LSTM and GRU units and processes patient sequences to predict personalized insulin dosage.You can check it out here:https://drive.google.com/file/d/10JspsXdBGk9TsfWnc3f7zO8Rk5nA15hW/view?usp=sharing


