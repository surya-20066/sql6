📁 SQL Subquery Practice Repository
This repository contains SQL queries that demonstrate the use of:

✅ Scalar Subqueries
✅ Correlated Subqueries
✅ Subqueries inside IN, EXISTS, and = operators

The queries are designed using two simple tables: e1 and e2, with sample employee data.

📦 Table Structure
Table: e1
Column	Data Type	Description
id	INT(5)	Employee ID
name	VARCHAR2(10)	Employee Name
salary	INT(20)	Employee Salary

Table: e2
Column	Data Type	Description
id	INT(5)	Employee ID
name	VARCHAR2(10)	Employee Name
salary	INT(20)	Employee Salary

💾 Sample Data
Table: e1
id	name	salary
1	bk	20000
2	lk	30000
3	jk	40000
4	pk	50000

Table: e2
id	name	salary
1	surya	10000
5	yash	20000
6	jani	60000
7	sohan	70000

🛠️ Key SQL Queries
✅ 1. Subquery with IN
Selects employees from e1 whose id exists in e2.

sql
Copy
Edit
SELECT e1.name, e1.salary
FROM e1
WHERE e1.id IN (SELECT id FROM e2);
✅ 2. Scalar Subquery with =
Compares e1.id with the minimum id from e2.

sql
Copy
Edit
SELECT *
FROM e1
WHERE e1.id = (SELECT MIN(id) FROM e2);

✅ 3. Correlated Subquery with EXISTS
Selects rows from e2 where a matching salary exists in e1.

sql
Copy
Edit
SELECT *
FROM e2
WHERE EXISTS (
    SELECT 1
    FROM e1
    WHERE e1.salary = e2.salary
);
