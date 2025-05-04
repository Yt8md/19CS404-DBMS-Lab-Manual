**Question 1**
--
![image](https://github.com/user-attachments/assets/459b965f-8309-4f53-bbed-736180520a8c)


```sql
update employees set email = 'not available', commission_pct = 0.55 where department_id = 110;
```

**Output:**

![image](https://github.com/user-attachments/assets/fac230fc-741f-4d87-bf72-d9b3d722406e)


**Question 2**
---
![image](https://github.com/user-attachments/assets/8ef405a4-2071-4bbe-a6d5-1005dcd6f5af)


```sql
update employees set email = 'Unavailable';
```

**Output:**

![image](https://github.com/user-attachments/assets/5087a264-0c1d-475e-8fc1-c44575998313)


**Question 3**
---
![image](https://github.com/user-attachments/assets/a703c84a-efed-4f5d-96db-fd11ce0ea821)


```sql
update employees set salary = 2*salary where department_id = 20 and job_id like '%man%';
```

**Output:**

![image](https://github.com/user-attachments/assets/71ace666-9a59-436c-a6a4-8cb50f07e406)


**Question 4**
---
![image](https://github.com/user-attachments/assets/ca40c043-4b78-4b61-925c-9bede4eac51e)


```sql
update products set category = 'Household' where product_name like '%Detergent%';
```

**Output:**

![image](https://github.com/user-attachments/assets/b41b44ca-9fc1-440d-99ed-350309a55c7f)


**Question 5**
---
![image](https://github.com/user-attachments/assets/bd58593a-88f8-422b-af5f-4931a60e41f0)


```sql
update products set reorder_lvl = reorder_lvl*0.7 where cost_price>50 and quantity <100;
```

**Output:**

![image](https://github.com/user-attachments/assets/4482e0aa-3df2-4592-8b30-847987c45ee5)


**Question 6**
---
![image](https://github.com/user-attachments/assets/700bde10-d912-4b7e-b231-89d56f4ed19a)


```sql
delete from Doctors where specialization = 'Cardiology';
```

**Output:**

![image](https://github.com/user-attachments/assets/27b80fb9-6855-44f3-be48-b73c2b2d1f2d)


**Question 7**
---
![image](https://github.com/user-attachments/assets/bce51b18-f394-452c-8f15-1592aadf164d)


```sql
delete from customer where opening_amt between 4000 and 6000;
```

**Output:**

![image](https://github.com/user-attachments/assets/d004fda7-2c32-4c55-942d-575cfc0be6f6)


**Question 8**
---
![image](https://github.com/user-attachments/assets/33107399-117b-480b-85e1-e24cd5806401)


```sql
delete from surgeries where surgery_id = 3 or surgery_id = 4;
```

**Output:**

![image](https://github.com/user-attachments/assets/003b0f53-2332-46ae-bf21-f520216a06e7)


**Question 9**
---
![image](https://github.com/user-attachments/assets/98488559-f6b4-4a65-aea4-87532ed94e59)


```sql
delete from doctors where last_name is null;
```

**Output:**

![image](https://github.com/user-attachments/assets/765f4da0-a1a3-4159-9987-f9cee8df6ff6)


**Question 10**
---
![image](https://github.com/user-attachments/assets/164fc043-ffd0-40c7-938c-d4b839a600bf)


```sql
delete from Customer where grade!=3; 
```

**Output:**

![image](https://github.com/user-attachments/assets/4136c382-8a5f-40d4-994f-54c3f68d21a2)

