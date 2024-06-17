# HR-Analytics-Dashboard

## Problem Statement

This dashboard helps the HR department understand employee attrition better. It provides detailed information on various aspects of attrition, including overall attrition rate, attrition by age, education, and job role, as well as customer satisfaction data and distribution of employees by age. Through these insights, HR can identify key factors contributing to employee turnover.

The dashboard reveals that the current attrition rate is 16.1%. By analyzing this data, HR can pinpoint areas needing improvement to enhance employee satisfaction and retention. 

This targeted approach enables the HR department to implement effective strategies to reduce attrition and improve the overall work environment.


### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a csv file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : It was observed that in none of the columns errors & empty values were present except column named "YearsWithCurrentManager".
- Step 5 : For calculating attrition , this column wa not taken into account (i.e column named "YearsWithCurrentManager")
- Step 6 : New Column AttritionCount was added to convert bool attrition data to numeric.
- Step 7 : In the report view, under the visualization, background image was added.
- Step 8 : Visual filters (Slicers) were added for three fields of department column named "Human Resourses", "Research & Dev" & "Sales" 
- Step 9 : Six card visuals were added to the canvas, representing count of Employee, Attrition Count, Attrition rate, Average Age, Average Salary &  Average Years in company.
- Step 10 : A treemap was added to show the gender distribution.
- Step 11 : A donut chart was added to the report design area representing the attrition count based on education field.
- Step 12 : A column chart was added to the report design area representing the attrition by age.
- Step 13 : A Matrix was added to the report design area representing the employee satisfaction score by job role.
- Step 14 : A bar chart was added to the report design area representing the attrition by employee salary based on Age group.
- Step 15 : A area chart was added to the report design Area representing attrition by year.
- Step 16 : A bar chart was added to the report design Area representing attrition by job role.
- Step 17 : In the report view, under the insert tab, text boxe was added to the canvas, representing name of the dashboard. 
- Step 18 : Calculated column was created in which, customers were grouped into various age groups.

for creating new column following DAX expression was written;
       
    AgeGroup = SWITCH(
      TRUE(),
      'HR_Analytics[Age] >=18 && HR_Analytics[Age]<=25,"18-25",
      'HR_Analytics[Age] >=26 && HR_Analytics[Age]<=35,"26-35",
      'HR_Analytics[Age] >=36 && HR_Analytics[Age]<=45,"36-45",
      'HR_Analytics[Age] >=46 && HR_Analytics[Age]<=55,"46-55",
      "55+")
        
Snap of new calculated column ,

