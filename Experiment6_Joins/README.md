# Experiment 6: Joins

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

**Question 1**
--
<img width="1213" height="758" alt="image" src="https://github.com/user-attachments/assets/85214cfa-a6c5-4619-a1f8-94a84f76ed80" />


```sql
select p.first_name as 'patient_name',t.*
from patients p
inner join test_results t on p.patient_id = t.patient_id

```

**Output:**

<img width="1248" height="561" alt="image" src="https://github.com/user-attachments/assets/7d13d153-69ab-4da0-84a8-76c9a536b67c" />


**Question 2**
---

<img width="1235" height="758" alt="image" src="https://github.com/user-attachments/assets/613d1be6-fa4b-4754-b1b6-da98c20945a0" />
<img width="1158" height="728" alt="image" src="https://github.com/user-attachments/assets/47877246-0784-45ae-96a5-9a53114dc4be" />

```sql
select o.ord_no , o.ord_date, o.purch_amt , c.cust_name as 'Customer Name', c.grade,s.name as 'Salesman',s.commission
from orders o
join customer c on o.customer_id = c.customer_id 
join salesman s on o.salesman_id = s.salesman_id
```

**Output:**

<img width="1237" height="781" alt="image" src="https://github.com/user-attachments/assets/38285b1d-3a4c-47ca-9247-6b4c01527457" />


**Question 3**
---
<img width="1265" height="792" alt="image" src="https://github.com/user-attachments/assets/8a524db8-df19-4cae-80ad-8eeca8338544" />


```sql
select o.ord_no, o.purch_amt,c.cust_name,c.city
from orders o
join customer c on o.customer_id = c.customer_id
where o.purch_amt between 500 and 2000
```

**Output:**
<img width="1248" height="497" alt="image" src="https://github.com/user-attachments/assets/22966fa2-a1e8-4967-b679-8a8579d16fe1" />


**Question 4**
---
<img width="1247" height="466" alt="image" src="https://github.com/user-attachments/assets/abd224f5-a657-4b47-839a-a1f75964eb44" />


```sql
select c.cust_name, c.city,o.ord_no,o.ord_date,o.purch_amt
from customer c
left join orders o on c.customer_id = o.customer_id
where city = 'London'
```

**Output:**

<img width="1246" height="502" alt="image" src="https://github.com/user-attachments/assets/d6e6bfba-234d-4d05-bf3a-44c9ab0daa19" />


**Question 5**
---
<img width="1250" height="789" alt="image" src="https://github.com/user-attachments/assets/22bb0089-d6f9-4ed6-a03a-8caf9ae36bb5" />


```sql
select p.first_name,p.last_name
from patients p
inner join surgeries s on p.patient_id = s.patient_id
where s.surgery_date between '2024-01-01' and '2024-01-31'
```

**Output:**

<img width="1205" height="392" alt="image" src="https://github.com/user-attachments/assets/687ee795-aee3-4fb9-ba1a-f818127855ed" />


**Question 6**
---
<img width="1223" height="566" alt="image" src="https://github.com/user-attachments/assets/7ded739a-5e5e-4db7-b1e4-46e5874eff8f" />


```sql
select s.name as 'salesman_name', c.cust_name as 'customer_name'
from Salesman s
left join customer c on s.salesman_id = c.salesman_id
```

**Output:**

<img width="1195" height="864" alt="image" src="https://github.com/user-attachments/assets/2e3ac406-15a1-4e62-9ac1-34cc5a016de3" />


**Question 7**
---
<img width="1190" height="857" alt="image" src="https://github.com/user-attachments/assets/39a1ad54-0d47-4aa8-a822-85e0843b4596" />


```sql
select c.cust_name as 'Customer Name' , c.city,s.name as 'Salesman',s.city,s.commission
from customer c
join salesman s on c.salesman_id = s.salesman_id
where s.city <> c.city and commission > 0.12
```

**Output:**

<img width="1252" height="652" alt="image" src="https://github.com/user-attachments/assets/e40e0137-7c7c-4cfb-b917-35d7ff49ec26" />


**Question 8**
---
<img width="1232" height="846" alt="image" src="https://github.com/user-attachments/assets/0de08a4b-4fe4-4924-9780-b3c666de0c25" />


```sql
select c.cust_name,c.city,c.grade,s.name as 'Salesman',s.city
from customer c
join salesman s on c.salesman_id = s.salesman_id
order by customer_id ASC
```

**Output:**

<img width="1243" height="582" alt="image" src="https://github.com/user-attachments/assets/7ffbdf33-87dd-4b08-9d30-cfc3c5984b93" />


**Question 9**
---
<img width="1228" height="846" alt="image" src="https://github.com/user-attachments/assets/a3b53390-a56c-4b73-8e4e-2df38b7e4fb9" />


```sql
select c.cust_name,c.city,c.grade,s.name as 'Salesman',s.city
from customer c
join salesman s on c.salesman_id = s.salesman_id
where grade < 300
order by customer_id ASC
```

**Output:**
<img width="1252" height="798" alt="image" src="https://github.com/user-attachments/assets/d7e4e71a-e388-4ead-9cb1-07dc396d5e18" />


**Question 10**
---
<img width="1217" height="807" alt="image" src="https://github.com/user-attachments/assets/2a376f66-ddbf-47d6-8f7b-eac279bab07b" />


```sql
select p.first_name as 'patient_name', d.specialization as 'Doctor_speciali'
from patients p
inner join doctors d on p.doctor_id = d.doctor_id
where p.admission_date between '2024-01-01' and '2024-01-31'
```

**Output:**
<img width="1142" height="398" alt="image" src="https://github.com/user-attachments/assets/3147c15e-0822-45ce-87e1-0455c8db8d82" />

**Module Examination**

<img width="1205" height="86" alt="image" src="https://github.com/user-attachments/assets/e35b9610-b301-4db8-bdb7-4da430d2bc96" />


## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
