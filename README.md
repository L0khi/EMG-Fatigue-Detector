# 🧠 EMG Fatigue Detector – Biosignal-Based Muscle Fatigue Classification

This project explores the feasibility of using **electromyography (EMG)** signals to detect early signs of muscle fatigue in physically intensive tasks. It is designed as a **baseline biomedical signal processing prototype** simulating occupational stress scenarios in fields like skilled trades, healthcare, and ergonomic research.

---

## 📌 Objective

Develop a data-driven pipeline that:
- Preprocesses EMG time-series signals
- Extracts relevant features (RMS, mean/median frequency, FFT power)
- Trains a machine learning classifier to distinguish fatigued vs. non-fatigued states

This prototype serves as a starting point for **fatigue risk detection systems** in workplace injury prevention, rehabilitation monitoring, and human performance research.

---

## 🧠 Key Techniques

| Component              | Description |
|------------------------|-------------|
| **Signal Processing**  | RMS, FFT, Median/Mean Frequency |
| **ML Model**           | XGBoost Classifier (baseline) |
| **Evaluation**         | ROC-AUC, Confusion Matrix, F1-score |
| **Preprocessing**      | Scaling, artifact removal, segmentation |
| **Tools**              | Python, NumPy, SciPy, Matplotlib, Scikit-learn, XGBoost |

---

## 🔬 Results Summary

This prototype model was trained and tested on pre-labeled EMG data from multiple sessions. Due to signal complexity, label noise, and minimal domain-specific filtering, this version achieves **baseline classification metrics** as shown below.

| Metric         | Value     |
|----------------|-----------|
| Accuracy       | 62.0%     |
| Precision (1)  | 63%       |
| Recall (1)     | 59%       |
| F1-Score (1)   | 61%       |
| ROC-AUC        | 0.6724    |

> ⚠️ **Note**: These results reflect an early-stage exploration without full calibration or sensor placement optimization. The goal is to demonstrate the **pipeline feasibility**, not production-readiness.

---
