# 🛑 Driver Drowsiness Detection

A deep learning-based system to detect driver drowsiness in real-time using facial expressions and eye movement analysis. This project aims to improve road safety by alerting drivers when signs of drowsiness are detected.

---

## 🚀 Project Overview

This model classifies a driver's state into **drowsy** or **alert** based on video frame analysis. Using a combination of **CNN** and **LSTM** architectures, it captures both spatial and temporal features for accurate detection.

---

## 🧠 Model Architecture

- **Input:** Video frames (128x128)
- **Preprocessing:** Face detection, resizing, normalization
- **Model:** CNN layers for spatial features + LSTM for temporal sequence modeling
- **Output:** Binary classification (Drowsy / Not Drowsy)

---

## 🔍 Features

- Real-time detection using webcam or video
- Custom deep learning architecture (CNN + LSTM)
- Alerts for drowsiness detection
- Trained on [Driver Drowsiness Dataset (DDD)](https://www.kaggle.com/datasets/ismailnasri20/driver-drowsiness-dataset-ddd)

---

## 📁 Dataset

- **Source:** Kaggle  
- **Classes:** `Drowsy`, `Not Drowsy`  
- **Input Shape:** Sequences of frames, each resized to 128x128

---

## 📊 Experiments

| Experiment | Model Description                                                                 | Epochs             | Batch Size | Accuracy | Loss   | Val Accuracy |
| ---------- | ---------------------------------------------------------------------------------- | ------------------ | ---------- | -------- | ------ | ------------- |
| 1          | CNN (1 layer) + GlobalAvgPool + Bidirectional LSTM(64), Dense(32), Dropout(0.3)   | 10                 | 16         | 62.90%   | 0.6506 | 64.72%        |
| 2          | CNN (3 layers: 32→64→128) + LSTM(64), Dropout(0.5), Dense(64), Adam LR=0.0001      | 10                 | 32         | 92.05%   | 0.2605 | 92.11%        |
| 3          | CNN (3 layers: 8→16→32) + BatchNorm + LSTM(16), Dense(8), Dropout(0.3)             | 10                 | 32         | 92.37%   | 0.2532 | 98.57%        |
| 4          | CNN (4 layers: 8→16→32→48) + LSTM(32), Dense(32), Dropout(0.5), Regularization     | 10 (EarlyStopping) | 32         | 99.58%   | 0.1221 | 99.69%        |
| 5          | CNN (3 layers: 8→16→48) + LSTM(32), Dense(32), Dropout(0.5), Regularization        | 20 (EarlyStopping) | 32         | 98.27%   | 0.1393 | 99.13%        |

---

## 🛠️ Tech Stack

- Python
- TensorFlow / Keras
- OpenCV
- NumPy
- Matplotlib

---

## 🎯 How to Run

```bash
git clone https://github.com/yourusername/driver-drowsiness-detection.git
cd driver-drowsiness-detection
pip install -r requirements.txt
python detect_drowsiness.py
```
## 📸 Sample Images

Here are a few examples from the detection system:

### 🟡 Drowsy Driver Detection

![Drowsy Driver](images/Screenshot%202025-06-12%20153731.png)

### 🟢 Awake Driver Detection

![Awake Driver](images/Screenshot%202025-06-12%20153717.png)

---

## 📌 License

This project is licensed under the MIT License.
