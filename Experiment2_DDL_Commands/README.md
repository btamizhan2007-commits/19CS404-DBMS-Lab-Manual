# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## NAME: TAMIZHAN B
## REF NO: 212225230283

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
<img width="952" height="488" alt="image" src="https://github.com/user-attachments/assets/a310052c-03fb-4f1f-b9b6-dbf77799e806" />

```sql
alter table employee rename column id to employee_id;
```

**Output:**

<img width="1274" height="337" alt="image" src="https://github.com/user-attachments/assets/8771f8c9-2f13-4d5a-a56f-87435188e3a2" />

**Question 2**
---

<img width="892" height="515" alt="image" src="https://github.com/user-attachments/assets/f74f28b7-c041-4e21-966c-7c14df9efe6e" />

```sql
create table Customers(
CustomerID INTEGER,
Name TEXT,
Email TEXT,
JoinDate DATETIME
);
```

**Output:**

<img width="1263" height="466" alt="image" src="https://github.com/user-attachments/assets/97595ece-4e9b-45c9-b1fd-82942f6e8e70" />

**Question 3**
---

<img width="1262" height="564" alt="image" src="https://github.com/user-attachments/assets/1ea80de2-b12e-44c6-94f7-e03c4fa567d0" />

```sql

insert into Customers(CustomerID,Name,Address) 
values(306,'Diana Prince','Themyscira');
insert into Customers(CustomerID,Name,Address,City,Zipcode)
values(307,'Bruce Wayne','Wayne Mano','Gotham',10007);
insert into Customers(CustomerID,Name,Address,Zipcode)
values(308,'Peter Parker','Queens',11375);
```

**Output:**

<img width="1270" height="354" alt="image" src="https://github.com/user-attachments/assets/69d9aab3-db4b-4376-813a-c68471a6c295" />

**Question 4**
---

<img width="782" height="464" alt="image" src="https://github.com/user-attachments/assets/5b0b9cb2-3390-4a23-b014-6cc70e6b4595" />

```sql
insert into Employee(EmployeeID,Name,Position,Department,Salary)
values (2,'John Smith','Developer','IT',75000),
(3,'Anna Bell','Designer','Marketing',68000);
```

**Output:**

<img width="1276" height="424" alt="image" src="https://github.com/user-attachments/assets/17b64fc8-b0a1-4c87-96d1-ddd35968258f" />


**Question 5**
---

<img width="1243" height="568" alt="image" src="https://github.com/user-attachments/assets/e7e26b45-ab0d-4d66-b3ab-2b327d89cc71" />

```sql
insert into Employee(EmployeeID,Name,Position)
values(5,'George Clark','Consultant');
insert into Employee(EmployeeID,Name,Position,Department,Salary)
values(7,'Noah Davis','Manager','HR',60000);
insert into Employee(EmployeeID,Name,Position,Department)
values(8,'Ava Miller','Consultant','IT');
```

**Output:**

<img width="1274" height="350" alt="image" src="https://github.com/user-attachments/assets/813d2aeb-77bf-4e6e-bfb2-a00df2ae4bef" />

**Question 6**
---

<img width="1197" height="433" alt="image" src="https://github.com/user-attachments/assets/53da816e-f610-4cf6-bf6c-8e1692870b6e" />

```sql
ALTER TABLE  Companies
RENAME name to first_name;

ALTER TABLE  Companies
ADD  mobilenumber  number;

ALTER TABLE  Companies
ADD DOB  Date;

ALTER TABLE  Companies
ADD State varchar(30);
);
```

**Output:**

<img width="1251" height="432" alt="image" src="https://github.com/user-attachments/assets/bf33b304-3683-424e-b6ff-77d2397aa9e4" />

**Question 7**
---
<img width="856" height="516" alt="image" src="https://github.com/user-attachments/assets/177e64c7-08cd-481b-96d3-2d60f0152ad0" />

```sql
create table Products(
ProductID INTEGER,
ProductName TEXT,
Price REAL,
Stock INTEGER 
);
```

**Output:**

<img width="1234" height="342" alt="image" src="https://github.com/user-attachments/assets/32424b64-a03e-431d-9b70-49fd1a643450" />

**Question 8**
---

<img width="1235" height="354" alt="image" src="https://github.com/user-attachments/assets/3f0bff58-b7ca-4226-9f3f-f70f04653fef" />

```sql
alter table employee add column designation varchar(50);
```

**Output:**

<img width="1244" height="331" alt="image" src="https://github.com/user-attachments/assets/e9c6e228-afff-402c-a8c1-ba3ae5db3070" />


**Question 9**
---
<img width="1258" height="342" alt="image" src="https://github.com/user-attachments/assets/dfccd3c0-95e1-456a-97fd-2d22ca0b025c" />

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

<img width="1243" height="319" alt="image" src="https://github.com/user-attachments/assets/b4db2faf-c9d6-4b74-ac93-492267ea9c65" />

**Question 10**
---
<img width="877" height="463" alt="image" src="https://github.com/user-attachments/assets/dfb9d903-e289-4735-adb1-df1903685559" />

```sql
create table Tasks(
TaskID INTEGER,
TaskName TEXT,
DueDate DATE 
);
```

**Output:**

<img width="1247" height="410" alt="image" src="https://github.com/user-attachments/assets/0e1a120c-e78d-4ce4-99cf-373e0f96d0aa" />


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
