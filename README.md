![image](https://github.com/user-attachments/assets/903f4646-9ddc-4187-bae3-e291fc3e47e4)

# Excel Dashboard Project
### This is my first project in which I utilized foundational Excel skills to perform basic data analysis.

The dataset provides comprehensive details on job titles, salaries, locations, and key skills. It is based on real data science job information from 2023.

![01](https://github.com/user-attachments/assets/2c0d0fbd-90d2-4f31-8e3d-ace40f85cc50)


## Excel skills used in this analysis include:

- Functions and formulas
- Charts
- Data Validation

## Dashboard Project provides information on:

- Job Titles
- Salaries
- Locations
- Skills

## Dashboard overwiev:

## Charts:

### Job Salaries - Bar Chart

![02](https://github.com/user-attachments/assets/0c8845e1-dc08-4051-b2c3-d13693d22f0a)

Excel's bar chart functionality was applied to present salary data, with values formatted for clarity and the overall layout carefully adjusted for readability.
A horizontal orientation was chosen for the chart to allow for easier visual comparison between median salaries across job titles.
To further enhance the structure, job titles were arranged in descending order based on salary, which improved the interpretability of the data.
This approach revealed clear patterns in compensation, highlighting that Senior-level positions and Engineering roles typically offer higher pay than Analyst roles.

### Median by Location - Map Chart 

![03](https://github.com/user-attachments/assets/e33ef0ba-9568-4645-b390-ffe96e9cf42f)

Excel’s map chart was used to visualize median salaries across different countries, offering a clear global overview.
A color-coded scheme was applied to distinguish salary levels between regions, making differences immediately visible.
Each country with available data was represented by its median salary, ensuring consistent and meaningful comparisons.
The visual format enhances clarity and allows for quick interpretation of geographic salary patterns.
This approach effectively highlights disparities in pay, drawing attention to both the highest and lowest earning regions worldwide.

### Job Schedule Type - Bar Chart

![04](https://github.com/user-attachments/assets/04b339a7-1bbb-461c-b6fe-035766f0ee05)

Aditionally Bar chart was added which presents median salary data based on Job Title. 
The following chart offers a clear view of how compensation levels differ depending on the employment type.

### Count of Job Positions - Pie Chart

![05](https://github.com/user-attachments/assets/27892aae-fa53-4d6b-bcd1-0c398f9b461a)

The pie chart offers a clear visual representation of job distribution across key roles within the dataset. 
By displaying both the count and percentage for each job title, it allows for quick comparison of their relative prevalence.

## Functions

### Median by Job Title

A multi-criteria filtering approach was implemented to refine the dataset by checking for specific job titles, countries, and employment types, while excluding entries with missing salary values.
An array formula using the MEDIAN() function, combined with a nested IF() statement, was employed to perform conditional analysis across the dataset.

`=MEDIAN(
IF(
    (jobs[job_title_short]=A2)*
    (jobs[job_country]=country)*
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
    (jobs[salary_year_avg]<>0),
    jobs[salary_year_avg]
)
)`

### Count of Job Schedule Type

A dynamic list of unique job schedule types is generated using the FILTER() function, which excludes entries containing "and", commas, or zero values.
This approach ensures clean and relevant data by removing ambiguous or compound entries from the results.
The resulting formula populates the table below with a refined list of distinct schedule types used in the dataset.

`=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))` 

## Data Validation

### Filtering List:

Data Validation: Implementing the filtered list as a data validation rule under the Job Title, Country, and Type option in the Data tab.

![06](https://github.com/user-attachments/assets/54fca02c-7468-4d17-94c9-ecced3116f46)






