# Experiment 4: Aggregate Functions, Group By and Having Clause

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**
--
What is the average dosage prescribed for each medication?

```sql
SELECT MIN(salary) AS minimum_salary
FROM staff;

```

**Output:**

<img width="827" height="316" alt="image" src="https://github.com/user-attachments/assets/6353d027-7d50-4d77-a470-777401bd7cac" />


**Question 2**
---
Find the maximum salary of all staff members

```sql
SELECT MAX(salary) AS maximum_salary
FROM staff;

```

**Output:**
<img width="842" height="412" alt="image" src="https://github.com/user-attachments/assets/ebd38f2c-7617-4fbf-91f9-ff7b6e67b4b6" />


**Question 3**
---
Find the total salary of all staff members.

```sql
SELECT SUM(salary) AS total_salary
FROM staff;

```

**Output:**
<img width="837" height="312" alt="image" src="https://github.com/user-attachments/assets/29d6708c-c706-492f-8d78-8df7cec29160" />


**Question 4**
---
Find the average salary of all staff members

```sql
SELECT AVG(salary) AS average_salary
FROM staff;
```

**Output:**
<img width="837" height="442" alt="image" src="https://github.com/user-attachments/assets/38326095-3e56-47c5-b328-1923ea8120e8" />


**Question 5**
---
Find the total number of staff members.

```sql
SELECT COUNT(*) AS total_staff
FROM staff;

```

**Output:**
<img width="830" height="397" alt="image" src="https://github.com/user-attachments/assets/72465081-6e90-414f-8925-8a75f552537f" />


**Question 6**
---
Find the number of staff members in each department.

```sql
SELECT department, COUNT(*) AS staff_count
FROM staff
GROUP BY department;

```

**Output:**

<img width="827" height="382" alt="image" src="https://github.com/user-attachments/assets/efda5ac7-381e-455f-90bb-1ddadb29c8bc" />


**Question 7**
---

Find the total salary paid in each department.
```sql
SELECT department, SUM(salary) AS total_salary
FROM staff
GROUP BY department;

```

**Output:**

<img width="867" height="345" alt="image" src="https://github.com/user-attachments/assets/58efdb3d-1185-46b5-b087-a84f94cbb4a4" />


**Question 8**
---
Find the average salary in each department.

```sql
SELECT department, AVG(salary) AS average_salary
FROM staff
GROUP BY department;

```

**Output:**

<img width="821" height="305" alt="image" src="https://github.com/user-attachments/assets/2ea6e518-54bd-402e-bf63-7d3c95a385c8" />


**Question 9**
---

Display departments having more than 2 staff members.
```sql

SELECT department, COUNT(*) AS staff_count
FROM staff
GROUP BY department
HAVING COUNT(*) > 2;
```

**Output:**
<img width="827" height="367" alt="image" src="https://github.com/user-attachments/assets/53af328d-8276-4663-9ab7-9f34df0ef0cb" />


**Question 10**
---
Display departments whose total salary is greater than 150000.

```sql
SELECT department, SUM(salary) AS total_salary
FROM staff
GROUP BY department
HAVING SUM(salary) > 150000;

```

**Output:**
<img width="836" height="276" alt="image" src="https://github.com/user-attachments/assets/7cdf0cf6-5128-409f-807e-898233d455b4" />



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
