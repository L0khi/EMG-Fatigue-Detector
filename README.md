# 🧠 EMG Fatigue Detector (Prototype, 2025)

**Signal-Based Fatigue Classification using EMG Features**

This project analyzes Electromyography (EMG) signals to detect signs of muscle fatigue using domain-informed feature extraction and machine learning classification. It leverages a real-world biomedical dataset (NinaPro DB2) with signals captured across 49 hand gestures from multiple subjects.

---

## 📂 Dataset

- **Source:** [NinaPro DB2](https://ninapro.hevs.ch/instructions/DB2.html)
- **Format:** `.mat` files containing:
  - `emg`: Raw EMG signal (12 channels)
  - `restimulus`: Task/gesture label
  - `repetition`: Repetition number
  - Additional: `acc`, `glove`, `inclin`, etc.

- **Fatigue Labels:** Simulated dynamically using repetition counts and signal windows, validated using RMS and MDF trend behaviors from fatigue literature.

---

## 🔬 Feature Engineering

Features are extracted per EMG window (200 ms sliding with 50% overlap):

| Domain          | Features                                 |
|-----------------|-------------------------------------------|
| Time            | RMS, MAV, Zero Crossing, WL, SSC         |
| Frequency       | Median Frequency (MDF), Mean Frequency   |
| Time-Frequency  | Band Power (Wavelets), STFT-based energy |
| Statistical     | Variance, Std, Kurtosis, Skewness        |

Combined 60+ features per window.

---

## 🧠 Model Training

| Model           | Details                          |
|-----------------|----------------------------------|
| Classifier      | XGBoost                          |
| Balancing       | Stratified undersampling (equal fatigue classes) |
| Train-Test Split| 80/20 stratified                 |

Final Class Distribution: Fatigue(1): 50%, Non-Fatigue(0): 50%

---

## 🧪 Results (Balanced Test Set)

| Metric        | Value     |
|---------------|-----------|
| Accuracy      | **96.0%** |
| Precision     | 0.98 / 0.94 |
| Recall        | 0.93 / 0.98 |
| ROC-AUC       | **0.9929** |

📈 *Classification performance reflects realistic intra-subject variability and window-level fatigue transitions.*

---

## 📊 Visualizations

- Confusion matrix
- Fatigue trend over repetitions
- RMS & MDF dynamic visualization per gesture

---

## 📁 Folder Structure

