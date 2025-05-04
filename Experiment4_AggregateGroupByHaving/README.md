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
![image](https://github.com/user-attachments/assets/79472add-42fd-427a-a69e-e36b6cf9415a)


```sql
select PatientID, count(*) as AvgMedications from MedicalRecords group by PatientID;
```

**Output:**

![image](https://github.com/user-attachments/assets/3ab6aef1-6f40-4984-8e56-187ee947497c)


**Question 2**
---
![image](https://github.com/user-attachments/assets/af2ab57b-17d2-43cf-9dca-2ff0a9964832)


```sql
select Specialty,count(*) as TotalDoctor from Doctors group by specialty;
```

**Output:**

![image](https://github.com/user-attachments/assets/5133f1fc-3397-4710-be3d-1a5b63ac04b2)


**Question 3**
---
![image](https://github.com/user-attachments/assets/69f836d9-8216-4980-9b76-ab771877a496)


```sql
select InsuranceCompany,count(*) as TotalPatients from Insurance group by InsuranceCompany;
```

**Output:**

![image](https://github.com/user-attachments/assets/ba9f0663-9545-40c0-a63e-a849eda57417)


**Question 4**
---
![image](https://github.com/user-attachments/assets/97b12e74-3380-4faa-8626-ea91b761b703)


```sql
select count(distinct age) as COUNT from employee;
```

**Output:**

![image](https://github.com/user-attachments/assets/396f45af-377c-4b8e-92ab-47c3d8eca1a2)


**Question 5**
---
![image](https://github.com/user-attachments/assets/b2e024fb-c931-435a-a731-f26fcb986632)


```sql
select count(distinct salesman_id) as COUNT from orders;
```

**Output:**

![image](https://github.com/user-attachments/assets/c62f897a-6ab9-424a-add5-5b6219a9e60f)


**Question 6**
---
![image](https://github.com/user-attachments/assets/473c06d4-04aa-4ced-9464-4e081d4824cf)


```sql
select name as Employee_Name,min(age) as Age from employee;

```

**Output:**

![image](https://github.com/user-attachments/assets/2aa90160-1a9f-48d0-b1aa-e221be1b1c99)


**Question 7**
---
![image](https://github.com/user-attachments/assets/66bc8d14-29a3-4b44-8430-d25b8c15a777)


```sql
select count(*) as COUNT from customer where city != 'Noida';
```

**Output:**

![image](https://github.com/user-attachments/assets/bcd50289-48df-45ab-b2d1-c14c981526cf)


**Question 8**
---
![image](https://github.com/user-attachments/assets/15eaa93f-2263-40b6-bd81-7488b1f2a65c)

```sql
SELECT age, MAX(income) AS 'MAX(income)'
FROM employee
GROUP BY age
HAVING MAX(income) > 2000000;
```

**Output:**

![image](https://github.com/user-attachments/assets/f37a3da9-6e90-419f-befc-d0eeeb1fa312)

**Question 9**
---
![image](https://github.com/user-attachments/assets/5f4fc90d-a96a-489e-976d-86d240c359fc)

```sql
select city,sum(income) as Income from employee
group by city
having Income>200000;
```

**Output:**

![image](https://github.com/user-attachments/assets/9bdda9fe-918b-4f90-9221-d0bcd3a40066)

**Question 10**
---
![image](https://github.com/user-attachments/assets/e92a06c7-9d2e-4bda-b18b-fcb63e84160f)


```sql
select jdate,AVG(workhour) from employee1
group by jdate
having avg(workhour)<10
```

**Output:**

![image](https://github.com/user-attachments/assets/b09503c6-fb20-4b57-a5f9-7d64e1c7f9af)


## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
