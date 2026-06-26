# Student-Lifestyle-Analysis
End-to-end Exploratory Data Analysis on a Student Lifestyle and Stress Prediction Dataset (25,500  students record
, 9 workload &amp; lifestyle features) to identify key risk factors using Python. Cleaned data was also loaded into a PostgreSQL database.


## Project Overview
This project explores a synthetic dataset of 25,500 student records to analyze the relationship between student lifestyle habits (sleep, study hours, social media usage, attendance) and their stress levels.

The data was extracted, comprehensively cleaned and transformed using Python (Pandas), and finally loaded into a local PostgreSQL database for further querying and storage.

## Tech Stack & Tools
- Language: Python
- Data Manipulation & Analysis: Pandas, NumPy
- Data Visualization: Matplotlib, Seaborn
- Database: PostgreSQL, SQLAlchemy, Psycopg2

## Environment: Jupyter Notebook
# Pipeline Phases
1. Data Understanding (Extract)
- Loaded the initial dataset (student-lifestyle.csv) containing 25,500 rows and 9 columns.
- Conducted initial statistical summaries and identified missing values, data anomalies (e.g., negative study hours
and class imbalances.

2. Data Cleaning & Feature Engineering (Transform)
- Anomaly Correction: Handled impossible negative values in the Study_Hours column by converting them to 0.
- Handling Nulls: Dropped rows with missing primary grouping keys (Student_Type).
- Applied Median Imputation for continuous numerical variables (Sleep_Hours, Study_Hours, Social_Media_Hours, Attendance) to avoid skewing from extreme values.
- Applied Mode Imputation for discrete/categorical-like numericals (Exam_Pressure, Family_Support, Month).
- Outlier Treatment: Detected and handled outliers using the Interquartile Range (IQR) method.
- Feature Engineering: Created categorical bins for easier analysis:
- Sleep_Category: Poor (<6 hrs), Adequate (6-8 hrs), Good (>8 hrs).
- Study_Category: Low (<3 hrs), Moderate (3-6 hrs), High (>6 hrs).

3. Exploratory Data Analysis (EDA)
- Utilized Seaborn and Matplotlib to visualize distributions, boxplots, and correlation heatmaps.
- Analyzed stress levels across different subgroups (School, College, Working Students) and lifestyle categories.
4. Database Integration (Load)
- Saved the transformed dataset as Cleaned_Student_Lifestyle.csv.
- Established a local connection to a PostgreSQL database (EDA projects) using psycopg2.
- Successfully automated the loading of the cleaned DataFrame directly into a PostgreSQL table using SQLAlchemy.

## Key Insights & Findings
- Exam Pressure is the Primary Stressor: The correlation heatmap revealed that Exam_Pressure has the highest positive correlation (0.52) with student stress levels. Furthermore, 90.78% of students reporting an exam pressure level of 10 were stressed.
- Working Students are the Most Stressed: Among the demographics, working students reported the highest stress rate (38.19%), compared to college (31.25%) and school students (20.48%).
- Sleep Matters: Stressed students generally sleep less. 37.32% of students in the "Poor" sleep category (<6 hours) reported being stressed, compared to only 21.57% in the "Good" sleep category.
- Study Hours: Stressed students tend to study more (average 5.38 hours) compared to non-stressed students (average 4.38 hours).
- Family Support Mitigates Stress: Students with higher average family support scores showed a lower likelihood of experiencing stress.
- Inconclusive Metrics: Based on the boxplot analysis, there was no distinct, measurable difference in Social_Media_Hours or Attendance between stressed and non-stressed students in this dataset.

## Files
Student_Lifestyle_Analysis.ipynb — Main EDA notebook
student-lifestyle.csv   — Raw dataset
Cleaned_Student_Lifestyle.csv   — Cleaned output

## 👤 Author
Bikash Sahani
github.com/bikashsahani | linkedin.com/in/bikash-sahani