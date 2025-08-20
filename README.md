# Panic_Attack_Analysis
## Panic Attack Analysis
### Table of Contents :
- Problem Statement 
- Datasource 
- Data Preparation
- Data Analysis (DAX)
- Data Visualization Dashboard
- Insights

### Problem Statement :
The objective of this project is to create a Panic Attack Monitoring Dashboard in Power BI for healthcare professionals and researchers. The dashboard provides insights into panic attack frequency, triggers, demographics, and treatment effectiveness, helping in early detection and patient care improvement.

Possible KPIs include (but are not limited to):

- Total Number of Panic Attacks
- Panic Attack Frequency by Patient / Month
- Average Panic Attack Duration
- Most Common Triggers (Stress, Caffeine, Lack of Sleep, etc.)
- Panic Attack Severity (Average Intensity Score)
- Panic Attack Distribution by Age & Gender
- Panic Attacks During Treatment vs. Before Treatment
- % of Patients with Reduced Episodes after Therapy
- Medication vs. Non-Medication Effectiveness

### Datasource :

The dataset used for this analysis contains patient-reported panic attack events, demographics, and treatment details.

- Dataset: Panic Attack Event Data
- Rows: ~5,000 observations
- Columns: ~20 attributes (Patient ID, Age, Gender, Date, Time, Trigger, Severity, Duration, Treatment Status, etc.)

### Data Preparation :

Performed data cleaning and transformation in Power Query:

- Removed duplicate patient event records
- Standardized categorical values (Yes/No, Trigger categories)
- Validated correct data types (numeric for duration, categorical for triggers, datetime for event timestamps)
- Created calculated fields for Attack Frequency, Severity Index, and Improvement %

## Data Analysis (DAX):
  
Measures used in  all visualization are:
 
% Patients Dizziness = `DIVIDE(COUNTROWS(FILTER('panic_attack_dataset',panic_attack_dataset[Dizziness]=TRUE())),COUNTROWS('panic_attack_dataset'),0) *100`
Age group Switch = `SWITCH(TRUE(),'panic_attack_dataset'[Age]<=17, "Child", panic_attack_dataset[Age]<=24,"Adolescent",panic_attack_dataset[Age]<=64,"Adult","Senior")`

## Data Visualization (Dashboard) :

Data visualization for the data analysis (DAX) was done in Microsoft Power BI Desktop:

Shows visualizations from Pizza Sales Dashborad :
| Number of Patients by Symptoms |
| ----------- |
| ![Panic Attack](https://github.com/rohitaage17/Pizza_Sales_Dashoboard/blob/main/Pizza_Sales_Dashboard.png) |

| Other Requirments |
| ----------- |
| ![Panic Attack](https://github.com/rohitaage17/Pizza_Sales_Dashoboard/blob/main/Best_Worst_Pizza_Sales.png) |

| Age group Analysis|
| ----------- |
| ![Panic Attack](https://github.com/rohitaage17/Pizza_Sales_Dashoboard/blob/main/Best_Worst_Pizza_Sales.png) |

## Insights :

From the analysis, the following can be observed:
  
- Sweating (836) & Shortness of Breath (746) are strong indicators of panic attacks.
- Chest Pain, while less frequent, is medically significant and should not be ignored.
- Insufficient sleep (≤5 hrs), moderate alcohol intake, and longer panic attack durations (20–40 min) are strongly associated with a higher number of patients experiencing panic attacks.
- Lifestyle factors (sleep & alcohol) appear to play a significant role in both the frequency and severity of panic episodes.
- Adolescents tend to experience higher panic scores with caffeine and phobia triggers.
- Adults show more severe impact of PTSD and social anxiety compared to adolescents.
- Sleep hours remain fairly consistent across both groups (~6.4–6.7 hrs), indicating sleep alone isn’t the differentiator—the type of trigger matters more by age.



