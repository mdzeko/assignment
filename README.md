
# 1. Practical coding
In a text editor of your choice write pseudo code to solve the following problem: Write a function that removes non ASCII characters from a String


    purge_string(input):
	    string output = ""
	    foreach(char c in input):
		    if (int)c < 128:
			    output += c
	    return output

# 2. SQL query

The **EMPLOYEE** table has the following attributes: *NAME*, *DEPT_ID*, and *SALARY*. The **DEPARTMENT** table has the following attributes: *ID* and *NAME*.  
Write a query that shows the department names along with the highest salary in each department
	    

Departments:

![image](https://user-images.githubusercontent.com/1204176/193678763-fa3996b5-7b31-4ea2-9528-4092b96a3292.png)

Employees:

![image](https://user-images.githubusercontent.com/1204176/193684544-9f67604a-9948-47d9-abef-62100ffb5ca9.png)

Highest salary by department:

    select max(e.salary) as 'highest_salary', d.name from DEPARTMENT d
    JOIN EMPLOYEE e on e.dept_id = d.id
    GROUP by d.name;

![image](https://user-images.githubusercontent.com/1204176/193684794-636953d3-125a-4a37-b349-b15a1d81ee04.png)

    
# 3. SQL modification

Modify query from the previous task (2. SQL query), so the results are only departments with the highest salary above 3000.

    SELECT max(e.salary) AS 'highest_salary', d.name FROM DEPARTMENT d
    JOIN EMPLOYEE e on e.dept_id = d.id
    GROUP by d.name
    HAVING max(e.salary) > 3000
Result is an empty table since the highest salary of 3000 is in "Sales" and  is not higher than 3000.

# 4. SQL modification

Modify the query from the second task (2. SQL query) to ensure all departments are displayed in the results, even if there is no employee for the department.

    SELECT max(e.salary) AS 'highest_salary', d.name FROM DEPARTMENT d
    LEFT JOIN EMPLOYEE e on e.dept_id = d.id
    GROUP by d.name

![image](https://user-images.githubusercontent.com/1204176/193685587-a5a1a8bb-60dd-4adc-9dfe-a5f62f7d549a.png)
