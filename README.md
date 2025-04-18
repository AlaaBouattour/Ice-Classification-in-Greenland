
# Ice Classification in Greenland

This project focuses on detecting the presence of ice in Greenland using **infrasound signal data** and **meteorological features**. It was developed as part of a machine learning lab project at Université Paris-Saclay (M2QF).

## Objective

To build and evaluate several supervised learning models to **classify ice presence** (binary classification) based on infrasound signal intensity and other temporal features.

---

## 🛠️ Methodology

### 1. Data Preprocessing
- **Target binarization**: `Y1 > 0` is labeled as ice presence (`1`), `Y1 = 0` as no ice (`0`).
- **Feature engineering**: Temporal features (month, day, year) were extracted from timestamps.
- **Exploratory analysis**: Seasonal patterns were identified in the data.
- **Train/val/test split**: Ensured robust evaluation and no data leakage.

### 2. Models Trained

| Model                  | ROC-AUC | Precision | Recall | F1-Score |
|------------------------|---------|-----------|--------|----------|
| Decision Tree          | 0.811   | 0.684     | 0.661  | 0.672    |
| Weighted Decision Tree | 0.873   | 0.563     | 0.831  | 0.671    |
| **Random Forest**      | 0.839   | 0.737     | 0.712  | **0.724** |
| XGBoost                | 0.804   | **0.804** | 0.627  | 0.705    |
| Extra Trees            | 0.825   | 0.755     | 0.678  | 0.714    |

---

## Best Model

**Random Forest** yielded the most balanced performance, achieving the highest F1-score while maintaining strong ROC-AUC and precision.

---

## Key Learnings

- The **month** feature carried strong predictive power due to seasonal ice patterns.
- **Weighted classifiers** significantly improved recall for minority classes.
- **Precision-recall threshold tuning** is critical for imbalanced classification tasks.
