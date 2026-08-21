# Experiment 2: DDL Commands

## NAME: TAMIZHAN B
## REF NO: 212225230283

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**
--

<img width="925" height="432" alt="q1" src="https://github.com/user-attachments/assets/4384b93b-3dff-4deb-bab1-b60e5446b095" />


```sql
alter table employee rename column id to employee_id;
```

**Output:**

<img width="1251" height="339" alt="a1" src="https://github.com/user-attachments/assets/3682e985-f418-4c39-8638-668bd7d3900a" />

**Question 2**
---

<img width="902" height="461" alt="q2" src="https://github.com/user-attachments/assets/e341f0eb-738f-460c-831a-3229454e52ce" />

```sql
create table Customers(
CustomerID INTEGER,
Name TEXT,
Email TEXT,
JoinDate DATETIME
);
```

**Output:**

<img width="1239" height="416" alt="a2" src="https://github.com/user-attachments/assets/30f559bd-512a-4486-89a1-356f2650a8c5" />


**Question 3**
---

<img width="1212" height="495" alt="q3" src="https://github.com/user-attachments/assets/f2100cec-d20b-4c64-91cc-1dcace4766a2" />

```sql
insert into Customers(CustomerID,Name,Address) 
values(306,'Diana Prince','Themyscira');
insert into Customers(CustomerID,Name,Address,City,Zipcode)
values(307,'Bruce Wayne','Wayne Mano','Gotham',10007);
insert into Customers(CustomerID,Name,Address,Zipcode)
values(308,'Peter Parker','Queens',11375);
```

**Output:**

<img width="1252" height="328" alt="a3" src="https://github.com/user-attachments/assets/e2c9a079-5196-444d-9bca-1bdf28393d39" />

**Question 4**
---

<img width="767" height="404" alt="q4" src="https://github.com/user-attachments/assets/6c1c7d83-e25f-47d7-ba03-9fb85794534c" />

```sql
insert into Employee(EmployeeID,Name,Position,Department,Salary)
values (2,'John Smith','Developer','IT',75000),
(3,'Anna Bell','Designer','Marketing',68000);
```

**Output:**

<img width="1262" height="388" alt="a4" src="https://github.com/user-attachments/assets/4b7ceb49-19ac-4827-a758-ba24f5205b8b" />

**Question 5**
---

<img width="1225" height="500" alt="q5" src="https://github.com/user-attachments/assets/22b72a2c-d425-4b91-927a-7ddf06c103c8" />

```sql
insert into Employee(EmployeeID,Name,Position)
values(5,'George Clark','Consultant');
insert into Employee(EmployeeID,Name,Position,Department,Salary)
values(7,'Noah Davis','Manager','HR',60000);
insert into Employee(EmployeeID,Name,Position,Department)
values(8,'Ava Miller','Consultant','IT');
```

**Output:**

<img width="1243" height="316" alt="a5" src="https://github.com/user-attachments/assets/7fb7550e-3c3f-4435-8a1c-3819b635c29d" />

**Question 6**
---

<img width="883" height="455" alt="q6" src="https://github.com/user-attachments/assets/8d3c34a0-6113-4d8c-a3a2-43b694d46488" />

```sql
create table Products(
ProductID INTEGER,
ProductName TEXT,
Price REAL,
Stock INTEGER 
);
```

**Output:**

<img width="1252" height="338" alt="a6" src="https://github.com/user-attachments/assets/5415f5e5-93c1-4a93-beb7-218314c4faa1" />

**Question 7**
---

<img width="880" height="315" alt="q7" src="https://github.com/user-attachments/assets/541952dc-d795-412e-b3d8-5b86663c9cc1" />

```sql
alter table employee add column designation varchar(50);
```

**Output:**

<img width="1235" height="309" alt="a7" src="https://github.com/user-attachments/assets/14b925cf-137b-42eb-837f-93e1b30686c9" />

**Question 8**
---

<img width="888" height="401" alt="q8" src="https://github.com/user-attachments/assets/09bdc544-e6cc-4454-801d-fdef58f29da5" />

```sql
create table Tasks(
TaskID INTEGER,
TaskName TEXT,
DueDate DATE 
);
```

**Output:**

<img width="1235" height="400" alt="a8" src="https://github.com/user-attachments/assets/8129a594-c3fc-4dd3-a3dd-9db150a2349c" />

**Question 9**
---

<img width="1254" height="359" alt="q9" src="https://github.com/user-attachments/assets/328a7841-9955-4b17-9cbb-15d724484af7" />

```sql
CREATE TABLE ProjectAssignments(
AssignmentID INTEGER PRIMARY KEY,
EmployeeID  INTEGER, 
ProjectID INTEGER,
AssignmentDate  DATE NOT NULL,
FOREIGN KEY (EmployeeID)
   REFERENCES  Employees(EmployeeID)
FOREIGN KEY (ProjectID)
   REFERENCES  Projects(ProjectID)
);
```

**Output:**

<img width="1247" height="307" alt="a9" src="https://github.com/user-attachments/assets/e900238c-dc75-4beb-8acb-25323afe2e2e" />

**Question 10**
---

<img width="1200" height="420" alt="q10" src="https://github.com/user-attachments/assets/7124df24-a976-4079-aa6a-c6a16d9dfc68" />

```sql
ALTER TABLE  Companies
RENAME name to first_name;

ALTER TABLE  Companies
ADD  mobilenumber  number;

ALTER TABLE  Companies
ADD DOB  Date;

ALTER TABLE  Companies
ADD State varchar(30);
```

**Output:**

<img width="1253" height="439" alt="a10" src="https://github.com/user-attachments/assets/bd9b22ed-c05b-4b8b-9079-3538ac4149c7" />

## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
