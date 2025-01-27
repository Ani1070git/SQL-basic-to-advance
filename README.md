# SQL-basic-to-advance
This Repo contains SQL interview questions along with their answers. Each question is followed by a detailed explanation of the query.

### Table Used for Questions

This table will be referenced for solving SQL questions:

| EmployeeID | Name       | Department  | Salary | JoiningDate | ManagerID |
|------------|------------|-------------|--------|-------------|-----------|
| 1          | Alice      | HR          | 60000  | 2021-05-01  | 3         |
| 2          | Bob        | IT          | 75000  | 2020-08-15  | 3         |
| 3          | Charlie    | Management  | 120000 | 2018-12-01  | NULL      |
| 4          | David      | IT          | 70000  | 2022-01-20  | 2         |
| 5          | Eva        | HR          | 58000  | 2023-03-10  | 1         |

## Question 1: Fetch names of employees in the IT department
### Query:
```sql
SELECT Name 
FROM Employees 
WHERE Department = 'IT';
```
# Explaination :
SELECT Name: Fetches the Name column from the table.

FROM Employees: Indicates the table to query.

WHERE Department = 'IT': Filters the rows where the Department column equals 'IT'

# Question 2: Find the total salary of employees in the HR department
### Query:
```sql
SELECT SUM(Salary) AS TotalSalary
FROM Employees
WHERE Department = 'HR';
```
# Explaination :
SUM(Salary): Adds up the values in the Salary column.

AS TotalSalary: Renames the result as TotalSalary.

WHERE Department = 'HR': Filters only the rows where the Department is 'HR'.
