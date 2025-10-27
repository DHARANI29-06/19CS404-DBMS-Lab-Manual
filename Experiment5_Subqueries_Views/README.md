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
<img width="1222" height="748" alt="image" src="https://github.com/user-attachments/assets/75abd6cc-6af6-4b71-be68-f029ed362c8f" />


```sql
select ord_no, purch_amt, ord_date, customer_id ,salesman_id
from orders
where salesman_id = (
select salesman_id
from salesman
where name = 'Paul Adam');
```

**Output:**

<img width="1261" height="393" alt="image" src="https://github.com/user-attachments/assets/3258cb6a-1411-4811-86af-abd2bbdc854a" />


**Question 2**
---
<img width="1030" height="628" alt="image" src="https://github.com/user-attachments/assets/f32ec78e-c9fa-4a0d-8f4d-a73929e3449b" />


```sql
select * from CUSTOMERS
where ADDRESS = 'Delhi';
```

**Output:**

<img width="1237" height="360" alt="image" src="https://github.com/user-attachments/assets/5e824484-3f2c-4315-9faf-3d4dbda8e17d" />


**Question 3**
---
<img width="1232" height="797" alt="image" src="https://github.com/user-attachments/assets/4b6a2498-3cbf-4ddf-a974-0540b139b1c4" />


```sql
select ord_no, purch_amt, ord_date,salesman_id
from orders
where salesman_id = (
select salesman_id
from salesman
where commission = (select MAX(commission) 
from salesman 
));
```

**Output:**

<img width="1271" height="470" alt="image" src="https://github.com/user-attachments/assets/51dae900-b52e-4226-9a17-71ee7d1a3826" />

**Question 4**
---
<img width="1234" height="819" alt="image" src="https://github.com/user-attachments/assets/8182b799-cbcd-49dd-ab16-73c6bf542166" />


```sql
select ord_no, purch_amt, ord_date, customer_id ,salesman_id
from orders
where salesman_id in (
select salesman_id
from salesman
where city = 'New York');
```

**Output:**

<img width="1236" height="482" alt="image" src="https://github.com/user-attachments/assets/29bf0f0e-88f4-4fde-91df-bf5d3c99eb21" />


**Question 5**
---
<img width="1215" height="630" alt="image" src="https://github.com/user-attachments/assets/646cb35a-026e-477c-b03a-4b7abaa8ff45" />


```sql
select ord_no, purch_amt, ord_date, customer_id, salesman_id
from orders
where purch_amt > (
select AVG(purch_amt)
from orders
where ord_date = '2012-10-10');
```

**Output:**

<img width="1240" height="458" alt="image" src="https://github.com/user-attachments/assets/5316614d-1bd2-4983-b7ba-5277354706e8" />


**Question 6**
---
<img width="1086" height="622" alt="image" src="https://github.com/user-attachments/assets/c981390b-2276-4280-94a8-bf6a2f6923a1" />


```sql
select * from CUSTOMERS
where ADDRESS = 'Delhi'
and AGE < 30
group by ID;
```

**Output:**

<img width="1233" height="364" alt="image" src="https://github.com/user-attachments/assets/3d167b5d-1c29-4d0c-b031-d85c7dad2fb4" />


**Question 7**
---
<img width="1179" height="657" alt="image" src="https://github.com/user-attachments/assets/61e02579-0102-4c72-b413-799296fe6ebb" />


```sql
select * from Employee
where age < (
select AVG(age)
from Employee
where income > 250000);
```

**Output:**

<img width="1255" height="528" alt="image" src="https://github.com/user-attachments/assets/31782e69-f042-4889-9864-8c13550733c5" />


**Question 8**
---
<img width="999" height="652" alt="image" src="https://github.com/user-attachments/assets/b4ce9dc5-6e47-4523-97b9-23edfac27713" />


```sql
select * from CUSTOMERS
where salary > 4500;
```

**Output:**
<img width="1256" height="431" alt="image" src="https://github.com/user-attachments/assets/3e2b8f1a-0854-423d-8512-7df2502cac55" />


**Question 9**
---
<img width="1131" height="535" alt="image" src="https://github.com/user-attachments/assets/42571b4d-a360-4fff-8fe3-23cfd8f6de44" />


```sql
select name,city
from customer
where city in (
select city
from customer
where id in (3,7));
```

**Output:**
<img width="1211" height="455" alt="image" src="https://github.com/user-attachments/assets/8479da43-cb67-4839-8940-7341b8801c66" />



**Question 10**
---
<img width="1256" height="610" alt="image" src="https://github.com/user-attachments/assets/40617561-3ec7-42ac-9832-330d0df09f75" />

```sql
select *
from GRADES g
where grade = (
select MIN(grade)
from GRADES
where subject = g.subject);
```

**Output:**
<img width="1252" height="455" alt="image" src="https://github.com/user-attachments/assets/f27ee9b0-9de3-4310-9f0d-8b6ea7f0793c" />


**Module Examination**
<img width="1336" height="77" alt="image" src="https://github.com/user-attachments/assets/58199ad1-3684-428c-9802-ef4dda616303" />

## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
