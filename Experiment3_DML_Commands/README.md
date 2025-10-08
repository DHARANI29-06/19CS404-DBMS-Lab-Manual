# Experiment 3: DML Commands

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
<img width="1066" height="525" alt="image" src="https://github.com/user-attachments/assets/9f0b6690-9cdc-4fed-9f27-2fb76da56571" />


```sql
update Products
set reorder_lvl = 40 
where category = 'Grocery';
```

**Output:**

<img width="1196" height="402" alt="image" src="https://github.com/user-attachments/assets/9c52a84f-e024-4fd2-a8a2-f39fed2dccd0" />


**Question 2**
---
<img width="1158" height="507" alt="image" src="https://github.com/user-attachments/assets/b14b3e04-08ca-4f00-abc2-b35f9fead78b" />


```sql
update Products
set reorder_lvl = 20 
where quantity < 10 
and category = 'Snacks';
```

**Output:**

<img width="1181" height="576" alt="image" src="https://github.com/user-attachments/assets/a2d1bb8d-142e-457f-b8f5-d7ddda343cc3" />


**Question 3**
---
<img width="1206" height="711" alt="image" src="https://github.com/user-attachments/assets/d80039cf-8140-4a13-b215-68ee502ec86a" />


```sql
update Employees
set salary = salary + 500,
email = 'updated'
where job_id = 'SA_REP'
and commission_pct > 0.15;
```

**Output:**
<img width="1197" height="530" alt="image" src="https://github.com/user-attachments/assets/c19650ee-2b07-491c-9fd7-4bfee31d23f4" />



**Question 4**
---
<img width="1020" height="212" alt="image" src="https://github.com/user-attachments/assets/126b38c6-0475-414a-a953-f6e3b2ac8b66" />


```sql
update products
set product_name = 'Grapefruit'
where product_id = 4;
```

**Output:**
<img width="1189" height="250" alt="image" src="https://github.com/user-attachments/assets/538f3da8-9b36-40da-80fe-828bfb4d08db" />



**Question 5**
---
<img width="1078" height="525" alt="image" src="https://github.com/user-attachments/assets/1d773343-1113-4ab7-911c-63e51108ad2c" />


```sql
update Products
set category = 'Household'
where product_name LIKE '%Detergent%';
```

**Output:**

<img width="1197" height="504" alt="image" src="https://github.com/user-attachments/assets/6fd6dc8f-ad8c-4f98-ab4a-c697a3f1b271" />

**Question 6**
---
<img width="1209" height="488" alt="image" src="https://github.com/user-attachments/assets/689198fb-4461-4ce5-9e1b-f776292ab378" />


```sql
delete from Customer
where (grade = 2 and CUST_NAME LIKE 'M%')
and PAYMENT_AMT < 3000;
```

**Output:**

<img width="1187" height="411" alt="image" src="https://github.com/user-attachments/assets/639419e8-ff40-46db-85fd-35ec320aa9aa" />


**Question 7**
---
<img width="1199" height="486" alt="image" src="https://github.com/user-attachments/assets/1af6919d-2edf-4e8a-affd-81fe4b5d0524" />

```sql
delete from Customer
where grade %2 = 1;
```

**Output:**


<img width="1200" height="427" alt="image" src="https://github.com/user-attachments/assets/43c21129-b3f5-4b94-8b47-1fd65c1cf2e1" />

**Question 8**
---
<img width="808" height="157" alt="image" src="https://github.com/user-attachments/assets/4fd69e5c-eb50-418d-991b-cec8c6c69710" />

```sql
delete from Doctors 
where doctor_id=1;
```

**Output:**
<img width="1196" height="274" alt="image" src="https://github.com/user-attachments/assets/89f97b59-88b9-42a8-9fb5-e9aecb9721f0" />


**Question 9**
---
<img width="1208" height="484" alt="image" src="https://github.com/user-attachments/assets/89ba856b-7483-443d-9bc4-92159490b8b9" />

```sql
delete from Customer
where (grade = 3 
or AGENT_CODE = 'A008')
and OUTSTANDING_AMT < 5000;
```

**Output:**
<img width="1199" height="410" alt="image" src="https://github.com/user-attachments/assets/fb9156b7-3871-4b9f-b2dc-c69105314198" />



**Question 10**
---
<img width="1208" height="724" alt="image" src="https://github.com/user-attachments/assets/07a56ae6-64d0-4435-9616-2d544e4947de" />


```sql
Delete from Customer
where grade = 2;
```

**Output:**
<img width="1193" height="600" alt="image" src="https://github.com/user-attachments/assets/fbbfc6ae-41e5-4045-bc89-6a286041a120" />

**Module Examination**
---
<img width="1314" height="77" alt="image" src="https://github.com/user-attachments/assets/0b26cb48-8560-4cc2-a634-c6dc1a9a451b" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
