# 🫀 Health Care Report Analysis

 
## Project Overview
The Healthcare report is a comprehensive data visualisation dashboard designed to track, monitor
and analyse key hospital and patient metrics. It consolidates operational data-ranging from financial performance and patient demographics to clinical conditions and treatment distributions.

[dashboard](https://github.com/user-attachments/assets/fc982bbf-cd32-4e3f-81d8-6455a1966f65)



## Data Source

The **Healthcare Report** is gotten from kaggle.


### Tools

- Excel - Data cleaning [Download here](https://microsoft.com)
- SQL Server - Data Analysis [Download here](https://mysqlserver.com)
- Power BI - For DAX Measures and creating visualisation


### Data Cleaning/Preparation

In the initial data preparation phase, I performed the following tasks:
1. Data loading and Inspection
2. Handling missing values
3. Handling inconsistency in names
4. Change data type
5. Data Cleaning and formatting
6. Loading data into the model


### Exploratory Data Analysis

EDA  involved exploring the sales data to answer key questions, such as:


- Total billing Amount
- Patient demographic
- Total & Average length of stay
- Blood type distribution


## Data Analysis

Include some interesting code/feature worked with

```sql
-- count by age
-- 18 - 35 Young Adult
-- 36 - 60 Adult
-- 61- 80 Old
SELECT
	CASE
		WHEN Age < 36 THEN 'Young Adult'
        WHEN Age < 61 THEN 'Adult'
        ELSE 'Old'
   END AS `Age range`,    
   ROUND(SUM(`Billing amount`),0) AS `Total Amount`
FROM  `healthcare_dataset 6`
GROUP BY `Age range`
ORDER BY `Total Amount` DESC;
```


### Results/Findings
1. The facility recorded a total billing amount of **₦43.78** across the analysed period.
2. The healthcare system maintains a large active staff base 0f **1,700 total doctors**.
3. The average age of patients utilising the facility is **52 years** reflecting an older demographic.
4. Cumulative hospital stay reached **27,016 total days**, resulting in a high average length of stay
   of **16 days per patient**.
5. Patient intake channels show an even distribution across **Emergency(583)**, **Elective(574)**, and **Urgent(583)**
   admissions.



   ### Recommendation
   Based on the analysis, we recommend the following actions;

   - Since Patient volumes experience a sharp, sustained increase during the first the final quarter-peaking at 161         patients in November-hospital administration should front-load staff scheduling, shift locations, and leave            planning ahead of October to prevent burnout and maintain service quality.
  
   - Ensure pharmacy and medical inventory(particularly for common medications like Liptor, Paracetamol,Penicillin,
     Ibupropen, and Aspirin) are scaled up to by late September to match the incoming Q4 volume spike.
   - Providing proactive community outreach  or tele health check-ins for chronic patients can help catch acute flares        early, balancing out the evenly distributed emergency(583) and urgent(555) admission pathways,
   - Given that the top medical conditions are dominated by chronic illness like asthma (319 patients),cancer(300           patients), obesity, arthritis, hypertension and diabetes, the facility should implement dedicated outpatient           screening and preventive management clinics.
  
### Limitations
1. Missing values, dirty data and incorrect data types

### References

- kaggle healthcare dataset [download here](https://www.kaggle.com)
- Applied Frameworks : Utilizes Power Query for ETL data cleaning pipeline, and DAX Measures(such as aggregation, filterimg and calculated columns for length of stay and billing summaries).
   



