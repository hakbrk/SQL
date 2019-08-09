# SQL
SQL - Homework assignment #9

File List
- Avg_Salary - Average Salary by title bar chart

- Create_Table_Code - Exported text file from quickdatabasediagrams.com, used to create table in Postgresql.

- ERD_Code - Text file that can be used to create the ERD using quickdatabasediagrams.com.
EDR_Diagram - Entity Relationship Diagram (ERD) showing the database structure of the Postgres                     database used for the homework assignemnt.
Query - Text file with Postgresql code used to query the database.
        SQL_Homework_JLH.ipynb - Jupyter Notebook file used to import Postgresql database into Pandas           and generate the Avg_Salary bar chart.

Following are notes intended to clarify the methodology used during the query and bonus exercises.
1.  List the following details of each employee: employee number, last name, first name, gender, and salary.
    - As the instructions requested this data was pulled from the employees table.  It should be noted that further inspection of the         data revealed that this tale includes both past and present employees, not just current employees.
  
2.  List employees who were hired in 1986.
    - Data was pulled from the employees table.  As in the above query, there was no filter applied to drop past employees so results         represent strictly any employee list in the employees table.
   
3.  List the manager of each department with the following information: department number, department name, the manager's employee           number, last name, first name, and start and end employment dates.
    - This query represents the current manager of each department.  Following the first query, it was noticed that the data represented        both past and present managers.  A filter was added by the use of a WHERE command that called for only rows containing the year          9999 in the to_date column within the dept_manager table to accomplish this.
    
4.  List the department of each employee with the following information: employee number, last name, first name, and department name.
    - This query represents department each current employee contained in the employees table currently holds.  The data contained in         the dept_emp table represents both current and historical data.  A filter was added by the use of a WHERE command that called for       only rows containing the year 9999 in the to_date column within the dept_emp table to accomplish this.
  
5.  List all employees whose first name is "Hercules" and last names begin with "B".
    - This query was generated by the use of a WHERE statement and wildcard to return the instances of the last name beginning with "B".
    
6.  List all employees in the Sales department, including their employee number, last name, first name, and department name.
    - This query returns all employees currently serving in the Sales department.  Again as in previous queries a WHERE statement             filtering out any past employees was utilized.
    
7.  List all employees in the Sales and Development departments, including their employee number, last name, first name, and department     name.
    - This query is essentially the same as #6 but included an additional group of employees currently working in Development.
    
8.  In descending order, list the frequency count of employee last names, i.e., how many employees share each last name.
    - This query returned the frequency of each last name contained in the employees table, it was then sorted greatest to least similar       last names.  The most similar name was found to be Baba, and the least similar is Foolsday (Sounds like a joke to me?).
    
Bonus Section

1.  Import the SQL database into Pandas.
    - The import was accomplished using Psycopg which was found using a google search.  All code can be found in Jupyter Notebook             SQL_Homework_JLH.
    
2.  Create a bar chart of average salary by title.
    - A bar chart was constructed using Seaborn.  The chart represents the average salary by tile for current employees.  It should be         noted that the average salaries when considering all employees in the employees table results in the same averages, so that tells       us that there has been no change in salary for any of the employees during the time frame of the dataset.  Bar chart can be found       as the png titled Avg_Salary
