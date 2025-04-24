**1. Introduction**

DESCRIPTION: Beginning in the spring of 2009, the H1N1 influenza virus, commonly referred to as "swine flu," swept across the globe. It is estimated that in the first year, swine flu was responsible for 363,000 deaths worldwide.

OBJECTIVE: The objective of this project is to identify individuals who will not receive a swine flu vaccine. Predicting individuals who will not receive the vaccine will help to inform the CDC’s marketing strategies. To do this, I have analyzed over 26,000 data points collected via phone call through the National 2009 H1N1 Flu Survey. This survey was administered by the National Center for Health Statistics in collaboration with the CDC.
DEFINING KEY TERMS: Throughout this notebook, when the term “unvaccinated” is used, it refers specifically to the annual swine flu vaccinestill recommended today by the CDC.
METHODOLOGY: Logistic Regression
TARGET: h1n1_vaccine
1 represents no vaccine
0 represents vaccine
PERFORMANCE METRICS: Performance will be evaluated according to the area under the receiver operating characteristic curve (ROC) along with the accuracy, recall, precision, and f1 scores. A higher value indicates stronger performance.

**2. Description of the Data:**

*From the DrivenData Website *36 Columns Total *For all binary variables: 0 = No; 1 = Yes
respondent_id: unique and random identifier
h1n1_concern - Level of concern about the H1N1 flu. 0 = Not at all concerned; 1 = Not very concerned; 2 = Somewhat concerned; 3 = Very concerned
h1n1_knowledge - Level of knowledge about H1N1 flu. 0 = No knowledge; 1 = A little knowledge; 2 = A lot of knowledge
behavioral_antiviral_meds - Has taken antiviral medications. (binary)
behavioral_avoidance - Has avoided close contact with others with flu-like symptoms. (binary)
behavioral_face_mask - Has bought a face mask. (binary)
behavioral_wash_hands - Has frequently washed hands or used hand sanitizer. (binary)
behavioral_large_gatherings - Has reduced time at large gatherings. (binary)
behavioral_outside_home - Has reduced contact with people outside of own household. (binary)
behavioral_touch_face - Has avoided touching eyes, nose, or mouth. (binary)
doctor_recc_h1n1 - H1N1 flu vaccine was recommended by doctor. (binary)
doctor_recc_seasonal - Seasonal flu vaccine was recommended by doctor. (binary)
chronic_med_condition - Has any of the following chronic medical conditions: asthma or an other lung condition, diabetes, a heart condition, a kidney condition, sickle cell anemia or other anemia, a neurological or neuromuscular condition, a liver condition, or a weakened immune system caused by a chronic illness or by medicines taken for a chronic illness. (binary)
child_under_6_months - Has regular close contact with a child under the age of six months. (binary)
health_worker - Is a healthcare worker. (binary)
health_insurance - Has health insurance. (binary)
opinion_h1n1_vacc_effective - Respondent's opinion about H1N1 vaccine effectiveness. 1 = Not at all effective; 2 = Not very effective; 3 = Don't know; 4 = Somewhat effective; 5 = Very effective.
opinion_h1n1_risk - Respondent's opinion about risk of getting sick with H1N1 flu without vaccine. 1 = Very Low; 2 = Somewhat low; 3 = Don't know; 4 = Somewhat high; 5 = Very high.
opinion_h1n1_sick_from_vacc - Respondent's worry of getting sick from taking H1N1 vaccine. 1 = Not at all worried; 2 = Not very worried; 3 = Don't know; 4 = Somewhat worried; 5 = Very worried.
opinion_seas_vacc_effective - Respondent's opinion about seasonal flu vaccine effectiveness. 1 = Not at all effective; 2 = Not very effective; 3 = Don't know; 4 = Somewhat effective; 5 = Very effective.
opinion_seas_risk - Respondent's opinion about risk of getting sick with seasonal flu without vaccine. 1 = Very Low; 2 = Somewhat low; 3 = Don't know; 4 = Somewhat high; 5 = Very high.
opinion_seas_sick_from_vacc - Respondent's worry of getting sick from taking seasonal flu vaccine. 1 = Not at all worried; 2 = Not very worried; 3 = Don't know; 4 = Somewhat worried; 5 = Very worried.
age_group - Age group of respondent.
education - Self-reported education level.
race - Race of respondent.
sex - Sex of respondent.
income_poverty - Household annual income of respondent with respect to 2008 Census poverty thresholds.
marital_status - Marital status of respondent.
rent_or_own - Housing situation of respondent.
employment_status - Employment status of respondent.
hhs_geo_region - Respondent's residence using a 10-region geographic classification defined by the U.S. Dept. of Health and Human Services. Values are represented as short random character strings.
census_msa - Respondent's residence within metropolitan statistical areas (MSA) as defined by the U.S. Census.
household_adults - Number of other adults in household, top-coded to 3.
household_children - Number of children in household, top-coded to 3.
employment_industry - Type of industry respondent is employed in. Values are represented as short random character strings.
employment_occupation - Type of occupation of respondent. Values are represented as short random character strings.

