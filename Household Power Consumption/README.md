# ⚡ Household Power Consumption — ML Analysis & Prediction

> **DSC478 · Programming Machine Learning**  
> Predicting electricity usage patterns through regression, classification, ensemble learning, and clustering.

---

## 📋 Table of Contents

- [Problem Statement](#problem-statement)
- [Dataset](#dataset)
- [Project Pipeline](#project-pipeline)
- [Models Implemented](#models-implemented)
- [Results](#results)
- [Clustering Analysis](#clustering-analysis)
- [Installation](#installation)
- [Usage](#usage)
- [Future Work](#future-work)

---

## 🎯 Problem Statement

This project analyzes **household power consumption** time-series data to:

1. **Regression** — Predict the continuous value of global active power consumption.
2. **Classification** — Classify whether power usage is **high** or **low** based on a median threshold.

The goal is to build accurate predictive models that improve understanding of energy consumption behavior and support decision-making in energy management systems.

---

## 📦 Dataset

| Property | Detail |
|---|---|
| **Source** | Household Power Consumption (UCI) |
| **Records Used** | ~500,000 |
| **Features** | Global active power, reactive power, voltage, global intensity, sub-metering 1–3 |
| **Target (Regression)** | `Global_active_power` (continuous) |
| **Target (Classification)** | `high_usage` (binary: 1 if above median, else 0) |

**Engineered Features:** `Hour`, `DayOfWeek`, `Month`, `IsWeekend`

---

## 🔄 Project Pipeline

```
Raw Data
  │
  ▼
Data Preprocessing
  ├── Handle missing values ('?' → NaN → forward fill)
  ├── Parse DateTime → extract Hour, Day, Month, IsWeekend
  ├── Create binary target: high_usage (above median)
  └── Feature scaling (StandardScaler for LR & K-Means)
  │
  ▼
Exploratory Data Analysis
  ├── Time-series trend visualization
  ├── Power by hour / day / month
  ├── Feature correlation matrix
  └── Distribution analysis
  │
  ▼
Model Training & Evaluation
  ├── Regression: Linear Regression, Random Forest Regressor
  ├── Classification: Logistic Regression, Random Forest Classifier
  ├── Ensemble: Voting Classifier (Soft Voting)
  └── Clustering: K-Means (k=4)
```

---

## 🤖 Models Implemented

### Regression
| Model | Train RMSE | Test RMSE | Train R² | Test R² |
|---|---|---|---|---|
| Linear Regression | 0.5126 | 0.5097 | 0.7635 | 0.7632 |
| **Random Forest Regressor** | — | **0.2900** | — | **0.9234** |

### Classification
| Model | F1-Score | ROC-AUC |
|---|---|---|
| Logistic Regression | 0.8667 | 0.9360 |
| Random Forest Classifier | 0.9586 | 0.9938 |
| **Voting Ensemble** | **0.9287** | **0.9858** |

### Ensemble — Voting Classifier (Soft Voting)
Combines:
- Logistic Regression
- Random Forest Classifier
- Gradient Boosting Classifier

```
Voting Ensemble F1-Score : 0.9287
Voting Ensemble AUC      : 0.9858
Overall Accuracy         : 93%
```

---

## 📊 Key EDA Findings

- **Peak hours:** 19:00–21:00 (highest average power ~1.8 kW)
- **Weekends** show noticeably higher consumption than weekdays
- **Winter months** (Jan, Dec) exhibit the highest energy usage
- `Global_intensity` and `Sub_metering_3` are strongly correlated with global active power

---

## 🔵 Clustering Analysis

K-Means clustering (k=4) segmented consumption into four behavioral groups:

| Cluster | Avg Hour | Avg Power | Interpretation |
|---|---|---|---|
| 0 | 14.9 | 0.97 kW | Afternoon — moderate usage |
| 1 | 3.6 | 0.42 kW | Nighttime / Early morning |
| 2 | 15.4 | 3.25 kW | Afternoon — **peak usage** |
| 3 | 14.5 | 0.96 kW | Afternoon — moderate usage |

**Silhouette Score:** `0.2303`

---

## 🛠️ Installation

```bash
# Clone the repository
git clone https://github.com/your-username/household-power-ml.git
cd household-power-ml

# Create a virtual environment
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

### Requirements

```
pandas
numpy
scikit-learn
matplotlib
seaborn
jupyter
```

---

## 🚀 Usage

```bash
# Launch Jupyter Notebook
jupyter notebook

# Or run the main script directly
python main.py
```

> Download the dataset from the [UCI ML Repository](https://archive.ics.uci.edu/ml/datasets/individual+household+electric+power+consumption) and place it in the `/data` directory.

---

## 🔮 Future Work

- [ ] Hyperparameter tuning via `GridSearchCV` / `RandomizedSearchCV`
- [ ] Deep learning with **LSTM** for time-series forecasting
- [ ] Training on the full dataset (~2M records) for better generalization
- [ ] Real-time prediction pipeline / API deployment
- [ ] Anomaly detection for unusual consumption spikes

---

## 📄 License

This project was developed as part of **DSC478 – Programming Machine Learning** coursework.
