#  Short-Term Blood Glucose Forecasting Using Hybrid Deep Learning
📌 Project Overview

This project focuses on short-term blood glucose forecasting using Continuous Glucose Monitoring (CGM) time-series data.
The objective is to predict the next glucose value (15 minutes ahead) using a sequence of past CGM readings.
A hybrid deep learning and meta-learning framework is proposed, combining:

LSTM (Long Short-Term Memory)

GRU (Gated Recurrent Unit)

Random Forest and Linear Regression as meta-learners

The system is designed for time-series forecasting, not long-term diabetes progression or clinical outcome prediction.


🎯 Problem Statement

Continuous Glucose Monitoring systems generate high-frequency glucose readings that reflect rapid physiological changes.
Accurate near-future glucose prediction is essential for:

Early detection of hypoglycemia and hyperglycemia

Real-time alerts and decision support

Smart diabetes monitoring applications

This project addresses the challenge of learning temporal glucose patterns using CGM data alone, without relying on insulin, meal, or lifestyle inputs.

📂 Dataset

Source: Mendeley Data – Diabetes Progression Prediction Dataset

Subjects Used: 25

Data Used:

EventDateTime (timestamp)

CGM (glucose value)

Sampling:
Original: ~5-minute intervals

Resampled to: 15-minute intervals

Window Size:
60 past timesteps (≈ 15 hours)

Prediction Horizon:
Next CGM value (t + 1) → 15 minutes ahead

⚠️ Only CGM values and timestamps are used.
This is time-series forecasting, not disease progression prediction.


🧠 Methodology

1. Data Preprocessing
   
Timestamp alignment and resampling

Missing value interpolation

Noise reduction using smoothing

Min–Max normalization

4. Sequence Construction
   
Sliding window approach

Input: CGM values from t−60 to t

Output: CGM value at t+1

6. Deep Learning Models
   
LSTM: Captures long-term glucose dependencies

GRU: Captures short-term fluctuations

8. Meta-Learner Fusion
   
Predictions from LSTM and GRU are combined

Linear Regression and Random Forest learn optimal fusion

Random Forest provides final refined prediction



📊 Models Implemented

Linear Regression

Random Forest

XGBoost

LSTM

GRU

Hybrid LSTM + GRU + Random Forest (Final Model)


📈 Evaluation Metrics

Models are evaluated using:

RMSE (Root Mean Square Error)

MAE (Mean Absolute Error)

R² Score

These metrics assess forecasting accuracy, not clinical outcomes.



✅ Key Outcomes

Hybrid LSTM–GRU–RF model outperforms individual models

Effectively captures both smooth trends and sharp glucose changes

Demonstrates strong alignment with real CGM trajectories

Suitable for real-time glucose forecasting systems



🚫 What This Project Does NOT Do

This project does NOT predict:

Diabetes progression

HbA1c changes

Insulin requirements

Risk of complications

Long-term health outcomes

The scope is intentionally limited to short-term glucose forecasting.



🛠️ Tech Stack

Python

TensorFlow / Keras

Scikit-learn

Pandas

NumPy

Matplotlib
