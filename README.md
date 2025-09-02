# Predicting In-Hospital Stroke Risk After Catheterization  
---

## Project Overview  
This project aims to **predict the risk of in-hospital stroke** among patients treated with **catheterization**, using data from the **MIMIC-IV** database.  
The model is designed to support medical professionals in identifying high-risk patients and improving prioritization in clinical settings.

---

## Background  
Catheterization is a widely performed medical procedure. Despite its benefits, it carries the risk of complications such as **blood clot formation**, which can lead to **ischemic strokes**.  
Timely identification of at-risk patients is critical for **early intervention** and **stroke prevention**.  
This project leverages machine learning to address this challenge.

---

## Aim of the Project  
To develop a **predictive model** that classifies patients into two groups:
- Patients **without** an in-hospital stroke after catheterization  
- Patients **with** an in-hospital stroke after catheterization  

**Objective:**  
Improve treatment prioritization and minimize preventable strokes during hospitalization.

---

## Data Description

**Source:** [MIMIC-IV](https://physionet.org/content/mimiciv/2.2/) medical database  
**Target Variable:**
- `has_stroke_disease`:  
  - `0` – No in-hospital stroke  
  - `1` – In-hospital stroke occurred  

**Key Features:**

| Variable         | Description                                      |
|------------------|--------------------------------------------------|
| `subject_id`     | Patient identifier                               |
| `hadm_id`        | Hospital admission ID                            |
| `gender`         | Gender (0: Female, 1: Male)                      |
| `anchor_age`     | Age in years                                     |
| ICD features     | Comorbidities based on diagnosis codes           |

**Preprocessing Highlights:**
- Included only patients who underwent catheterization  
- Categorical variables were encoded  
- No need for normalization (no continuous numeric variables)  

---

## Methodology  

1. **Model Selection:**
   - Initial model: **SVM** → poor results due to class imbalance  
   - Second model: **Random Forest** → moderate results  
   - Final model: **Logistic Regression** → best balance of performance metrics  

2. **Class Imbalance Handling:**
   - Used **undersampling** of the majority class (non-stroke)

3. **Evaluation Metrics:**
   - **Precision** – correctness of positive stroke predictions  
   - **Recall** – how many actual strokes were identified  
   - **Accuracy** – overall correct predictions  

---

## Results  

| Metric     | Score    |
|------------|----------|
| Precision  | 0.93     |
| Recall     | 1.00     |
| Accuracy   | 97.26%   |

Best results were achieved using **Logistic Regression** with a balanced dataset.

---

## Recommendations  

- **Model:** Logistic Regression is effective when balanced  
- **Features:** Add numeric features (e.g., lab data) to improve performance  
- **Tuning:** Use regularization and hyperparameter search  
- **Imbalance:** Continue handling with sampling or weighted losses

---

## Acknowledgments  

- Dataset from **MIMIC-IV**  
- Research inspired by:  
  *“Ischemic Strokes After Cardiac Catheterization – Opportune Thrombolysis Candidates”*

---
