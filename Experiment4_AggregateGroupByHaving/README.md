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
<img width="1029" height="544" alt="image" src="https://github.com/user-attachments/assets/78f17f9d-a34e-4741-9094-6200b1c43faa" />


```sql
select PatientID,count(*) as TotalRecords
from MedicalRecords
group by PatientID;
```

**Output:**
<img width="1047" height="644" alt="image" src="https://github.com/user-attachments/assets/961840c8-ea1c-4452-966b-c08d378c2f4f" />


**Question 2**
---
<img width="1015" height="547" alt="image" src="https://github.com/user-attachments/assets/e1c143f2-2939-41b4-bf91-488460fe5590" />


```sql
select DoctorID , count(*) AS TotalRecords
from MedicalRecords
group by DoctorID;
```

**Output:**
<img width="1002" height="623" alt="image" src="https://github.com/user-attachments/assets/225d1ea0-d877-4813-82e7-903c8fee9f45" />




**Question 3**
---
<img width="1034" height="577" alt="image" src="https://github.com/user-attachments/assets/f430ac36-43f1-4e58-a121-2f983562b18e" />


```sql
select Specialty , count(*) AS TotalDocto
from Doctors
group by Specialty;
```

**Output:**
<img width="1042" height="673" alt="image" src="https://github.com/user-attachments/assets/0f1a92d5-a6e1-46f4-bf1a-e961442000b0" />

**Question 4**
---
<img width="1009" height="478" alt="image" src="https://github.com/user-attachments/assets/dc15e383-b3fa-461b-bc26-8db38c90acc9" />


```sql
select count(*) AS COUNT
from customer
where city <> "Noida";
```

**Output:**

<img width="903" height="292" alt="image" src="https://github.com/user-attachments/assets/43fefd69-e723-42aa-9eca-fe023e86a999" />


**Question 5**
---
<img width="888" height="468" alt="image" src="https://github.com/user-attachments/assets/eb6c2656-5e01-474c-a89d-d3ebc4f9dc6e" />


```sql
select name,MAX(LENGTH(name)) as length
from customer;
```

**Output:**

<img width="827" height="302" alt="image" src="https://github.com/user-attachments/assets/1cc337c6-1a8b-4b82-b09c-6b0ca57d8a11" />


**Question 6**
---
<img width="1065" height="459" alt="image" src="https://github.com/user-attachments/assets/3078de0f-d969-49cf-bd46-f9fafdccdb8f" />


```sql
select count(DISTINCT city) AS unique_cities
from customer;
```

**Output:**

<img width="833" height="312" alt="image" src="https://github.com/user-attachments/assets/3065f294-7ba2-4844-8654-cef4f3183b75" />



**Question 7**
---
<img width="973" height="435" alt="image" src="https://github.com/user-attachments/assets/2076c974-60d4-4d3c-a200-2bfd170ae801" />


```sql
select SUM(income) AS total_income
from employee
where age >= 40;
```

**Output:**

<img width="810" height="296" alt="image" src="https://github.com/user-attachments/assets/bf1fc5bc-2e4a-4f32-838b-2fadbeb6fbb1" />



**Question 8**
---

<img width="1192" height="451" alt="image" src="https://github.com/user-attachments/assets/fa534447-2080-45b3-9c0b-3e93e18c4b84" />


```sql
select (age/5)* 5 as age_group , MIN(age) as "MIN(age)"
from customer1
group by (age/5) * 5
having MIN(age) < 25;
```

**Output:**

<img width="877" height="316" alt="image" src="https://github.com/user-attachments/assets/5025ee78-7bcf-4fb9-9551-396a4ca57007" />



**Question 9**
---
<img width="1183" height="475" alt="image" src="https://github.com/user-attachments/assets/d9e5b0e8-ec5d-40bb-80f7-1fcadac5cd52" />

```sql
select address, AVG(salary) AS "AVG(salary)"
from customer1
group by address
having AVG(salary) > 5000;
```

**Output:**

<img width="810" height="432" alt="image" src="https://github.com/user-attachments/assets/581f150a-5aaa-4a59-b2f2-272c3802be33" />



**Question 10**
---

<img width="1155" height="497" alt="image" src="https://github.com/user-attachments/assets/cbca8039-73b4-4c1f-8efa-5a7a470c6d38" />


```sql
select jdate,SUM(workhour) AS "SUM(workhour)"
from employee1
group by jdate
having SUM(workhour) > 40;
```

**Output:**

<img width="981" height="374" alt="image" src="https://github.com/user-attachments/assets/6735e9a3-43dd-4f72-ac63-de73eb1a6c93" />



**SEB EXAM**
<img width="1206" height="112" alt="image" src="https://github.com/user-attachments/assets/fce2cc82-99d1-4b94-a235-74350245aea2" />



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
