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
![image](https://github.com/user-attachments/assets/5ca0404a-4dff-492e-9d42-ea7c88687565)


```sql
SELECT student_name, grade FROM GRADES WHERE (subject,grade) IN (SELECT subject,MIN(grade) FROM GRADES GROUP BY subject);
```

**Output:**

![image](https://github.com/user-attachments/assets/b3286f95-4ece-40dd-8e70-da35538f8dda)


**Question 2**
---
![image](https://github.com/user-attachments/assets/01be9094-525b-4f04-91a8-43d0c70c3659)


```sql
SELECT * FROM GRADES WHERE(subject,grade) IN (SELECT subject,MAX(grade) FROM GRADES GROUP BY subject);
```

**Output:**

![image](https://github.com/user-attachments/assets/0285e90c-e1e6-4fde-84ba-7bf9f296ce73)


**Question 3**
---
![image](https://github.com/user-attachments/assets/64b24505-3d55-4b58-a96d-840e749bd2f3)


```sql
select ID,NAME,AGE,ADDRESS,SALARY FROM customers where SALARY >4500;
```

**Output:**

![image](https://github.com/user-attachments/assets/701d927d-ff4e-44a7-bd31-5cb9cebc5e79)


**Question 4**
---
![image](https://github.com/user-attachments/assets/9f6538f1-9671-47da-a3c8-5e95b321962f)


```sql
SELECT name
FROM customer
WHERE phone IN (
    SELECT phone
    FROM customer
    GROUP BY phone
    HAVING COUNT(*) = 1
);

```

**Output:**

![image](https://github.com/user-attachments/assets/4ed7fdc3-421b-471f-8c8f-6ac67f72a5c3)


**Question 5**
---
![image](https://github.com/user-attachments/assets/19ada03e-81b0-43f9-aa25-0d9bb17e03ad)


```sql
SELECT * FROM CUSTOMERS WHERE SALARY < 2500;

```

**Output:**

![image](https://github.com/user-attachments/assets/7f708dd7-c5a1-431c-946d-40b9567fd5cd)


**Question 6**
---
![image](https://github.com/user-attachments/assets/20938f98-4f5a-4d9c-a4bb-95309e38b0e3)


```sql
SELECT * FROM CUSTOMERS WHERE AGE < 30;

```

**Output:**

![image](https://github.com/user-attachments/assets/6a1e03cb-fcd8-4f77-b16c-e6961ab574ad)


**Question 7**
---
![image](https://github.com/user-attachments/assets/24329b22-1175-485f-97e2-97f81d12af64)


```sql
SELECT s.salesman_id, s.name
FROM salesman s
JOIN customer c ON s.salesman_id = c.salesman_id
GROUP BY s.salesman_id, s.name
HAVING COUNT(c.customer_id) > 1;

```

**Output:**

![image](https://github.com/user-attachments/assets/167c19d5-9d29-402f-905e-a995d2969f9a)


**Question 8**
---
![image](https://github.com/user-attachments/assets/460c4f38-8cb7-438f-b03c-c518db12fb49)


```sql
select * from CUSTOMERS WHERE SALARY > 1500;
```

**Output:**

![image](https://github.com/user-attachments/assets/87e849b6-af8b-4143-b2c9-9ef82cf060fd)


**Question 9**
---
![image](https://github.com/user-attachments/assets/4d9e52f7-9b13-4139-a337-bd1d068d5f49)


```sql
-- 
SELECT name, city
FROM customer
WHERE city IN (
  SELECT city
  FROM customer
  WHERE id IN (3, 7)
);

```

**Output:**

![image](https://github.com/user-attachments/assets/169bfe00-632c-4a08-9997-31a1df67e41f)


**Question 10**
---
![image](https://github.com/user-attachments/assets/729d194c-b70f-4507-8fb5-45018b982917)


```sql
SELECT o.ord_no, o.purch_amt, o.ord_date, o.salesman_id
FROM orders o
JOIN salesman s ON o.salesman_id = s.salesman_id
WHERE s.commission = (
  SELECT MAX(commission)
  FROM salesman
);

```

**Output:**

![image](https://github.com/user-attachments/assets/9e1c1eb9-b00d-440b-a2da-d6a4a7459da0)





## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
