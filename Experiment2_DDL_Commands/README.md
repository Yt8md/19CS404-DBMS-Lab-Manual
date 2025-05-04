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

![image](https://github.com/user-attachments/assets/4c7057ed-ecff-4536-a358-d465938b94c1)


```sql
insert into Customers(ID,NAME,AGE,ADDRESS,SALARY)values(1,'Ramesh',32,'Ahmedabad',2000);
insert into Customers(ID,NAME,AGE,ADDRESS,SALARY)values(2,'Khilan',25,'Delhi',1500);
insert into Customers(ID,NAME,AGE,ADDRESS,SALARY)values(3,'Kaushik',23,'Kota',2000);
```

**Output:**

![image](https://github.com/user-attachments/assets/71458be3-2b83-4d22-9f44-f3d20656adb1)


**Question 2**
---
![image](https://github.com/user-attachments/assets/8136a9d4-0519-446a-b73a-636b1aab1b77)


```sql
alter table Student_details add State TEXT;
```

**Output:**

![image](https://github.com/user-attachments/assets/45252bff-ff72-45d0-8562-604c1a82721e)


**Question 3**
---
![image](https://github.com/user-attachments/assets/c6b51ddb-ab98-43e5-a6ae-5b56ae6dda67)


```sql
create table products(product_id int primary key,
product_name TEXT not null,
list_price decimal(10,2) not null,
discount decimal(10,2) not null default '0',
check(list_price>=discount),
check(discount>=0),
check(list_price>=0)
);
```

**Output:**

![image](https://github.com/user-attachments/assets/495d8513-8922-4d31-970f-441fd4d2cd1e)


**Question 4**
---
![image](https://github.com/user-attachments/assets/e0a97859-6c46-447b-92e8-360c447ee6c6)


```sql
create table Invoices(InvoiceID int primary key,
InvoiceDate date,
DueDate date,
Amount real,
check(Duedate>=InvoiceDate),
check(Amount>=0)
);
```

**Output:**

![image](https://github.com/user-attachments/assets/8659cded-7b2e-43b3-8849-cf5875174bc3)


**Question 5**
---

![image](https://github.com/user-attachments/assets/7d5e863c-cdcc-4bd5-b0e0-c4700d84b601)


```sql
insert into Products(ProductID,ProductName,Price,stock)select ProductID,ProductName,Price,Stock from Discontinued_products;
```

**Output:**

![image](https://github.com/user-attachments/assets/d7ac33e7-4c11-45da-b713-06bde3c02503)


**Question 6**
---
![image](https://github.com/user-attachments/assets/5e632b4c-e878-4663-b0a5-c274b59e512c)


```sql
create table Employees(EmployeeID INTEGER,
FirstName TEXT,
LastName TEXT,
HireDate DATE
);
```

**Output:**

![image](https://github.com/user-attachments/assets/958aba7d-a07c-4d1e-8302-0a37c7499ddf)


**Question 7**
---
![image](https://github.com/user-attachments/assets/2998a938-2a3f-42cc-8ab5-2e4c0bbec4e0)


```sql
alter table Companies add designation varchar(50);
alter table Companies add net_salary number;
alter table Companies add dob date;
```

**Output:**

![image](https://github.com/user-attachments/assets/4c27fa8b-2d81-4785-b583-2a1d7fdf5636)


**Question 8**
---
![image](https://github.com/user-attachments/assets/19e88c56-f245-4099-8880-8b09d4d28ae4)


```sql
insert into Books(ISBN,Title,Author,Publisher,Year)values('978-1234567890','Data Science Essentials','Jane Doe','TechBooks',2024);
```

**Output:**

![image](https://github.com/user-attachments/assets/09ddeee6-f6e0-43f0-af14-216bef8f649a)


**Question 9**
---
![image](https://github.com/user-attachments/assets/e0aebff7-9ebc-4493-9bbb-d68b8cc74171)


```sql
create table Shipments(ShipmentID int primary key,
ShipmentDate date,
SupplierID int,
OrderID int,
foreign key(SupplierID) references Suppliers(SupplierID),
foreign key(OrderID) references Orders(OrderID)
);
```

**Output:**

![image](https://github.com/user-attachments/assets/76eb159a-5086-4817-83d1-2851b433e367)


**Question 10**
---
![image](https://github.com/user-attachments/assets/855c9d3d-f474-4e29-8429-25e0d78e1f5e)


```sql
create table item (item_id text primary key,
item_desc text not null,
rate int not null,
icom_id text,
foreign key(icom_id) references company(com_id) on update set null on delete set null,
check(length(icom_id)=4)
);
```

**Output:**

![image](https://github.com/user-attachments/assets/79dec9f9-d04b-463e-9b84-c73191497ef9)


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
