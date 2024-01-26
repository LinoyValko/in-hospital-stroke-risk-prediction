Project Overview:

This project, led by Moriya Yulzari and Linoy Valko, aims to predict the risk of in-hospital stroke among patients treated with catheterization. The project utilizes a dataset obtained from the MIMIC-IV database, comprising information about patients' medical history and outcomes.

Background:

Every year, a substantial number of catheterizations are performed, with a potential risk of post-procedure complications, such as blood clot formation leading to strokes. The identification of at-risk patients is crucial for prioritizing treatment and preventing adverse events. This project addresses this challenge using machine learning.

Aim of the Project:

The primary goal is to create a predictive model that classifies patients into two groups: those who had a stroke during hospitalization after catheterization and those who did not. The model aims to assist medical professionals in prioritizing treatments based on predicted stroke risk, thereby minimizing errors in patient prioritization and allowing better focus on prevention.

Data Variables:

has_stroke_disease: Outcome variable indicating the occurrence of stroke (0: No, 1: Yes)
subject_id: Patient ID
hamd_id: Patient hospitalization number
gender: Gender of the patient (0: Female, 1: Male)
anchor_age: Patient's age in years
Additional variables indicating the presence of specific diseases based on ICD codes.
Data Preprocessing
The dataset was filtered to include only patients who underwent catheterization. Categorical variables, such as gender, were encoded. No numeric variables were used, eliminating concerns about outliers and scaling.

Methodology:

1. Model Selection Attempted SVM initially but faced challenges with class imbalance.
2. Experimented with random forest, achieving moderate results.
3. Finalized the logistic regression model due to good precision and recall scores.

Evaluation Metrics:

Accuracy, recall, and precision were chosen as evaluation metrics.
Challenges
Imbalance in the outcome variable addressed through undersampling.

Results:

Logistic regression with a reduced ratio of stroke to non-stroke cases achieved the best results (Precision: 0.93, Recall: 1, Accuracy: 97.26%).

Recommendations:

Model Selection: Logistic regression with a balanced ratio yielded optimal results.

Data Expansion: Consider expanding the dataset with numeric features for further improvement.

Hyperparameter Tuning: Experiment with different hyperparameter values for models.

Generalization: Address the challenge of class imbalance for better generalization.

Acknowledgments
The project utilizes data from the MIMIC-IV database.

Inspiration from "Ischemic Strokes After Cardiac Catheterization-Opportune Thrombolysis Candidates" article.
