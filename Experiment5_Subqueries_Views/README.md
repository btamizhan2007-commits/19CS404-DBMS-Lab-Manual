# Experiment 5: Subqueries and Views

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```


**Question 1**
--
What is the average dosage prescribed for each medication?
Sample tablePrescriptions Table
```
Medication     AvgDosage
-------------  ----------
Ciprofloxacin  500.0
Doxorubicin    60.0
Ibuprofen      400.0
Levothyroxine  50.0
Lisinopril     10.0
MMR            0.5
Pending        0.0
Prenatal vita  1.0
Sertraline     50.0
Topiramate     25.0
```
```
SELECT
  Medication,
  AVG(Dosage) AS AvgDosage
FROM
  Prescriptions
GROUP BY
  Medication;
```


**Output:**
<img width="697" height="745" alt="image" src="https://github.com/user-attachments/assets/0942632f-2398-4d0f-bc08-082e6c9cf8be" />


**Question 2**
---
How many patients are there in each city?

```sql
Sample table: Patients Table

Address     TotalPatients
----------  -------------
Berlin      3
Chicago     4
Mexico      3
```
```
select Address,count(*)
as TotalPatients
from Patients
group by Address
```

**Output:**
<img width="661" height="396" alt="image" src="https://github.com/user-attachments/assets/14cc621a-709f-4234-9662-901aa679cfac" />


**Question 3**
---
Write a SQL Query to find how many medications are prescribed for each patient?

Sample table:MedicalRecords Table

```sql
PatientID   AvgMedications
----------  --------------
4           5
6           1
7           1
8           3

```
```
SELECT PatientID,COUNT(*) AS 
AvgMedications
FROM MedicalRecords
GROUP BY PatientID;
```

**Output:**
<img width="679" height="614" alt="image" src="https://github.com/user-attachments/assets/d62a60a3-e5e9-4b7d-b1a4-91aa8ef2230b" />


**Question 4**
---
Write a SQL query to find the maximum purchase amount.

Sample table: orders

```sqlord_no      purch_amt   ord_date    customer_id  salesman_id

----------  ----------  ----------  -----------  -----------

70001       150.5       2012-10-05  3005         5002

70009       270.65      2012-09-10  3001         5005

70002       65.26       2012-10-05  3002         5001
```
```
SELECT
  MAX(purch_amt) AS MAXIMUM
FROM
  orders;
```
**Output:**
<img width="408" height="298" alt="image" src="https://github.com/user-attachments/assets/00330865-471c-43f0-b5a7-b80ccab0405c" />


**Question 5**
---
Write a SQL query to find the total income of employees aged 40 or above.

Table: employee

```sql
name        type
----------  ----------
id          INTEGER
name        TEXT
age         INTEGER
city        TEXT
income      INTEGER

```
```
SELECT
  SUM(income) AS total_income
FROM
  employee
WHERE
  age >= 40;
```

**Output:**
<img width="442" height="308" alt="image" src="https://github.com/user-attachments/assets/2a700fff-2b36-471e-b991-df3c92445cc7" />

**Question 6**
---
Write a SQL query to find the number of employees whose age is greater than 32.

Sample table: employee

```sql
SELECT
  COUNT(*) AS COUNT
FROM
  employee
WHERE
  age > 32;
```

**Output:**

<img width="439" height="321" alt="image" src="https://github.com/user-attachments/assets/e739692b-f583-4b2b-a762-abd088cfa24c" />


**Question 7**
---
Write a SQL query to find the average length of names for people living in Chennai?

Table: customer

```sql
name        type
----------  ----------
id          INTEGER
name        TEXT   
city        TEXT
email       TEXT
phone       INTEGER
```
```
SELECT
  AVG(LENGTH(name)) AS avg_name_length
FROM
  customer
WHERE
  city = 'Chennai';
```

**Output:**
<img width="445" height="296" alt="image" src="https://github.com/user-attachments/assets/d1854149-bf8a-42a5-a00b-263d84c2d4f8" />


**Question 8**
---
Write the SQL query that accomplishes the grouping of data by joining date (jdate), calculates the maximum work hours for each date, and excludes dates where the maximum work hour is not greater than 12.

Sample table: employee1


```
jdate       MAX(workhour)
----------  -------------
2004.0      15
2006.0      15
```
```
SELECT
  jdate,
  MAX(workhour) AS "MAX(workhour)"
FROM
  employee1
GROUP BY
  jdate
HAVING
  MAX(workhour) > 12;
```
**Output:**
<img width="673" height="376" alt="image" src="https://github.com/user-attachments/assets/daa441c7-2c67-4ae9-939d-001572fc71cb" />


**Question 9**
---
Write the SQL query that achieves the grouping of data by occupation, calculates the total work hours for each occupation, and excludes occupations where the total work hour sum is not greater than 20.

Sample table: employee1

```sql
occupation  SUM(workhour)
----------  -------------
Business    30
Doctor      30
Engineer    24
Teacher     27
```
```
SELECT
  occupation,
  SUM(workhour) AS "SUM(workhour)"
FROM
  employee1
GROUP BY
  occupation
HAVING
  SUM(workhour) > 20;
```

**Output:**
<img width="619" height="432" alt="image" src="https://github.com/user-attachments/assets/fbd78c16-60c1-4d15-afa0-bafb6b8d18f4" />


**Question 10**
---
Write the SQL query that achieves the grouping of data by occupation, calculates the average work hours for each occupation, and includes only those occupations where the average work hour falls between 10 and 12.

Sample table: employee1

```sql
occupation  AVG(workhour)
----------  -------------
Business    10.0
Engineer    12.0
```
```
SELECT
  occupation,
  AVG(workhour) AS "AVG(workhour)"
FROM
  employee1
GROUP BY
  occupation
HAVING
  AVG(workhour) BETWEEN 10 AND 12;
```

**Output:**
<img width="757" height="392" alt="image" src="https://github.com/user-attachments/assets/5044a4af-91d0-4a68-ba47-7b6473b42326" />



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
