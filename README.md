# Heart Disease Prediction — Machine Learning Coursework

> A machine learning project comparing four classification algorithms to predict the presence of heart disease in patients.

---

## 📁 Repository Contents

| File | Description |
|---|---|
| `heart.csv` | The dataset used for training and testing |
| `heart_disease_ml.ipynb` | Main Jupyter notebook with all models |
| `README.md` | Project documentation |

---

## 📊 Dataset Overview

**Source:** UCI Heart Failure Prediction Dataset  
**Rows:** 918 patients  
**Columns:** 12  
**Target:** `HeartDisease` — 0 (No Disease) / 1 (Disease)

### Target Distribution
| Class | Count | Percentage |
|---|---|---|
| No Heart Disease (0) | 410 | 44.7% |
| Heart Disease (1) | 508 | 55.3% |

### Feature Descriptions

| Feature | Type | Description |
|---|---|---|
| `Age` | Numerical | Age of the patient in years |
| `Sex` | Categorical | M = Male, F = Female |
| `ChestPainType` | Categorical | ATA, NAP, ASY, TA |
| `RestingBP` | Numerical | Resting blood pressure (mm Hg) |
| `Cholesterol` | Numerical | Serum cholesterol (mg/dl) |
| `FastingBS` | Binary | Fasting blood sugar > 120 mg/dl (1 = Yes, 0 = No) |
| `RestingECG` | Categorical | ECG results — Normal, ST, LVH |
| `MaxHR` | Numerical | Maximum heart rate achieved |
| `ExerciseAngina` | Categorical | Exercise-induced angina — Y / N |
| `Oldpeak` | Numerical | ST depression induced by exercise |
| `ST_Slope` | Categorical | Slope of peak exercise ST segment — Up, Flat, Down |
| `HeartDisease` | Binary | **Target variable** — 0: No, 1: Yes |

---

## ⚙️ Preprocessing

- Categorical columns encoded using **One-Hot Encoding** (`drop_first=True`)
- Train / Test split: **80% / 20%** with stratification to preserve class balance
- **StandardScaler** applied for Linear Regression, Logistic Regression, and Naive Bayes
- Decision Tree does **not** require scaling

---

## 🤖 Models & Steps

### Step 2 — Load & Prepare Data
Load `heart.csv`, explore shape and missing values, encode categorical features, and split into train/test sets.

### Step 3 — Decision Tree
- Trained with `max_depth=4`
- Visualised using `plot_tree()`
- No scaling required
- Outputs: tree diagram, feature importances, confusion matrix

### Step 4 — Linear Regression
- Not a native classifier — continuous output thresholded at **0.5** to produce binary predictions
- Included as a conceptual baseline
- Outputs: predicted value distribution, confusion matrix

### Step 5 — Logistic Regression
- Best suited for binary classification problems
- Outputs: confusion matrix, ROC curve with AUC, feature coefficients chart

### Step 6 — Naive Bayes
- Uses `GaussianNB` — assumes feature independence
- Fast and effective even on smaller datasets
- Outputs: confusion matrix

### Step 7 — ROC Curves
All four models plotted together on a single ROC curve chart with AUC scores for comparison.

### Step 8 — Summary & Comparison
Full comparison table and grouped bar chart across all models.

---

## 📈 Results

| Model | Accuracy | Precision | Recall | F1 Score |
|---|---|---|---|---|
| Decision Tree | 83.7% | 85.2% | 87.4% | 86.3% |
| Linear Regression* | 89.1% | 90.5% | 90.5% | 90.5% |
| Logistic Regression | 88.6% | 90.3% | 89.8% | 90.0% |
| Naive Bayes | **91.3%** | **91.9%** | **93.3%** | **92.6%** |

*Linear Regression output thresholded at 0.5 for binary classification

> **Best Model: Naive Bayes** — achieved the highest accuracy (91.3%) and F1 score on this dataset.

---

## 🚀 How to Run

1. Open [JupyterLite](https://jupyter.org/try-jupyter/lab/) in your browser
2. Upload `heart.csv` and `heart_disease_ml.ipynb`
3. Open the notebook and run **Kernel → Restart & Run All**

> ⚠️ JupyterLite runs entirely in the browser (Pyodide). The notebook handles package installation and data loading automatically — no setup required.

---

## 🛠️ Libraries Used

- `pandas` — data loading and manipulation
- `numpy` — numerical operations
- `matplotlib` & `seaborn` — visualisations
- `scikit-learn` — machine learning models and metrics

---

## 👩‍💻 Author

**Viola Makishtii**  
Heart Disease Prediction — Machine Learning Coursework
