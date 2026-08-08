# 🏋️ Body Performance Analytics & Intelligent Classification System

An end-to-end Machine Learning project for analyzing physical performance data, identifying important performance-related factors, classifying individuals into four performance categories (A–D), and predicting broad jump distance.

## 📌 Project Overview

This project applies the complete Machine Learning workflow to the **Body Performance Dataset**, including:

- Data Understanding
- Data Cleaning & Validation
- Exploratory Data Analysis (EDA)
- Feature Engineering
- Data Preprocessing
- Classification
- Regression
- Hyperparameter Tuning
- Cross-Validation
- Model Evaluation
- Model Comparison

### 🎯 Project Objectives

The project addresses two main Machine Learning tasks:

**1. Classification**

Predict the participant's performance class:

`A / B / C / D`

**2. Regression**

Predict the participant's:

`broad_jump_cm`

---

## 📊 Dataset

The original dataset contains:

- **13,393 records**
- **12 features**
- Physical fitness and body-performance measurements

### Features

| Feature | Description |
|---|---|
| `age` | Participant age |
| `gender` | Participant gender |
| `height_cm` | Height in centimeters |
| `weight_kg` | Weight in kilograms |
| `body_fat_%` | Body fat percentage |
| `diastolic` | Diastolic blood pressure |
| `systolic` | Systolic blood pressure |
| `gripForce` | Hand grip strength |
| `sit_and_bend_forward_cm` | Flexibility measurement |
| `sit_ups_counts` | Number of sit-ups |
| `broad_jump_cm` | Standing broad-jump distance |
| `class` | Performance category (A–D) |

After data-quality validation and cleaning, the final dataset contained **13,371 valid observations**.

---

# 🔎 Exploratory Data Analysis

The analysis investigated:

- Data types
- Missing values
- Duplicate records
- Invalid measurements
- Distributions
- Outliers
- Categorical variables
- Correlations
- Age vs. performance
- Feature relationships

### Key Findings

- The four performance classes are highly balanced.
- `gripForce` and `broad_jump_cm` showed a strong positive correlation.
- `sit_ups_counts` and `broad_jump_cm` also showed a strong positive correlation.
- Body fat showed negative relationships with major performance measures.
- Performance generally declined with increasing age.
- `sit_and_bend_forward_cm` emerged as the most important feature in the Decision Tree.
- Blood-pressure variables showed very weak relationships with fitness-performance variables.

---

# 🧹 Data Preprocessing

The preprocessing stage included:

- Removing duplicate records
- Detecting physiologically impossible values
- Removing invalid observations
- Encoding categorical variables
- Encoding the target class
- Feature scaling using `StandardScaler`
- Preparing separate feature matrices and targets for classification and regression

Domain-based validation was used rather than treating every statistical outlier as an error.

---

# 🤖 Machine Learning Models

## Classification Models

The following algorithms were evaluated:

1. K-Nearest Neighbors (KNN)
2. Decision Tree
3. Random Forest
4. Support Vector Machine (SVM)
5. Neural Network (MLP)

## Regression Model

- Linear Regression

---

# 🏆 Classification Results

| Model | Best Accuracy | F1 Score |
|---|---:|---:|
| 🥇 Random Forest | **74.32%** | **0.74** |
| 🥈 Tuned SVM (RBF) | **71.71%** | ~0.72 |
| SVM (Default) | 69.84% | 0.70 |
| Decision Tree (Pruned) | 67.66% | 0.68 |
| Decision Tree (Unpruned) | 64.56% | 0.64 |
| KNN (k=30) | 62.77% | 0.63 |
| KNN (k=5) | 58.99% | 0.59 |

### 🥇 Best Classification Model

**Random Forest**

```text
Number of Trees: 100
Maximum Depth: 9
Accuracy: 74.32%
Macro F1: 0.74
```

Random Forest achieved the strongest classification result among the correctly configured models.

---

# 📏 Regression Results

Linear Regression was used to predict `broad_jump_cm`.

### 80:20 Train/Test Split

```text
MSE  = 335.91
RMSE = 18.33 cm
R²   = 0.7773
```

### 5-Fold Cross-Validation

```text
Mean R² = 0.7915
Std     = ±0.0102
```

The model showed stable performance across different train/test splits and explained a substantial proportion of the variation in broad-jump distance.

---

# 🔬 Important Insights

### 💪 Physical Performance Relationships

Some of the strongest observed relationships included:

- Grip Force ↔ Broad Jump: **r = 0.752**
- Sit-ups ↔ Broad Jump: **r = 0.750**
- Height ↔ Grip Force: **r = 0.736**
- Height ↔ Weight: **r = 0.735**

### 🧘 Feature Importance

The Decision Tree identified:

```text
sit_and_bend_forward_cm → 0.4387
```

as the most important feature, followed by:

```text
sit_ups_counts
age
body_fat_percent
weight_kg
```

### 📉 Age & Body Fat

Age and body fat showed important negative relationships with several physical-performance measurements.

---

# 🧠 Neural Network

A Multi-Layer Perceptron (MLP) was also investigated using a three-layer architecture with dropout regularization.

The reported experiment reached approximately **74.23% test accuracy**.

However, the final model comparison identified a target-encoding implementation issue in one Neural Network experiment, where the model was configured with 304 classes instead of the intended four classes.

Therefore, the Neural Network requires correction and retraining before its performance can be fairly compared with the other classifiers.

---

# 📁 Repository Contents

```text
Body-performance-Analytics/
│
├── project_body_performance.ipynb
├── bodyPerformance.csv
├── Body-Performance-Analytics-and-Intelligent-Classification-System.pdf
├── AI_ML_Final_Report for dr-body performance.docx
└── README.md
```

### Files

**`project_body_performance.ipynb`**  
Complete Jupyter Notebook containing data analysis, preprocessing, model training, evaluation, and visualizations.

**`bodyPerformance.csv`**  
Dataset used for the analysis and Machine Learning experiments.

**`Body-Performance-Analytics-and-Intelligent-Classification-System.pdf`**  
Final project report.

**`AI_ML_Final_Report for dr-body performance.docx`**  
Editable version of the project report.

---

# 🛠️ Technologies

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Machine Learning
- Exploratory Data Analysis
- Data Visualization
- Cross-Validation
- Hyperparameter Tuning

---

# 🚀 How to Run

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/Body-performance-Analytics.git
```

### 2. Open the project folder

```bash
cd Body-performance-Analytics
```

### 3. Install the required libraries

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

### 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

Then open:

```text
project_body_performance.ipynb
```

and run the notebook cells sequentially.

---

# 🔮 Future Work

Future improvements could include:

- Correcting and retraining the Neural Network
- Performing more extensive Random Forest hyperparameter tuning
- Applying SHAP for model interpretability
- Exploring additional non-linear models
- Investigating feature interactions
- Evaluating alternative feature-selection strategies
- Expanding the dataset for improved representation

---

# 📚 Project Deliverables

This repository provides:

📓 **Jupyter Notebook**  
📊 **Dataset**  
📄 **PDF Report**  
📝 **Editable Report**

---

## 👩‍💻 Academic Project

**Body Performance Analytics and Intelligent Classification System**

Developed as part of the:

**Introduction to Artificial Intelligence and Machine Learning**

---

## ⭐ Key Takeaway

> Physical performance is influenced by multiple interacting factors rather than a single measurement.  
> This project demonstrates how Machine Learning can uncover these relationships, classify performance levels, and predict physical performance outcomes.