![Snap_1](https://github.com/amankumar0245/HR-Analytics-Dashboard/blob/ed3fb6cf380c01b3252212bb16aaa77b9758e62c/Assets/Screenshot%202024-06-17%20193148.png)

        
- Step 19 : New measure was created to find total employee turnover rate/Attrition rate.

Following DAX expression was written for the same,
        
        AttritionRate = SUM(HR_Analytics[AttritionCount])/SUM(HR_Analytics[EmployeeCount])
- Step 20 : Card visual to represent count of Employee, Attrition, Attrition Rate, Avg Age ,Avg Salary, Avg Years

   ![Snap_Percentage](https://github.com/amankumar0245/HR-Analytics-Dashboard/blob/ed3fb6cf380c01b3252212bb16aaa77b9758e62c/Assets/Screenshot%202024-06-17%20193113.png)
        
- Step 21 : Filter to filter attrition by department,
 
 A card visual was used to represent this filter.
 
 ![Snap_Percentage](https://github.com/amankumar0245/HR-Analytics-Dashboard/blob/ed3fb6cf380c01b3252212bb16aaa77b9758e62c/Assets/Screenshot%202024-06-17%20193125.png)

 - Step 22 : Tree Chart too represent Attriton By gender,
 
 ![Snap_Percentage](https://github.com/amankumar0245/HR-Analytics-Dashboard/blob/ed3fb6cf380c01b3252212bb16aaa77b9758e62c/Assets/Screenshot%202024-06-17%20192708.png)

 - Step 23 : Donut Chart to represent Attrition By Education,
 
 ![Snap_Percentage](https://github.com/amankumar0245/HR-Analytics-Dashboard/blob/ed3fb6cf380c01b3252212bb16aaa77b9758e62c/Assets/Screenshot%202024-06-17%20192506.png)
 
  - Step 24 : Column Chart to represent Attrition By Age,
 
 ![Snap_Percentage](https://github.com/amankumar0245/HR-Analytics-Dashboard/blob/ed3fb6cf380c01b3252212bb16aaa77b9758e62c/Assets/Screenshot%202024-06-17%20192519.png)

   - Step 25 : Table to represent Attrition By job Satisfaction Score,
 
 ![Snap_Percentage](https://github.com/amankumar0245/HR-Analytics-Dashboard/blob/ed3fb6cf380c01b3252212bb16aaa77b9758e62c/Assets/Screenshot%202024-06-17%20192529.png)

   - Step 26 : bar Chart to represent Attrition By Salary,
 
 ![Snap_Percentage](https://github.com/amankumar0245/HR-Analytics-Dashboard/blob/ed3fb6cf380c01b3252212bb16aaa77b9758e62c/Assets/Screenshot%202024-06-17%20192549.png)

   - Step 27 : Area line Chart to represent Attrition By Years of Service,
 
 ![Snap_Percentage](https://github.com/amankumar0245/HR-Analytics-Dashboard/blob/ed3fb6cf380c01b3252212bb16aaa77b9758e62c/Assets/Screenshot%202024-06-17%20192538.png)

  - Step 28 :Bar Chart to represent Attrition By Job Role,
 
 ![Snap_Percentage](https://github.com/amankumar0245/HR-Analytics-Dashboard/blob/ed3fb6cf380c01b3252212bb16aaa77b9758e62c/Assets/Screenshot%202024-06-17%20192638.png)

 
# Snapshot of Dashboard (Power BI Service)

![dashboard_snapo](https://github.com/amankumar0245/HR-Analytics-Dashboard/blob/ed3fb6cf380c01b3252212bb16aaa77b9758e62c/Assets/Screenshot%202024-06-15%20202934.png)

 

# Insights

A single page report was created on Power BI Desktop.

Following inferences can be drawn from the dashboard;

### [1] Total Number of Employees = 1470

### [2] Employee Turnover/Attrition = 237

   Number of turnover employees (Male) = 150 (63.29 %)

   Number of satisfied Customers (Female) = 87 (36.71 %)
   
### [3] Average Employee Years at Company = 7

### [4] Employee Turnover rate = 16.1%

### [5] Average Age of Employee = 37
           
### [6] Average Salary of Employees = 6.5k

### [7] Average Salary of Employees = 6.5k
           
### [8] Attrition By Education
    a) life Sciences - 38%
    b) Medical - 27%
    c) Marketing - 15%
    d) Technical Degree - 14%

      thus, the employee with education background in life sciences has highest attrition rate.
  
  These ratings will change if different visual filters will be applied.  

  ### [9] Attrition By Age
    a) 18-25 - 44
    b) 26-35 - 116
    c) 36-45 - 43
    d) 46-55 - 26
    e) 55+   - 8

      thus, the employees in the age group of 26-35 has the highest attrition.
  
 These ratings will change if different visual filters will be applied.
 
### [10] Employee Job satisfaction score Vs Attrition

    Healthcare Representative = 20 
   
    thus, highest employee turnover are the laboratory technician which is 62 out of which 20 employees has given 1 score which
    means they were not satified with their job.

 
 ### Age Group
 
    2.1)  21.69 % customers belong to '0-25' age group.
 
    2.2)  52.44 % customers belong to '25-50' age group.
 
    2.3)  25.57 % customers belong to '50-75' age group.
 
    2.4)  0.31 % customers belong to '75-100' age group.
 
         thus, maximum customers belong to '25-50' age group.
         
### Attrition By Salary

    3.1) upto 5k - 163.

    3.2) 5k-10k  - 49.

    3.3) 10k-15k  - 20.

    3.4) 15k+     - 5
       
       thus, the employee whi has salary less than or equal to 5k has highest turnover.

### Attrition By Year

       less than 1 - 16/237
       1 year      - 59/237
       4- year     - 19/237
       5 - year    - 21
       
       thus, the employees tend to leave after 1 year of their service.
