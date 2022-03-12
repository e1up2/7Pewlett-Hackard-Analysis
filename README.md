# Pewlett-Hackard-Analysis
## Overview
The Pewlett-Hackard-Analysis is about creating database designs or Entity Relationship Diagrams, designing and managing tables, and writing SQL queries to explore and manipulate data in database tables. SQL queries will ask questions from our data and discover the relationships between different data tables using relational databases. In the PH Analysis, we would design a database to address two issues the company faces as its baby boomer generation begins to retire. 1) The company is offering retirement packages for those who meet specific criteria, and 2) the company wants to know which positions will be affected when many employees retire at the same time. 

To determine which employees are retiring and those that are eligible for mentorship, our analysis will reframe the ask into two questions:
1. Who will be retiring in the next few years
2. How many positions will Pewlett-Hackard need to fill

This analysis will help future-proof the company by generating a list of all employees eligible for the retirement package.

In the first part of our analysis, we will create a database design or Entity Relationship Diagram from the CSV files the company has been using to manage its employee data for many years. We would apply data modeling, engineering, and analysis skills to get the PH database running.

In the second part of our analysis, we will use SQL queries to determine the number of retiring employees per title and identify eligible employees to participate in a mentorship program. In the end, we will prepare a report to help the company prepare for the upcoming large-scale retirement.

### Phase 1:
1. Identify and define the common columns in the employee CSVs.
2. Determine entity relationships by identifying primary keys and foreign keys
3. Create an Entity Relationship Diagram by defining table name, columns, data types and specify primary keys and foreign keys
4. Create the employee database
5. Create the database schmema - this will contain all the tables indentified in the ERD
6. Import the csv files into the appropriate tables
7. Write SQL query to determine retirement eligibility
      * Create new table to hold the employee retirement info
      * Write SQL query to determine current employees by joining the retirement info table with the dept emp table; filter by the to_date column to give the list of employees that are with the company
      * By joinning the current emplyee table with the dep employee table write a query to determine the count of employees retiring by department.
      * Write SQL to determine employee info by joining columns from the employees, salaries, and department tables
      * Write SQL to determine manager info by joining columns from the current employees, departments, and department manager tables
      * Write SQL to determine department retirees by adding department to the current employee table.

#### Entity Relationship Diagram
![PH_ERD](erd.png)


### Phase 2: 
1. The Number of Retiring Employees by Title
      * Write a query to determine retirement titles
      * Using the DISTICT ON statement, retrieve the first occurrence of the employee number for each set of rows defined by the ON () clause.
      * Select the query result into a new unique_titles table.
      * Write another query to retrieve the number of employees by their most recent job title who are about to retire.

2. The Employees Eligible for the Mentorship Program
      * Retrieve the emp_no, first_name, last_name, and birth_date columns from the Employees table
      * Retrieve the from_date and to_date columns from the Department Employee table.
      * Retrieve the title column from the Titles table.
      * Use a DISTINCT ON statement to retrieve the first occurrence of the employee number for each set of rows defined by the ON () clause.
      * Select the query result into a new mentorship_eligibilty table. 
      * Join the Employees and the Department Employee tables on the primary key and the Employees and the Titles tables on the primary key.
      * Filter the data on the to_date column to all the current employees, then filter the data on the birth_date columns to get all the employees whose birth dates are between January 1, 1965 and December 31, 1965.
      * Order the table by the employee number.

### Results
* With 29,414, employees with Senior Engineer title are most eligible for retirement.
* There are only 2 employees with Manager as their title that are eligible for retirement.
* There are 1549 employees eligible for the mentorship program.
* Using the COUNT function we determine that the Senior Staff and Engineer titles have the highest count of 569 and 501 eligible employees for the mentorship program
* Using the COUNT function we determine that the Production and Development departments with 322 and 396 have the highest count of employees eligible for the mentorship program

Number of Employees Retiring By Title

![Retiring_Titles_Count_](retiring_titles_count.png)


The Employees Eligible for the Mentorship Program

![Mentorship_Eligibility_](mentorship_eligibility.png)


Mentorship Eligibility Title Count

![Mentorship_Eligibility_Title_Count](eligibility_title_count.png)


Mentorship Eligibility Department Count

![Mentorship_Eligibility_Dept_Count_](eligibility_dept_count.png)



### Summary
From our retiring titles table there are 90,398 roles that will be needed to filled when the silver tsunami begins. Our mentorship eligibility table reveals that PH has only 1,549 eligible employees that may move up to fill higher roles. This means that PH has a short fall of 88,849 eligible employeees.

To address this shortfall, PH needs to identify the departments and titles that have the highest share of the 88,849 and focus their efforts on these departments and titles.
From the retiring titles table, we determine that the Senior Staff and Engineer titles with 29,414 and 28,254 counts are the most of all eligible titles.
We can decompose the 90398 count by department. This will illuminate the departments that has the biggest need. 

The Development department with 23,927 has the biggest shortfall of eligible employees for the mentorship program

Retiring Departments

![Retiring_Depts](retiring_depts.png)

Retiring Departments Count

![Retiring_Depts_Count](retiring_depts_counts.png)

Shortfall By Title

![Shortfall_By_Titles](shortfall_by_titles.png)

Shortfall By Departments

![Shortfall_By_Depts](shortfall_by_depts.png)
