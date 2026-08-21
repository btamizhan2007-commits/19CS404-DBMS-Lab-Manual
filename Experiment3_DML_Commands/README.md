# Experiment 3: DML Commands

## TAMIZHAN B
## REF NO: 212225230283

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**
--

<img width="880" height="665" alt="q1" src="https://github.com/user-attachments/assets/97bba360-1bd8-42e1-a5d8-79b1535d930a" />

```sql
delete from Doctors where last_name is NULL;
```

**Output:**

<img width="1192" height="863" alt="a1" src="https://github.com/user-attachments/assets/55f72f22-a962-456d-84eb-1b3353535b24" />

**Question 2**
---

<img width="1119" height="741" alt="q2" src="https://github.com/user-attachments/assets/49c912e0-c60b-469b-a22e-12ff3cc519b9" />

```sql
select product_id,original_price,discount_percentage,(original_price*(1-discount_percentage)) as discounted_price from Products where original_price between 50 and 150; 
```

**Output:**

<img width="1206" height="388" alt="a2" src="https://github.com/user-attachments/assets/47a71ea6-327b-4d8d-ad42-aff4d8fd61aa" />

**Question 3**
---

<img width="1180" height="726" alt="q3" src="https://github.com/user-attachments/assets/18838d98-aa95-4e62-8a95-6375f9c8549b" />

```sql
update products set reorder_lvl=reorder_lvl*0.7 where product_name like '%cream%' and quantity>reorder_lvl;
```

**Output:**

<img width="1192" height="548" alt="a3" src="https://github.com/user-attachments/assets/b47453f8-de98-48d8-9101-c331ec32d66b" />

**Question 4**
---

<img width="1106" height="668" alt="q4" src="https://github.com/user-attachments/assets/67e52d5f-7dc6-4f96-b975-2cfe8dbf6251" />

```sql
select EmpID,EmpFname,EmpLname,Department,Project,Address,DOB,Gender from  EmployeeInfo1  where Department is NULL;
```

**Output:**

<img width="1252" height="301" alt="a4" src="https://github.com/user-attachments/assets/226f47ff-3125-4f5d-80d3-506ba0f20c6b" />

**Question 5**
---

<img width="994" height="832" alt="q5" src="https://github.com/user-attachments/assets/89533739-f5f6-4ea8-8c13-364ca0360ea8" />

```sql
select * from emp where hiredate between '2024-06-01' and '2024-09-01';
```

**Output:**

<img width="1238" height="410" alt="a5" src="https://github.com/user-attachments/assets/2137c079-f8a5-4c09-87c3-9f13ae965f3e" />

**Question 6**
---

<img width="1202" height="569" alt="q6" src="https://github.com/user-attachments/assets/75087c28-db36-451f-93b5-70397f205528" />


```sql
select product_id,original_price,discount_percentage,tax_rate,(original_price *(1-discount_percentage))*(1+tax_rate) as final_price from Products;
```

**Output:**

<img width="1240" height="328" alt="a6" src="https://github.com/user-attachments/assets/6b426846-4636-4642-ae9e-bf4428208d8e" />

**Question 7**
---

<img width="1237" height="541" alt="q7" src="https://github.com/user-attachments/assets/350ff9ac-7fea-4a8e-8393-a4fb8f1e2794" />


```sql
select customer_id,city,grade,'High Rating' as Rating from customer where grade>=300
union
select customer_id,city,grade,'Low Rating' as Rating from customer where grade<300;
```

**Output:**

<img width="954" height="550" alt="a7" src="https://github.com/user-attachments/assets/b2b304cb-49f6-4ec8-929f-8674fe412b46" />


**Question 8**
---

<img width="1239" height="494" alt="q8" src="https://github.com/user-attachments/assets/81452ecd-47b4-4434-b36f-45e395cfe350" />

```sql
delete from Customer where CUST_CITY<>'New York' and OUTSTANDING_AMT >5000;
```

**Output:**

<img width="1175" height="450" alt="a8" src="https://github.com/user-attachments/assets/54ae2b39-27df-49ac-9c38-0549e07b190d" />

**Question 9**
---

<img width="1263" height="510" alt="q9" src="https://github.com/user-attachments/assets/2c67a01f-f342-49d4-9888-c83bb0c2665c" />

```sql
select customer_id,cust_name,city,grade,salesman_id from customer where city='New York' or grade >200;
```

**Output:**

<img width="1252" height="654" alt="a9" src="https://github.com/user-attachments/assets/418f8db6-745f-4853-9bc4-86d55f739c59" />

**Question 10**
---

<img width="1205" height="582" alt="q10" src="https://github.com/user-attachments/assets/423c5c15-1649-40eb-878a-deec72da9d8b" />

```sql
delete from customer where GRADE =2;
```

**Output:**

<img width="1251" height="314" alt="a10" src="https://github.com/user-attachments/assets/4ab34213-1d34-4d5b-9fa6-943814102644" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