**3. Model Performance**

The final model was a logistic regression model with gridsearched parameters.

Accuracy: 83.99%.
Recall: 95.11%.
Precision: 86.04%.
F1-Score: 90.35%.
ROC AUC Score: 68.905%.

![272706730-ae41d4cd-e0d7-438a-8164-0e65ccdb71e2](https://github.com/user-attachments/assets/090e5211-65b6-406a-a2ba-04e5fcc761e8) ![272706689-d15fb01a-027f-4f38-9de7-c77d674df2bc](https://github.com/user-attachments/assets/34b816b4-d7a9-4a0f-a48d-233de619a405)

MODEL INTERPRETATION: While the final model’s overall accuracy score was 84%, the recall rate was 95%. This tells us that of individuals who will not receive the vaccine, the model will accurately predict 95% of them. This is good news for us because, for this business question, we are mostly concerned with identifying unvaccinated individuals. It won’t hurt to market to an individual who will indeed get the vaccine. We would rather err on the side of identifying a larger volume of unvaccinated individuals. Let’s take a sneak peak at what this machine learning model tells us.

**4. Model Predictions**
 
Using the model, we generated predictions. The predictions revealed the following trends in the data. Note that these visualizations are from the Power BI Dashboard .

Income: 

<img width="285" alt="272707547-00fd7cea-3e8d-4143-8cb8-038ce3566cee" src="https://github.com/user-attachments/assets/0f67b567-1bfd-4ee1-a696-acf267c7cbb8" />

Income: 

<img width="285" alt="272707547-00fd7cea-3e8d-4143-8cb8-038ce3566cee-1" src="https://github.com/user-attachments/assets/a88726a4-469e-4f93-aed5-311833b6cca4" />


Sex and Age:

<img width="449" alt="272709659-c4a4e9ef-926a-4da3-966d-4217bb39c6b3" src="https://github.com/user-attachments/assets/4c35fe7a-ee30-4e8c-b5b3-a8bca7313a44" />


Employment Status:

<img width="273" alt="272710757-f850472d-4e26-41b8-bf99-6ed11165c1d3" src="https://github.com/user-attachments/assets/3e0dfc1d-5c32-426a-a1fc-2e0aa954fe8a" />

Race: 

<img width="790" alt="272712991-9fbdf7cc-7c0e-4dbd-8354-5957c0e6c912" src="https://github.com/user-attachments/assets/a731a9cb-27c0-4fe1-9ca2-5dee61750b47" />


Doctor Recommendation:

<img width="323" alt="272709073-21aa5d4e-3a09-4f7e-8ca1-a61d443f6ff5" src="https://github.com/user-attachments/assets/7fa9591d-9523-4510-a3b4-230cae7ca3b0" />


Education: 

<img width="419" alt="272707722-1a335dc9-63bd-4355-9648-c702b71a496a" src="https://github.com/user-attachments/assets/29ffa1c8-7edd-42c0-b107-caee020c73e3" />

Rent / Home Home

<img width="771" alt="272712807-fb9564ac-6128-4b6c-a8ee-e0ab87e37764" src="https://github.com/user-attachments/assets/f2b50a9d-841b-46e3-8982-0fedd65146da" />



