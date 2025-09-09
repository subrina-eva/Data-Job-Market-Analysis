# Project 2 Analysis  

## Introduction  

This project was created to analyze the data science job market with a focus on salaries, skills, and regional demand. By combining Excel’s advanced 
analytics tools with real-world data, the goal was to uncover insights that can guide job seekers and professionals toward better career decisions.  

### Questions to Analyze  

To understand the data science job market, I asked the following:  

 1. **Do more skills get you better pay?**
 2. **What’s the salary for data jobs in different regions?**
 3. **What are the top skills of data professionals?**
 4. **What’s the pay for the top 10 skills?**  

### Excel Skills Applied  

The following Excel skills were utilized for analysis:  

- 📊 **Pivot Tables**  
- 📈 **Pivot Charts**  
- 🧮 **DAX**
- 🔍 **Power Query**   
- 💪 **Power Pivot**  

### Data Jobs Datasets  

This project uses a dataset containing 2023 data science job market information, sourced from Luke Barousse’s Excel course. The dataset provides insights into:  

- 👩‍💼 **Job titles**  
- 💰 **Salaries** 
- 📍 **Locations**  
- 🛠 **Skills**   

## 1️⃣ Do more skills get you better pay?  

### 🔍 Skill: Power Query (ETL)    

#### 📥 Extract  

- Using Power Query, I pulled data from (`data_salary_all.xlsx`) and created two queries:  
  - 🗃 A dataset containing all job-related information.  
  - 🔧 A dataset listing the skills associated with each job ID.  
 
#### 🔄 Transform  

- I refined both queries by adjusting column types, removing unnecessary fields, cleaning text (removing specific words), and trimming excess spaces.  
   - 📊 data_jobs_salary  

       <img width="289" height="296" alt="2_Project_Analysis_Screenshot1" src="https://github.com/user-attachments/assets/2464ca54-9fc9-42c3-9e47-5114654e0f12" />   


   - 🛠 data_job_skills

       <img width="316" height="425" alt="2_Project_Analysis_Screenshot2" src="https://github.com/user-attachments/assets/2e89d34f-199f-47a2-ad92-ec7350583869" />  


#### 🔗 Load  

- The cleaned and structured queries were then loaded back into the workbook, providing a solid foundation for further analysis.
  - 📊 data_jobs_salary

    <img width="1919" height="962" alt="2_Project_Analysis_Screenshot3" src="https://github.com/user-attachments/assets/9f9657d3-89fa-4782-ad47-2550f23e6248" />  


  - 🛠 data_job_skills
 
    <img width="1918" height="982" alt="2_Project_Analysis_Screenshot4" src="https://github.com/user-attachments/assets/dcc17a9d-312b-43c5-bcfc-7501441cd03f" />  

### 📊 Analysis

#### 💡 Insights

- 📈 There is a positive correlation between the number of skills requested in job postings and the median salary, particularly in roles like
  Senior Data Engineer and Data Scientist.
- 💼 Roles that require fewer skills, like Business Analyst, tend to offer lower salaries, suggesting that more specialized skill sets command higher market value.

  <img width="2126" height="1134" alt="2_Project_Analysis_Chart1" src="https://github.com/user-attachments/assets/b1eb9f7f-cdf6-458e-bc1e-8a175c3117bf" />  

#### 🤔 So What

- This trend emphasizes the value of acquiring multiple relevant skills, particularly for individuals aiming for higher-paying roles.

## 2️⃣ What’s the Salary for Data Jobs in Different Regions?  

### 🧮 Skills: PivotTables & DAX  

#### 📈 Pivot Table  

- 🔢 Built a PivotTable using the Data Model in Power Pivot.  
- 📊 Placed job_title_short in the rows area and salary_year_avg in the values area.  
- 🧮 Added a custom measure to calculate the median salary for U.S. jobs:

```
=CALCULATE(
      [Median Salary], data_jobs_salary[job_country]="United States")
```    

