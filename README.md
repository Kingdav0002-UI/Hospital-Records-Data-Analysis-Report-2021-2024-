# Hospital-Records-Data-Analysis-Report

## 1. Introduction

This project analyzes hospital patient records collected between 2021 and 2024. The dataset contains information about patients, their medical conditions, treatments received, admission and discharge date, DOB, gender, and hospital bill amounts.

This project analyzes hospital records from 2021 to 2024 to uncover patterns in patient demographics, medical conditions, hospital admissions, length of stay, and billing. 

The goal is to provide clear insights that can help hospital management understand trends, identify areas of concern,identify high-cost medical conditions and treatments, and improve healthcare resource planning, and make more informed decisions.


## 2. Data Description
The dataset used for this analysis is the Hospital Record Dataset, which contains summarized Hospital Record Analysis from the year 2021-2024 and was gotten from Kaggel link below
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
   - **No duplicates Found**
   
   - **Missing/Blank values**
   - Checked important columns such as Patient ID, Medical Condition, Admit Date, Discharge Date, and Bill Amount for missing values, No missing value found
   
   - **Incorrect data types**
   -  Converted admission, Date of birth, and discharge dates column into date formats, from MM/D/YY to D/MM/YY
   
   - **Age calculation**
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
  
   - ** 3 more columns where added in the dataset which are
   - Lenght of stay
   - Age at admisssion
   - Age group
  
  **Data Quality Issues**
  During data cleaning, some records were identified where the patient’s Date of Birth occurred after the Admission Date. Since these    records could result in incorrect age calculations, they were flagged as “Invalid DOB” and excluded from age-based analysis while being retained in the original dataset.

** Calculated Measures **
1. Total Patients =
DISTINCTCOUNT('Hospital'[Patient ID])
2. Average Bill per Patient =
DIVIDE(
    [Total Bill Amount],
    [Total Patients])
3. Total Admissions =
COUNTROWS('Hospita[admit date]l')
4. Total medical condition = DISTINCTCOUNT(Sheet1[Medical Condition])

** Visualization Techniques **

The following power Bi visuals were utilized

-KPI cards
-Clustered Bar Charts
-Clusterd Column Charts
-Donut Charts
-Line Chart
-Slicers

** Dashboard Development
The project consist of 3 Dashboard pages
** Overview **
** Patient & Medical **
** Bill Analysis **

# 4. Analysis & Findings

## 4.1 Patient Demographics

The dataset contains 1,000 patients.

### Gender Distribution

- **Female:** 511 patients (51.1%)
- **Male:** 489 patients (48.9%)

The gender distribution is relatively balanced, although female patients slightly outnumber male patients.

   
