# Experiment 2: DDL Commands

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

<img width="1191" height="395" alt="image" src="https://github.com/user-attachments/assets/64589166-49d8-4010-97d0-f3abc4dff84a" />

**Code**
---
```sql
alter table employees add column salary INTEGER; 
```

**Output:**

<img width="1179" height="287" alt="image" src="https://github.com/user-attachments/assets/e4a64d8e-c22b-4cbc-b2a2-68384b7bcbb3" />


**Question 2**
---

<img width="1188" height="609" alt="image" src="https://github.com/user-attachments/assets/c31f4d02-4d17-4dff-be32-b4af7aff7ae6" />

**Code**
---
```sql
alter table Student_details add column Mobilenumber number;
```

**Output:**
<img width="1186" height="354" alt="image" src="https://github.com/user-attachments/assets/1e9ea43f-c0d5-4b0d-adb8-e6d69570e801" />



**Question 3**
---

<img width="1199" height="369" alt="image" src="https://github.com/user-attachments/assets/361077c5-50c7-400c-a55d-1d67b7f47cb7" />

**Code**
---
```sql
CREATE TABLE ProjectAssignments(
AssignmentID INTEGER primary key,
EmployeeID INTEGER,
ProjectID INTEGER,
AssignmentDate DATE NOT NULL,
foreign key (EmployeeID) REFERENCES Employees(EmployeeID)
foreign key (ProjectID) REFERENCES Projects(ProjectID)
);
```

**Output:**

<img width="1188" height="285" alt="image" src="https://github.com/user-attachments/assets/52efaa3a-19d2-4651-a452-82dae24a29ba" />

**Question 4**
---
<img width="1079" height="359" alt="image" src="https://github.com/user-attachments/assets/65d707be-7027-4a9b-b8a4-b83d10aa35bd" />

**Code**
---
```sql
CREATE TABLE Invoices(
InvoiceID INT PRIMARY KEY,
InvoiceDate DATE,
DueDate DATE check(DueDate>InvoiceDate),
Amount REAL check(Amount>0)
);
```

**Output:**
<img width="1179" height="285" alt="image" src="https://github.com/user-attachments/assets/6f59befe-fe24-4952-8503-c35679ee4cae" />


**Question 5**
---
<img width="789" height="339" alt="image" src="https://github.com/user-attachments/assets/24933e12-014c-44b8-843a-fe3e9547aee9" />

**Code**
---
```sql
insert into Employee(EmployeeID,Name,Department,Salary)
SELECT EmployeeID,Name,Department,Salary
FROM Former_employees
```

**Output:**
<img width="1170" height="274" alt="image" src="https://github.com/user-attachments/assets/6af0cd40-d5e5-4a81-9283-ff08fab23c0d" />


**Question 6**
---
<img width="1041" height="230" alt="image" src="https://github.com/user-attachments/assets/20d35bfc-abbb-4c3d-837f-bdc5bda67447" />

**Code**
---
```sql
insert into Student_details(RollNo,Name,Gender,Subject,MARKS)
values(201,'David Lee','M','Physics',92);
```

**Output:**
<img width="1186" height="218" alt="image" src="https://github.com/user-attachments/assets/926362e6-91fe-49e3-8fe2-00995be9e5e1" />



**Question 7**
---
<img width="1180" height="400" alt="image" src="https://github.com/user-attachments/assets/d7bd2409-b010-47f6-892d-eebf27015400" />

**Code**
---
```sql
create table Reviews(
ReviewID INTEGER,
ProductID INTEGER,
Rating REAL,
ReviewText TEXT);
```

**Output:**
<img width="960" height="461" alt="image" src="https://github.com/user-attachments/assets/afa90542-2403-4fa4-9d47-fa248094576c" />


**Question 8**
---
<img width="1165" height="498" alt="image" src="https://github.com/user-attachments/assets/d7b7a139-b0bf-4147-9aa1-065371decb88" />

**Code**
---
```sql
insert into Student_details(Rollno,Name,Gender,Subject,MARKS)
values(205,'Olivia Green','F',NULL,NULL),(207,'Liam Smith','M','Mathematic',85),(208,'Sophia Johns','F','Science',NULL);
```

**Output:**

<img width="1178" height="271" alt="image" src="https://github.com/user-attachments/assets/5aa82aa3-112b-4d9b-931e-9acba5bc253c" />


**Question 9**
---
<img width="1033" height="460" alt="image" src="https://github.com/user-attachments/assets/849ee7c0-d11a-4ac2-bbcd-38052f1c90d8" />

**Code**
---
```sql
CREATE TABLE item (
    item_id TEXT PRIMARY KEY,
    item_desc TEXT NOT NULL,
    rate INTEGER NOT NULL,
    icom_id TEXT CHECK (LENGTH(icom_id) = 4),
    FOREIGN KEY (icom_id) REFERENCES company(com_id)
    ON UPDATE CASCADE
    ON DELETE CASCADE
);
```

**Output:**

<img width="1177" height="338" alt="image" src="https://github.com/user-attachments/assets/81c56e70-3b98-434a-9b21-4ed5187af602" />


**Question 10**
---
<img width="1192" height="502" alt="image" src="https://github.com/user-attachments/assets/8153c3ca-cdaa-450f-98a1-f7049add8990" />

**Code**
---
```sql
create table products(
product_id int primary key,
product_name varchar(30),
list_price int not null,
discount int not null default 0
check(
list_price>=discount and
discount>=0 and
list_price>=0));
```

**Output:**
---
<img width="1186" height="276" alt="image" src="https://github.com/user-attachments/assets/0a957b00-c043-4aa2-886d-e5ff7c762380" />

**Seb exam:**
---
<img width="1360" height="72" alt="image" src="https://github.com/user-attachments/assets/afcbd982-6ed8-4439-a1e7-e29bab435bdb" />


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