#### 🧮 DAX  
- Created a measure to calculate the overall median salary across all regions:  

```
    Median Salary := MEDIAN(data_jobs_salary[salary_year_avg])  
```  

### 📊 Analysis  

#### 💡 Insights  

- 💼 Senior Data Engineers and Data Scientists earn higher median salaries worldwide, with the U.S. leading. A significant pay gap remains
between U.S. and non-U.S. roles, especially in high-tech jobs.  

  <img width="963" height="342" alt="2_Project_Analysis_Chart3" src="https://github.com/user-attachments/assets/dc69f4d3-26a1-447d-bde5-ab074e2853f6" />  

#### 🤔 So What  

- These salary insights are important for planning and salary negotiations, helping professionals and
  companies align their offers with market standards while considering geographical variations.  

## 3️⃣ What Are the Top Skills of Data Professionals?  

### 🔧 Skill: Power Pivot  

#### 💪 Power Pivot  

- 🔗 Built a data model by integrating (`data_jobs_salary`) and (`data_jobs_skills`).  
- 🧹 With the data already cleaned in Power Query, Power Pivot automatically established relationships between the two tables.

#### 🔗 Data Model  

- Connected the tables using the job_id column as the key.

<img width="745" height="661" alt="2_Project_Analysis_Screenshot5" src="https://github.com/user-attachments/assets/545ff974-162c-4ca2-81c6-9614b3d2504e" />  


#### 📃 Power Pivot Menu  

- Used the Power Pivot menu to refine the data model and simplify the creation of measures.

<img width="1919" height="814" alt="2_Project_Analysis_Screenshot6" src="https://github.com/user-attachments/assets/de99fa82-d89d-4171-b782-166f08cb23d3" />   

### 📊 Analysis    

#### 💡 Insights   

- 💻 SQL and Python remain the most critical skills for data professionals, while AWS and Azure highlight the growing importance of cloud technologies. 
Staying current with these tools is key to career growth and industry relevance.  

<img width="1493" height="971" alt="2_Project_Analysis_Chart2" src="https://github.com/user-attachments/assets/014081ca-6988-4eda-aa79-e7e6599a59b0" />  

#### 🤔 So What

- Understanding prevalent skills in the industry not only helps professionals stay competitive but also guides
  training and educational programs to focus on the most impactful technologies.  

## 4️⃣ What’s the Pay for the Top 10 Skills?  

### 📊 Skill: Advanced Charts (PivotChart) 

#### 📈 PivotChart  

- Designed a combo PivotChart to visualize both median salary and skill likelihood (%) from the PivotTable.  
  - 🪙 Primary Axis: Median Salary (Clustered Column).  
  - 👍 Secondary Axis: Skill Likelihood (Line with Diamond Markers).  
- Customized the chart by adding titles, refining axis labels, and enhancing readability through cleaner formatting.  
 
### 📊 Analysis    

#### 💡 Insights   

- 💰 Python, SQL, and Oracle drive the highest salaries, while general tools like PowerPoint and Word offer little value in high-paying roles. 
To maximize earning potential, professionals should focus on building strong technical skills.  

<img width="2065" height="1085" alt="2_Project_Analysis_Chart4" src="https://github.com/user-attachments/assets/96fc143b-390c-4aa2-a546-2d6b34a38e09" />  

### 🤔 So What

- This chart highlights the importance of investing time in learning high-value skills like Python and SQL, which are evidently tied to
  higher paying roles, especially for those looking to maximize their salary in the tech industry.  

## Conclusion

In this project, I explored real-world data science job postings to see what drives higher salaries. The analysis shows that having multiple skills 
especially Python, SQL, and cloud platforms can significantly boost your earning potential. Salaries also vary greatly by region, with the U.S. offering the highest pay, 
especially for technical roles. To remain competitive, professionals should focus on building strong technical foundations early and expand into advanced tools 
as they grow.  

These findings can help data professionals focus on the skills that matter most for advancing their careers.  