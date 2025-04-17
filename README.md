#Predicting Hospital Readmission for Diabetic Patients
---

## 🎯Overview:
This project focuses on predicting hospital readmissions for diabetic patients using a historical medical claims dataset from U.S. hospitals. The primary goal is to identify the likelihood of patient readmission, with an aim to improve the quality of care, reduce unnecessary hospital visits, and minimize healthcare costs.

By leveraging patient data—such as lab results, administered medications, demographic information, and diagnosis codes.

The dataset, collected over ten years (1999–2008) from 130 U.S. hospitals, contains over 50 variables for inpatient diabetic encounters, including details on lab tests, medication history, and visit frequency.
Extracted 'Diabetes 130-US Hospitals for Years 1999-2008' dataset from [Kaggle](https://www.kaggle.com/datasets/brandao/diabetes/data) using Kaggle API:

- __Diabetes 130-US Hospitals for Years 1999-2008__


In this project, we have utilized the above-mentioned dataset, which contains **101,766 records** of various details of diabetic patients. Key features include:

| Feature                         | Relevance to Churn                                                   |
|---------------------------------|----------------------------------------------------------------------|
| **encounter_id**                | Unique identifier of an encounter                                         |
| **patient_nbr**                 | Unique identifier of a patient                                           |
| **race**                        | Values: Caucasian, Asian, African American, Hispanic, and other                                                 |
| **gender**                      | Values: male, female, and unknown/invalid                             |
| **age**                         | Grouped in 10-year intervals: [0, 10), [10, 20),..., [90, 100)                                                  |
| **weight**                      | Weight in pounds                                         |
| **admission_type_id**           | Integer identifier corresponding to 9 distinct values, for example, emergency, urgent, elective, newborn, and not available                                                         |
| **discharge_disposition_id**    | Integer identifier corresponding to 29 distinct values, for example, discharged to home, expired, and not available                                                      | 
| **admission_source_id**         | Integer identifier corresponding to 21 distinct values, for example, physician referral, emergency room, and transfer from a hospital                                                      |
| **time_in_hospital**            | Integer number of days between admission and discharge                                                   |
| **payer_code**                  | Integer identifier corresponding to 23 distinct values, for example, Blue Cross/Blue Shield, Medicare, and self-pay                                                |
| **medical_specialty**           | Integer identifier of a specialty of the admitting physician, corresponding to 84 distinct values, for example, cardiology, internal medicine, family/general practice, and surgeon                                              |
| **num_lab_procedures**          | Number of lab tests performed during the encounter                                                        |
| **num_procedures**              | Number of procedures (other than lab tests) performed during the encounter                                                    |
| **num_medications**             | Number of distinct generic names administered during the encounter                                              |           
| **number_outpatient**           | Number of outpatient visits of the patient in the year preceding the encounter                                                     | 
| **number_emergency**            | Number of emergency visits of the patient in the year preceding the encounter                                                       |
| **number_inpatient**            | Number of inpatient visits of the patient in the year preceding the encounter           |
| **diag_1**                      | The primary diagnosis (coded as first three digits of ICD9); 848 distinct values                                              |           
| **diag_2**                      | Secondary diagnosis (coded as first three digits of ICD9); 923 distinct values                                                     | 
| **diag_3**                      | Additional secondary diagnosis (coded as first three digits of ICD9); 954 distinct values                                                       |
| **number_diagnoses**            | Number of diagnoses entered to the system           |
| **max_glu_serum**               | Indicates the range of the result or if the test was not taken. Values: >200, >300, normal, and none if not measured                                              |           
| **A1Cresult**                   | Indicates the range of the result or if the test was not taken. Values: >8 if the result was greater than 8%, >7 if the result was greater than 7% but less than 8%, normal if the result was less than 7%, and none if not measured                                                     | 
| **23 features for medications** | For the generic names: The features indicates whether the drug was prescribed or there was a change in the dosage. Values: “up” if the dosage was increased during the encounter, “down” if the dosage was decreased, “steady” if the dosage did not change, and “no” if the drug was not prescribed                                                       |
| **change**                      | Indicates if there was a change in diabetic medications (either dosage or generic name). Values: change and no change           |
| **diabetesMed**                 | Indicates if there was any diabetic medication prescribed. Values: yes and no                                              |           
| **readmitted**                  | (Target Variable) Days to inpatient readmission. Values: <30 if the patient was readmitted in less than 30 days, >30 if the patient was readmitted in more than 30 days, and No for no record of readmission                                                      | 


## ⚙️Methods
The project employs time series analysis techniques, including:

- __Data Extraction__
- __Data Cleaning & Preprocessing__
- __Feature Engineering__
- __Modeling__
- __Pediction and Evaluation__


  

## 🛠️ Tools & Technologies
- __Programming Language:__ Python
- __Libraries:__ NumPy, Pandas, Seaborn, Matplotlib, Scikit-learn, XGBoost
- __Environment:__ Jupyter Notebook

The final tuned model, while showing only modest improvements in accuracy, exhibits strong recall performance, which is particularly valuable in clinical settings where missing a high-risk patient can have serious consequences.

The results can empower healthcare professionals to:

- Target high-risk individuals for follow-up interventions

- Reduce hospital penalties and optimize resource allocation

- Improve the overall patient care journey and healthcare spending efficiency

With further refinement and integration into real-time clinical systems, such models can play a vital role in advancing value-based care and improving patient outcomes.
