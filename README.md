# Personalized Insulin Dosage Prediction Using Hybrid LSTM-GRU Model

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.8%2B-blue"/>
  <img src="https://img.shields.io/badge/TensorFlow-2.x-orange"/>
  <img src="https://img.shields.io/badge/Keras-Deep%20Learning-red"/>
  <img src="https://img.shields.io/badge/Architecture-Hybrid%20LSTM--GRU-yellow"/>
  <img src="https://img.shields.io/badge/Technique-Residual%20Connections-blueviolet"/>
  <img src="https://img.shields.io/badge/Dataset-AIM94%20(UCI)-lightgrey"/>
  <img src="https://img.shields.io/badge/R²%20Score-0.805-brightgreen"/>
</p>
<img width="1200" height="600" alt="image" src="https://github.com/user-attachments/assets/4a4cffa1-3bbd-4bbc-b6ce-ddfb62634ce2" />


## 🧠 Project Overview

This project presents a Residual Hybrid Deep Learning Model for predicting personalized regular insulin dosages in diabetic patients. The architecture integrates LSTM and GRU layers with residual connections, enabling the model to capture both short-term fluctuations and long-term glucose–insulin dependencies. Using the AIM94 dataset, advanced preprocessing and temporal feature engineering were applied to transform event-based logs into model-ready time-series data.

---

## 🔑 Key Highlights

- **Residual Hybrid Architecture**: Combines LSTM and GRU blocks with skip/residual connections to improve gradient flow and learning stability.
- **Raw Data Preprocessing**: Transforms the raw AIM94 event-based logs into a usable time-series format by pivoting codes, encoding time features cyclically, and generating lagged variables.
- **Time Window Sequence Modeling**: Generates input sequences using a sliding window approach to feed multivariate time-series data into the model.
- **Performance Improvement**: Achieved R² = 0.805, MAE = 1.29, MSE = 3.27, representing a ~30% improvement in R² and >60% reduction in MSE compared to baseline models.

---

## 🎯 Objectives

- Predict regular insulin dosages using historical glucose readings, food intake, and physiological events with high precision.
- Capture temporal patterns in diabetes management using hybrid recurrent architectures.
- Preprocess raw medical records into meaningful temporal sequences for modeling.
- Contribute toward building personalized decision-support tools in diabetic care.

---
## 🧪 Preprocessing Pipeline

To convert the raw AIM94 event-based logs into a model-ready time-series dataset, we performed the following steps:

- **Data Cleaning**: Removed irrelevant codes, handled missing values, and standardized date-time formats.
- **Event Pivoting**: Transformed event codes into structured columns like:
  - Glucose
  - Insulin types (Regular, NPH, UltraLente)
  - Food Intake
  - Hypoglycemia
  - Exercise
- **Feature Engineering**:
  - Cyclic encoding for time-of-day (sine/cosine of Hour and Minute)
  - Lag features for past glucose and insulin values
  - Temporal indicators (e.g., morning/afternoon/evening)
  - Binary event flags for food, exercise, symptoms
- **Sequence Generation**: Created multivariate input sequences using a sliding window to forecast the next insulin dose.
- **Normalization**: Applied Min-Max scaling to continuous features for better model convergence.

### 🔁 Raw to Processed Data Example
AIM94 RAM Dataset Available at : https://archive.ics.uci.edu/dataset/34/diabetes

To help understand the transformation, below is a visual comparison of how raw event-based logs are transformed into structured time-series records for modeling.

<div align="center">

<table>
  <tr>
    <td align="center"><strong>Table 3.1: Raw Event-Based Data</strong></td>
    <td></td>
    <td align="center"><strong>Table 3.2: Processed Time-Series Data</strong></td>
  </tr>
  <tr>
    <td><img src="https://github.com/user-attachments/assets/a9ff9fd5-4cda-4f1f-901e-230de855933a" width="360"/></td>
    <td align="center" style="vertical-align: middle;">
      <img src="https://e7.pngegg.com/pngimages/856/761/png-clipart-arrow-free-content-arrow-pointing-left-angle-rectangle.png" width="60"/>
    </td>
    <td><img src="https://github.com/user-attachments/assets/d4b6eccb-2697-4c4d-9821-d0f557c649aa" width="460"/></td>
  </tr>
</table>

</div>

These transformations were key to structuring the input sequences used by the hybrid LSTM-GRU model.


---

## 🏗️ Model Architecture

Our baseline Hybrid LSTM-GRU model consists of stacked LSTM and GRU layers followed by dense layers. The Residual Sequence Learning Model extends this by adding residual connections between recurrent blocks, along with normalization and dropout, to improve learning stability and accuracy.
<img width="971" height="689" alt="Architecture (2)" src="https://github.com/user-attachments/assets/d1efc10b-dec6-485b-b0f4-0d28330fc2f6" />

## ⚙️ Algorithm

The following summarizes the Residual Hybrid Network for Insulin Dose Prediction:
<div align="center"> <img width="1273" height="747" alt="image" src="https://github.com/user-attachments/assets/b47e08d3-2884-466e-8806-a108f8bbdde8" /></div>


## 📊 Results and Performance
We compared the proposed model with baseline architectures.
<div align="center"><img width="655" height="198" alt="image" src="https://github.com/user-attachments/assets/49db5e3c-e6e3-4701-a86c-172c51c03765" /></div>
➡️ The Residual Sequence Learning Model improved R² from 0.52–0.62 (baselines) to 0.805, while reducing MAE by ~10% and MSE by ~60%.



## 🔭 Future Work

- **Multi-output Prediction**: Extend the model to predict additional insulin types such as NPH and UltraLente.
- **Reinforcement Learning Integration**: Incorporate reinforcement learning to enable adaptive insulin dosage strategies based on real-time glucose response and patient history.
- **Attention Mechanisms**: Integrate attention or Transformer-based layers to enhance interpretability and focus on influential time steps.
- **Cross-Dataset Testing**: Evaluate the model on additional diabetes datasets to improve robustness and generalization.

---

## 📌 Final Hybrid Model

The final model integrates both LSTM and GRU units and processes patient sequences to predict personalized insulin dosage.You can check it out here:
[Hybrid Model](https://drive.google.com/file/d/10JspsXdBGk9TsfWnc3f7zO8Rk5nA15hW/view?usp=sharing).


