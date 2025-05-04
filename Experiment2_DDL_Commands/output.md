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

## Result:
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
![Output10](output.png)
