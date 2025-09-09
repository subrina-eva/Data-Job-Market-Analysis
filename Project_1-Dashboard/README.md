# Excel Salary Dashboard  

**Explore salaries, uncover trends, and take control of your career path.**

![1_Salay_Dashboard_Final_Dashboard](https://github.com/user-attachments/assets/9311fcb0-b44c-4df0-a4ad-7c694446c380)  

## Introduction  

This data job salary dashboard is designed to help job seekers explore salary trends across job roles and industries, ensuring fair and competitive compensation.  

The dataset, sourced from a Excel Data Analytics Course by Luke Barousse on YouTube, contains detailed information on job titles, salaries, locations, and essential skills that are presented here.  

### Dashboard file  
My final dashboard is in [1_Salary_Dashboard.xlsx](1_Salary_Dashboard.xlsx).  

### Excel Skills Applied  
The following Excel skills were utilized for analysis:  

- 📈 **Charts**
- 🧮 **Formulas and Functions**
- 📑 **Data Validation**

### Data Jobs Datasets  
This project uses a dataset containing 2023 data science job market information, sourced from Luke Barousse’s Excel course. The dataset provides insights into:  
- 👩‍💼 **Job titles**  
- 💰 **Salaries** 
- 📍 **Locations**  
- 🛠 **Skills**   

## Dashboard Overview  

### 📈 Charts  

#### 📊 Data Science Job Salaries – Bar Chart  

<img width="1475" height="887" alt="1_Salay_Dashboard_Chart1" src="https://github.com/user-attachments/assets/f702e290-33db-4113-a7fe-97f28664730f" />  

- 🛠 **Tools Used:** Excel bar chart with formatted salary values for clarity.  
- 🎨 **Design Approach:** Horizontal bars to easily compare salaries across job roles.  
- 📊 **Data Handling:** Jobs sorted by descending median salary for readability.  
- 💡 **Main Findings:** Senior and engineering roles tend to earn more than analyst positions.

#### 🌍 Country Median Salaries – Map Chart  

![1_Salay_Dashboard_Country_Map](https://github.com/user-attachments/assets/33bd2b2f-552e-4b99-9e16-ef2587e4eb92)  

- 🛠 **Tools Used:** Excel map chart to visualize median salaries worldwide.  
- 🎨 **Design Approach:** Color-coded regions for quick understanding of salary ranges.  
- 📊 **Data Handling:** Median salaries mapped for each country with available data.  
- 👁 **Visual Enhancement:** Instantly shows geographic salary trends.  
- 💡 **Main Findings:** Easily spot high-paying regions and understand global salary differences.

### 🧮 Formulas and Functions
   
#### 💰 Median Salary by Job Titles   

```
=MEDIAN(    
IF(  
    (jobs[job_title_short]=A2)*  
    (jobs[salary_year_avg]<>0)*  
    (jobs[job_country]=country)*  
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type]))),  
    jobs[salary_year_avg]  
)  
)  
```
- 🔍 **Purpose:** Calculates the median salary for a specific job title, country, and job schedule type.
- 📊 **Functionality:** Combines `MEDIAN()` with a conditional `IF()` for multi-criteria filtering.
- 🎯 **Benefit:** Provides precise, role-specific salary insights.
- 🔢 **Formula Purpose:** This formula populates the table below, returning the median salary based on job title, country, and type specified.

🍽 Background Table

<img width="354" height="276" alt="1_Salay_Dashboard_Screenshot1" src="https://github.com/user-attachments/assets/f03a417e-a318-440c-bae4-cad9c91fe05b" />  

📈 Dashboard Implementation    

<img width="486" height="484" alt="1_Salay_Dashboard_Job_Title" src="https://github.com/user-attachments/assets/e2de1e6f-f41c-4bc0-977e-0a1b58e65a66" />  

#### ⏰ Unique Job Schedule Types  

```
=FILTER(J2#,NOT(ISNUMBER(SEARCH("and",J2#)))*(J2#<>0))
```

- 🔍 **Purpose:** Generates a filtered list of job schedule types, excluding zero values and entries containing "and" or commas.  
- 🎯 **Benefit:** Ensures only clean, unique schedule types are used for analysis and validation.
- 🔢 **Formula Purpose:** This formula populates the table below, which gives us a list of unique job schedule type.  

🍽 Background Table  

<img width="197" height="133" alt="1_Salay_Dashboard_Screenshot2" src="https://github.com/user-attachments/assets/37aab1e4-2d3f-4ad8-abbc-02706460aac2" />    

📈 Dashboard Implementation  

<img width="391" height="485" alt="1_Salay_Dashboard_Job_Type" src="https://github.com/user-attachments/assets/171082e1-a50a-4346-ac39-260340e24cca" />   

### 📑 Data Validation  

#### 🔍 Filtered List  
 
- 🔒 **Why It Matters:** The Salary Dashboard incorporates enhanced data validation using a filtered list for `Job Title`, `Country`, and `Type` under the Data tab.  
   - 🎯 Controlled Inputs: Users can only select from predefined schedule types.  
   - 🚫 Error Prevention: Prevents incorrect or inconsistent entries.  
   - 👥 Improved Usability: Simplifies navigation and ensures cleaner data for analysis.  

![1_Salay_Dashboard_Data_Validation](https://github.com/user-attachments/assets/61d5e536-9839-4860-9de0-b302a17a48a7)  

## Conclusion  

I built this dashboard to explore and reveal salary patterns across data-focused roles, revealing how location and job type influence pay. It provides practical insights for career planning and demonstrates the power of Excel in turning raw data into actionable information.
