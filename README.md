# Explainable Early Mortality Risk Prediction in Sepsis Patients
Explainable early mortality risk prediction in sepsis patients using clinical and temporal features, with machine learning and SHAP explanations.


**Machine Learning | Healthcare Analytics | Explainable AI (SHAP)**

## Project Overview

This project develops a machine learning pipeline to predict hospital mortality risk among ICU stays identified as sepsis-related using clinical diagnosis text. It uses clinical measurements and temporal features derived from the first 24 hours of ICU data to compare predictive models and explain their outputs using SHAP (SHapley Additive exPlanations).

The project focuses on the trade-off between identifying patients who die in hospital and avoiding false alarms. It is an academic healthcare analytics project and is **not a clinically validated decision-support system**.

## Objectives

- Prepare a sepsis-related ICU cohort from the eICU Collaborative Research Database Demo.
- Engineer clinical summary and temporal features from the first 24 hours.
- Train and compare Logistic Regression, Random Forest, XGBoost, and CatBoost.
- Evaluate models using ROC-AUC, PR-AUC, accuracy, balanced accuracy, mortality recall, and specificity.
- Use SHAP to interpret influential features and improve model transparency.
- Communicate model results and healthcare insights through visualizations and a Power BI dashboard.

## Dataset

This project uses the **eICU Collaborative Research Database Demo v2.0.1**.

The project pipeline initially examined 2,520 ICU stays belonging to 1,841 patients. After sepsis-related cohort selection and excluding stays with ambiguous or missing hospital outcomes, the working cohort contained:

| Cohort measure | Count |
|---|---:|
| ICU stays in the final cohort | 376 |
| Hospital deaths | 64 |
| Survivors | 312 |

The dataset is intended for research and educational use. Refer to the official eICU documentation and applicable data-use terms before accessing or redistributing data.

## Methodology

1. **Cohort selection:** Identify sepsis-related ICU stays using diagnosis and admission text.
2. **Outcome definition:** Derive the hospital mortality target from hospital discharge status.
3. **Preprocessing:** Clean and prepare clinical measurements and outcome labels.
4. **Feature engineering:** Calculate first-24-hour clinical summaries and temporal features.
5. **Model training:** Train Logistic Regression, Random Forest, XGBoost, and CatBoost.
6. **Evaluation:** Compare classification performance, particularly mortality recall and false-positive trade-offs.
7. **Explainability:** Use SHAP to investigate which features influence model predictions.
8. **Visualization:** Present cohort characteristics, model performance, predictions, and feature importance.

## Models

- Logistic Regression — baseline model
- Random Forest — tree-based ensemble
- XGBoost — gradient-boosted trees
- CatBoost — gradient-boosted trees

## Evaluation Metrics

- **ROC-AUC:** Discrimination between survivors and non-survivors.
- **PR-AUC:** Precision-recall performance, particularly useful for an imbalanced outcome.
- **Accuracy:** Overall proportion of correct predictions.
- **Balanced accuracy:** Average recall across the two outcome classes.
- **Mortality recall:** Proportion of deaths correctly identified.
- **Specificity:** Proportion of survivors correctly identified.

In this project, a model with higher mortality recall may identify more deaths but also generate more false positives. Model selection therefore requires consideration of multiple metrics rather than accuracy alone.

## Explainable AI

SHAP is used to estimate how features contribute to model predictions. The analysis helps identify influential clinical and temporal variables, such as respiratory rate, age, red cell distribution width (RDW), and heart rate, where supported by the model outputs.

## Technology Stack

- Python
- Pandas and NumPy
- Scikit-learn
- XGBoost
- CatBoost
- SHAP
- Matplotlib and Seaborn
- Google Colab / Jupyter Notebook


## How to Run

1. Clone or download this repository.
2. Open the notebook in Google Colab or Jupyter Notebook.
3. Obtain access to the eICU Demo dataset through its official source and follow its data-use requirements.
4. Update the dataset paths in the notebook to match your environment.
5. Install the required Python packages.
6. Run the notebook cells in order to reproduce cohort preparation, feature engineering, model evaluation, and SHAP analysis.

## Limitations

- The cohort is selected using diagnosis and admission text matching; this may not capture every sepsis case or perfectly define a clinical sepsis cohort.
- The demo dataset is limited in size and may not represent the wider ICU population.
- The number of deaths is relatively small, so evaluation metrics can be unstable.
- Results depend on the selected features, preprocessing, train-test split, and classification threshold.
- Predictive associations do not establish causation.
- The model has not been externally validated or approved for clinical use.

## Team

- **Ravi Kumar Kushwaha** — BTech 
- **Rohit Kindarle** — BTech CSE 
