# Hospital-Records-Data-Analysis-Report

## 1. Introduction

This project analyzes hospital patient records collected between 2021 and 2024. The dataset contains information about patients, their medical conditions, treatments received, admission and discharge date, DOB, gender, and hospital bill amounts.

This project analyzes hospital records from 2021 to 2024 to uncover patterns in patient demographics, medical conditions, hospital admissions, length of stay, and billing. 

The goal is to provide clear insights that can help hospital management understand trends, identify areas of concern,identify high-cost medical conditions and treatments, and improve healthcare resource planning, and make more informed decisions.


## 2. Data Description
The dataset used for this analysis is the Hospital Record Dataset, which contains summarized Hospital Record Analysis from the year 2021-2024 and was gotten from Kaggel link 
[Hospital Record](https://www.kaggle.com/datasets/devildyno/hospital-patient-records-jan-2021-july-2024)

The dataset contains **1,000 patient records** and **10 columns**.

### Key Variables

| Column | Description |
|---|---|
| Patient ID | Unique identifier assigned to each patient |
| Name | Patient's name |
| Date of Birth | Patient's date of birth |
| Gender | Patient's gender |
| Medical Condition | Medical condition diagnosed |
| Treatments | Treatment provided to the patient |
| Doctor's Notes | Additional notes recorded by the doctor |
| Admit Date | Date the patient was admitted |
| Discharge Date | Date the patient was discharged |
| Bill Amount ($) | Total hospital bill for the patient |

### Dataset Period

- **Number of Patients:** 1,000
- **Admission Period:** July 2021 – August 2024
- **Total Hospital Bills:** $9,590,629.57
- **Average Bill:** $9,590.63
- **Median Bill:** $3,356.23
- **Minimum Bill:** $102.55
- **Maximum Bill:** $99,769.22


## 3. Methodology

The tools used for this cleaning and preparation are Microsoft Excel and Microsoft Power BI

The analysis was carried out using the following steps:

1. **Data inspection**
   - Reviewed the dataset structure and available variables.
   - Checked the number of records and columns.
   - Checked for duplicates.
   - Checked for missing values
   - Checked for incorrect data types
   - Checked for data errors
  
   
 2. **Data cleaning/Preparation**

     **No duplicates Found**
   
     **Missing/Blank values**
   - Checked important columns such as Patient ID, Medical Condition, Admit Date, Discharge Date, and Bill Amount for missing values, No missing value found
   
     **Incorrect data types**
   -  Converted admission, Date of birth, and discharge dates column into date formats, from MM/D/YY to D/MM/YY
   
   **Age calculation**
   -  Calculated Age at Admission using DOB and Admit Date and created a new column (Age at admission)
   -  Created age groups column for easier analysis with the name (Age group):
    * Early Childhood(0-4)
    * Children & Adolescents(5-17)
    * Young Adults(18-24)
    * Adults(25-59)
    * Older Adults(60+)
  
   **length of stay calculation**
   - Calculated the length of stay using discharge date minus admitted date and created a new column(Length of Stay)
  
   - **Invalid DOB and Admit date**
   - Some record had a Date of Birth that occured after the Admit Date.
   - This is logically impossible and would produce incorrect ages.
   - instead of deleting the records, i flagged them as "Invalid DOB" and excluded them from age related analysis
   - Rows affected = 13 rows affected
  
   **3 more columns where added in the dataset which are :**
   * Lenght of stay
   * Age at admisssion
   * Age group
  
  **Data Quality Issues**
  During data cleaning, some records were identified where the patient’s Date of Birth occurred after the Admission Date. Since these    records could result in incorrect age calculations, they were flagged as “Invalid DOB” and excluded from age-based analysis while being retained in the original dataset.

**Calculated Measures**
1. Total Patients =
DISTINCTCOUNT('Hospital'[Patient ID])
2. Average Bill per Patient =
DIVIDE(
    [Total Bill Amount],
    [Total Patients])
3. Total Admissions =
COUNTROWS('Hospita[admit date]l')
4. Total medical condition = DISTINCTCOUNT(Sheet1[Medical Condition])

**Visualization Techniques**

The following power Bi visuals were utilized

 *KPI cards
 
 *Clustered Bar Charts
 
 *Clusterd Column Charts
 
 *Donut Charts
 
 *Line Chart
 
 *Slicers

**Dashboard Development**

The project consist of 3 Dashboard pages

**Overview**
**Patient & Medical**
**Bill Analysis**

# 4. Analysis & Findings

## 4.1 Patient Demographics

The dataset contains 1,000 patients.

### Gender Distribution

- **Female:** 511 patients (51.1%)
- **Male:** 489 patients (48.9%)

The gender distribution is relatively balanced, although female patients slightly outnumber male patients.

### Age Group Distribution

| Age Group | Patients |
|---|---:|
| Older Adults | 382 |
| Adults | 361 |
| Children and Adolescent | 106 |
| Young Adults | 89 |
| Early Childhood | 49 |
| Invalid DOB | 13 |

Older adults represent the largest patient group, followed by adults.

This indicates that the hospital serves a large proportion of mature and elderly patients, which may increase demand for chronic disease management and specialized care.

## 4.2 Medical Conditions

The dataset contains **30 different medical conditions**.

The most frequently recorded conditions include:

| Medical Condition | Patients |
|---|---:|
| Skin Infection | 46 |
| Alzheimer's Disease | 46 |
| Migraine | 43 |
| Stroke | 42 |
| Bronchitis | 41 |

Skin Infection and Alzheimer's Disease were the most frequently recorded conditions, with 46 patients each.

Stroke was also among the most common conditions, with 42 patients.


## 4.3 Hospital Revenue

The total value of hospital bills in the dataset was:

**$9,590,629.57**

The average patient bill was approximately:

**$9,590.63**

However, the median bill was only:

**$3,356.23**

This large difference between the average and median indicates that some patients generated exceptionally high bills, which significantly increased the overall average.

The highest recorded individual bill was:

**$99,769.22**


## 4.4 Revenue by Year

| Year | Patients | Revenue ($) | Average Bill ($) | Avg. Length of Stay |
|---|---:|---:|---:|---:|
| 2021 | 155 | 1,509,148.22 | 9,736.44 | 14.88 |
| 2022 | 326 | 3,555,482.43 | 10,906.39 | 16.00 |
| 2023 | 352 | 3,075,452.97 | 8,737.08 | 16.04 |
| 2024 | 167 | 1,450,545.95 | 8,685.90 | 15.02 |

### Key Finding

2023 recorded the highest number of patients with **352 patients**.

However, 2022 generated the highest revenue at approximately **$3.56 million**.

This occurred because the average bill per patient was higher in 2022.


## 4.5 Length of Stay

The average patient stayed in the hospital for approximately:

**15.68 days**

Other statistics include:

- **Minimum stay:** 1 day
- **Maximum stay:** 30 days
- **Median stay:** 16 days
- **Total patient-stay days:** 15,675 days

The relatively high average length of stay suggests that the hospital manages many cases requiring extended treatment and monitoring.

## 4.6 Revenue by Medical Condition

The medical conditions generating the highest total billing were:

| Medical Condition | Patients | Revenue ($) | Average Bill ($) |
|---|---:|---:|---:|
| Cancer | 36 | 2,149,429.29 | 59,706.37 |
| Chronic Kidney Disease | 35 | 982,518.26 | 28,071.95 |
| Heart Disease | 29 | 929,046.88 | 32,036.10 |
| Stroke | 42 | 841,902.04 | 20,045.29 |
| COVID-19 | 25 | 672,418.30 | 26,896.73 |

### Key Finding

Cancer generated the highest revenue despite having only 36 patients.

The average cancer-related bill was approximately **$59,706**, making it one of the most expensive conditions in the dataset.

Chronic Kidney Disease and Heart Disease also generated significant revenue.


## 4.7 Treatment Analysis

Medication was the most frequently recorded treatment.

| Treatment | Patients | Revenue ($) | Average Bill ($) |
|---|---:|---:|---:|
| Medication | 192 | 2,470,272.64 | 12,866.00 |
| Physical Therapy | 92 | 1,025,331.60 | 11,144.91 |
| Rest | 63 | 82,860.11 | 1,315.24 |
| Antibiotics | 56 | 166,608.93 | 2,975.16 |
| Lifestyle Changes | 46 | 141,828.50 | 3,083.23 |
| Surgery | 44 | 1,337,586.27 | 30,399.69 |

Medication accounted for the highest number of patient treatments and also generated the highest total billing.

Surgery had a much smaller patient count but a considerably higher average bill.


## 4.8 High-Cost Treatments

Some treatments had relatively high average bills.

| Treatment | Average Bill ($) |
|---|---:|
| Chemotherapy | 64,982.90 |
| Radiation Therapy | 48,823.95 |
| Surgery | 30,399.69 |
| Dialysis | 26,735.69 |
| Ventilation | 25,668.42 |
| Speech Therapy | 19,457.21 |

### Key Finding

Chemotherapy had the highest average bill at approximately **$64,983 per patient**.

This is followed by Radiation Therapy at approximately **$48,824** per patient.

These treatments are associated with high-cost medical conditions and should be carefully considered when planning hospital resources and financial management.


# 5. Insights

### 1. Older adults represent the largest patient group

Older adults account for **382 patients**, making them the largest age group in the dataset.

This suggests that the hospital should maintain adequate resources for age-related and chronic medical conditions.

### 2. Female patients slightly outnumber male patients

Females account for 51.1% of patients while males account for 48.9%.

The difference is relatively small, indicating a fairly balanced gender distribution.

### 3. Cancer is the largest revenue-generating condition

Cancer generated approximately **$2.15 million**, making it the highest-revenue medical condition.

Although only 36 patients were recorded with cancer, their average bill was approximately $59,706.

### 4. Medication is the most common treatment

Medication was administered to **192 patients**, significantly more than any other treatment.

This indicates a high demand for medication-related services and pharmaceutical resources.

### 5. High-cost treatments have a major impact on revenue

Treatments such as chemotherapy, radiation therapy, surgery, and dialysis have relatively high average bills.

These treatments may require specialized equipment, healthcare professionals, and longer-term resource planning.

### 6. Patient volume does not always determine revenue

2023 had the highest number of patients, with 352 patients.

However, 2022 generated more revenue because the average bill per patient was considerably higher.

This demonstrates that patient volume alone is not enough to measure hospital financial performance.

### 7. The dataset contains some data quality issues

There are **13 records with invalid date-of-birth/age information**.

These records are classified as "Invalid DOB."

Improving data validation would make demographic analysis more reliable.

### 8. Hospital stays are relatively long

The average length of stay is approximately **15.68 days**.

This indicates significant hospital resource utilization and suggests that bed occupancy and discharge planning should be closely monitored.


# 6. Recommendations

## 1. Improve Management of High-Cost Conditions

Hospital management should closely monitor high-cost conditions such as:

- Cancer
- Chronic Kidney Disease
- Heart Disease
- Stroke
- COVID-19

Understanding the resources and costs associated with these conditions can help improve budgeting and financial planning.


## 2. Optimize Bed and Resource Management

With an average length of stay of approximately 15.68 days, hospital beds may remain occupied for extended periods.

The hospital should improve:

- Discharge planning
- Bed allocation
- Patient monitoring
- Treatment scheduling
- Follow-up care

## 4. Improve Patient Data Quality

The presence of invalid DOB and age records indicates the need for stronger data-entry validation.

The hospital should ensure that:

- Dates of birth are correctly entered.
- Admission dates are validated.
- Discharge dates are validated.
- Age is automatically calculated from DOB.
- Patient IDs remain unique.

## 5. Monitor High-Cost Treatments

Treatments such as chemotherapy, radiation therapy, surgery, and dialysis should be monitored carefully because of their high average costs.

Management can use regular cost analysis to identify unnecessary expenses and improve resource allocation.

## 6. Maintain Adequate Medication Supply

Medication is the most frequently used treatment in the dataset.

The hospital should maintain appropriate medication inventory levels to prevent shortages while avoiding excessive stock that may expire.

## 7. Use Data Dashboards for Continuous Monitoring

Hospital management should consider developing an interactive dashboard that tracks:

- Total patients
- Total revenue
- Average bill
- Patient demographics
- Medical conditions
- Treatments
- Length of stay
- Revenue by year
- Revenue by medical condition
- Revenue by treatment

This would allow management to make faster and more data-driven decisions.


# 7. Conclusion

The analysis of 1,000 hospital records from 2021 to 2024 provides useful insights into patient demographics, medical conditions, treatments, hospital stays, and financial performance.

The hospital generated approximately **$9.59 million** in total patient bills, with an average bill of approximately **$9,590.63**.

Older adults were the largest patient group, while female patients slightly outnumbered male patients.

Cancer was the highest revenue-generating medical condition, while medication was the most frequently used treatment.

The analysis also shows that high-cost treatments such as chemotherapy, radiation therapy, surgery, and dialysis have a significant impact on hospital revenue.

Overall, the findings demonstrate the importance of using healthcare data to improve resource allocation, financial planning, patient management, treatment capacity, and operational decision-making.

A hospital management dashboard based on these findings could provide management with a real-time overview of patient activity, revenue, medical conditions, treatments, and hospital utilization.

   
