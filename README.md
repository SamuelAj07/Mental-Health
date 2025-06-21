# Mental-Health Overview
---

# Table of Content

[Project Overview](#project-overview)

[Data Sources](#data-sources)

[Tools Used](#tools-used)

[Data PreProcessing](#data-preprocessing)

[Data Overview](#data-overview) 

[Tabular Overview](#tabular-overview) 

[Exploratory Data Analysis](#exploratory-data-analysis)

[Analysis Visualisation](#analysis-visualisation)

[Key Insights](#key-insights)

[Recommendations](#recommendations)

[Limitations](#limitations)

---

## Project Overview

This case study analyzed student mental health data to evaluate how factors like gender, age, academic performance, course of study, and marital status influence mental well-being This analysis diagnose the rate of wellness among university students of the India region


## Data Sources

The primary dataset used for this analysis was sourced from “Kaggle.com” – containing self-reported mental health data of students in India. 

## Tools Used

1. Excel

- [Data overview here](https://ibb.co/XfMY9xKt)

- [Cross-taulation](https://ibb.co/S4YQMZzH)

2. PowerBI

3. SQL

## Data PreProcessing

In the initial data cleaning phase, the following tasks were performed:
-	Handled missing values

-	Standardized text case

-	Converted CGPA range to average values

-	Re-coded binary responses to more improved clarity and align with context-specific analysis

-	DAX computation  

## Data Overview 

The dataset includes the following columns:

- Timestamp: Date and Time responses submitted
- Gender: Sex of students
-  Age: How old students are
-   Course: What student are studying in University
-   Current year of study: Study year students are as at response time.
-   CGPA: Cumulative Grade Point Average of the student
-  Marital status: Married or Single
-   Depression?: Indicates whether students reports experiencing symptoms of depression
-   Anxiety?: Indicates whether students reports experiencing symptoms of anxiety
-	Panic Attack?: Denotes if students reports experienced panic attacks
-    Treatment Seekers: Identifies whether students has sought professional help or treatment for their mental wellness. 


## Tabular Overview 

A brief overview of the tabular datasets. The first 5 Colums are displayed below. 

Timestamp|	Choose your gender|	Age|	What is your course?|	Your current year of Study|	What is your CGPA?|	Marital status|	Do you have Depression?|	Do you have Anxiety?|	Do you have Panic attack?|	Did you seek any specialist for a treatment?|
|-----|----|-----|-----|-----|----|-----|-----|-----|----|-----|
8/7/2020 12:02|	Female|	18|	Engineering|	Year 1|	3.00 - 3.49|	No|	Yes|	No|	Yes|	No|
8/7/2020 12:04|	Male|	21|	Islamic education|	Year 2|	3.00 - 3.49|	No|	No|	Yes|	No|	No|
8/7/2020 12:04|	Male|	21|	Islamic education|	Year 2|	3.00 - 3.49|	No|	No|	Yes|	No|	No|
8/7/2020 12:06|	Female|	22|	Law|	Year 3|	3.00 - 3.49|	Yes|	Yes|	No|	No|	No|
8/7/2020 12:13|	Male|	23|	Mathemathics|	Year 4|	3.00 - 3.49|	No|	No|	No|	No|	No|


## Exploratory Data Analysis

EDA aimed on what insights is to be processed, asking the following;

i. How does demographic information (age, gender, marital status) relate to mental health?

ii. What is the prevalence of mental health issues (depression, anxiety, panic attacks) among students?

iii. Are there correlations between academic factors (CGPA, Course, Year of study) and mental health?

iv. What proportion of students experiencing mental health issues have sought help?


## Analysis Visualisation

CHART ANALYSIS

![Screenshot (152)](https://github.com/user-attachments/assets/07206521-b680-457b-9b06-c87be09f05fa)

![Screenshot (154)](https://github.com/user-attachments/assets/be0d9cb7-230e-4ff9-83f7-7d6aede47129)

![Screenshot (155)](https://github.com/user-attachments/assets/9ebf7b9a-0d2b-4d1c-9273-656dd79fca28)

### Queries

```Sql
---Student with thw Minimum Cgpa--
SELECT * FROM [dbo].[Student_Mental_Health]
WHERE CGPA_Midpoint = (SELECT MIN(CGPA_Midpoint) from [dbo].[Student_Mental_Health]);
```

```Sql
---Student with thw Maximum Cgpa--
SELECT * FROM [dbo].[Student_Mental_Health]
WHERE CGPA_Midpoint = (SELECT MAX(CGPA_Midpoint) from [dbo].[Student_Mental_Health]); 
```
## Key Insights

1.	Depression is highest at ages 18(11 cases) with a gradual decline across till ages 21(0 case) before a gradual increase back to age 24.
   
2.	 Most Depression cases occur in Year 1 (14 cases), Year 2 and Year 3 (10 cases) with just 1 student with depression in Year 4
   
3.	 Ages 18 and 24 have the most cases of depression with special treatment, with middle ages 19-23 showing lower or no rate of seeking treatment.
   
4.	 Anxiety peaks at ages 18(14 cases) and 24(8 cases) showing higher stress in early and final academic years.
   
5.	 A downward trend in panic attack across ages 18 - 20, with ages 21and 22 having 0 cases with an upward trend back to ages 24
    
6.	 All married students were depressed (16 cases)
    
7.	 Students with depression have a slightly higher average CGPA (3.40) than those without (3.30)
    
8.	 Engineering students with CGPA average of 3. 3 report the highest Depression count (20 cases) followed by Biochemistry (3.6 CGPA average, 18 cases) and then Bachelor of Information Technology (3.1 CGPA average, 10 cases). Other courses had Depression cases range between 1 to 4
    
9.	 Students with Depression are more likely to have panic attacks than those with anxiety

10.	 Students in Year 4 have the highest average CGPA (3.56), while Year 3 students show the lowest (3.27)
    
11.	Females represent 82.8% of depression cases (29 out of 75) and 17.14% depression cases for males (6 out of 26). 
 


## Recommendations

1. Launch mental health educational programs especially for freshmen
   
2. Equip students with valuable skill
   
3. Increase awareness and free accessibility of Special treatment options for students who show signs of Depression
   
4. Promote social support networks such as extracurricular activities
   
5. Establish a Mental Health Design interventions to monitor trends in real time
    
6. Deploy gender-sensitive counseling, and safe space initiatives to address emotional stress, societal expectations, and peer dynamics.
    
7. Mental health support should be targeted at high achieving performance equally as low performance achievers
    
8. Intentionality of lecturers to simplify teaching systems.


## Limitations

i. Limited sample size

ii. Gender imbalance

iii. Limited scope of variables

iv. Ambiguous CGPA Values

v. Lack of time series data

