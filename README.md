# Student Mental Health Early Detection System

## Overview
This project builds an end-to-end pipeline to detect early signs of mental health risk in students using academic and stress-related factors. It includes preprocessing, exploratory analysis, and multiple machine learning models, with the best-performing model reported below.

### Problem Statement
Early signs of student mental health challenges are subtle and often missed, making timely intervention difficult for educators and counselors.

### Objective
Identify at-risk students early so universities can provide timely support and reduce long-term negative effects.

## Domain: Education / Mental Health
By analyzing patterns like attendance, grades, and self-reported stress factors, the system flags students who may be at risk. Early detection helps reduce dropouts, improve wellbeing, and support academic performance.

## Repository Structure
- `Data/Raw/StressLevelDataset.csv` — Source dataset (Kaggle)
- `notebooks/` — Individual preprocessing steps (missing values, encoding, scaling, etc.)
- `models/` — Individual model notebooks (KNN, SVM, Logistic Regression, Decision Tree, Random Forest, MLP)
- `Preprocess_group_pipeline.ipynb` — Group preprocessing pipeline (end-to-end)
- `Model_group_pipeline.ipynb` — Group modeling pipeline (training + evaluation)
- `results/`
  - `Outputs/preprocessed_stress_level_dataset.csv` — Final cleaned dataset
  - `Preprocess_Eda_visualizations/` — EDA charts from preprocessing
  - `model_Eda_visualizations/` — Training/Model EDA (accuracy/loss curves, confusion matrix)

## Dataset
- Dataset: Student Stress Factors — A Comprehensive Analysis
- Source: Kaggle — https://www.kaggle.com/datasets/rxnach/student-stress-factors-a-comprehensive-analysis?resource=download
- Type: Tabular (structured)
- Local path: `Data/Raw/StressLevelDataset.csv`

## Best Model: MLP (Multilayer Perceptron)
The MLP model achieved the best performance during evaluation (variety 2 with Keras callbacks).

Test Accuracy: 0.9091

Classification Report:

               precision    recall  f1-score   support

           0       0.88      0.89      0.89        74
           1       0.96      0.94      0.95        72
           2       0.89      0.89      0.89        74

    accuracy                           0.91       220
   macro avg       0.91      0.91      0.91       220
weighted avg       0.91      0.91      0.91       220

### Model Training Visualizations
The following plots are generated during training and saved under `results/model_Eda_visualizations/`:

![Accuracy over epochs](results/model_Eda_visualizations/Accuracy%20graph.png)

![Loss over epochs](results/model_Eda_visualizations/Loss%20graph.png)

![Confusion Matrix](results/model_Eda_visualizations/Confusion%20Matrix.png)

## Group Members and Roles
| Name | IT Number | Preprocessing Role | Model |
|------|-----------|--------------------|-------|
| Jayanath P.A.P.R | IT24104387 | Min-Max Scaling | KNN |
| Bandara I G C | IT24100307 | Outlier removal | MLP (Best Model) |
| Liyanage J A K | IT24100479 | Dimensional Reduction | Decision Tree |
| Makshuma B.G.K.J. | IT24100821 | Feature selection | SVM |
| Rodrigo H.V.O | IT24100890 | One Hot Encoding | Random Forest |
| Dasanayake H.T.N. | IT24100967 | Handling missing data | Logistic Regression |

## How to Run

### Prerequisites
- Python 3.8+
- Install dependencies:

```bash
pip install -r requirements.txt
```

### Local (Jupyter)
1. Open `Preprocess_group_pipeline.ipynb` and run all cells to generate `results/Outputs/preprocessed_stress_level_dataset.csv`.
2. Open `Model_group_pipeline.ipynb` and run all cells to train models and produce metrics/visualizations.

### Google Colab
Option A — Upload files directly:
1. Upload `Preprocess_group_pipeline.ipynb` to Colab and run it. When prompted, upload `Data/Raw/StressLevelDataset.csv`.
2. Then upload and run `Model_group_pipeline.ipynb`.

Option B — Mount Google Drive (recommended if running repeatedly):
1. Upload the repository folder to your Drive.
2. In the first cell, mount Drive and set the path to `Data/Raw/StressLevelDataset.csv`.

Outputs (preprocessed CSV and plots) will be saved under `results/` and can be downloaded from the Colab Files sidebar.

## Results
- Preprocessed dataset: `results/Outputs/preprocessed_stress_level_dataset.csv`
- Preprocess EDA visuals: `results/Preprocess_Eda_visualizations/`
- Model training visuals: `results/model_Eda_visualizations/`

## Project Goals
- Collect and preprocess student academic and stress-related data from the Kaggle dataset.
- Train multiple ML models to detect early signs of mental health risk.
- Report the best model (MLP) with metrics and provide training/EDA artifacts.
