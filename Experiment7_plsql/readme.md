# Experiment 7: PL/SQL – Variables, Control Structures and Loops

## AIM
To write and execute simple PL/SQL programs using variables, loops, and conditional statements.


## THEORY

PL/SQL, which stands for Procedural Language extensions to the Structured Query Language (SQL). It is a combination of SQL along with the procedural features of programming languages.

**Syntax:**
```sql
DECLARE 
   <declarations section> 
BEGIN 
   <executable command(s)>
EXCEPTION 
   <exception handling> 
END;
```

### Basic Components of PL/SQL Block:
- DECLARE: Section to declare variables and constants.
- BEGIN: The execution section that contains PL/SQL statements.
- EXCEPTION: Handles errors or exceptions that occur in the program.
- END: Marks the end of the PL/SQL block.

# PL/SQL Programs – Steps and Expected Output

## 1. Write a PL/SQL program to find the Greatest of Two Numbers

### Steps:
- Declare two numeric variables and initialize them.
- Use an `IF` statement to compare the values.
- Display the greater number using `DBMS_OUTPUT.PUT_LINE`.

**Expected Output:**  
Greater number is: 80

## Program 
```
DECLARE
    num1 NUMBER := 80;
    num2 NUMBER := 65;
BEGIN
    IF num1 > num2 THEN
        DBMS_OUTPUT.PUT_LINE('Greater number is: ' || num1);
    ELSIF num2 > num1 THEN
        DBMS_OUTPUT.PUT_LINE('Greater number is: ' || num2);
    ELSE
        DBMS_OUTPUT.PUT_LINE('Both numbers are equal: ' || num1);
    END IF;
END;
```
## OUTPUT
![image](https://github.com/user-attachments/assets/98d1749f-1863-4668-a7d7-fa18b7d3917d)


---

## 2. Write a PL/SQL program to Calculate Sum of First N Natural Numbers

### Steps:
- Declare a variable `n` and assign a value (e.g., 10).
- Initialize a `sum` variable to 0.
- Use a `WHILE` loop to iterate from 1 to `n`, adding each number to the sum.
- Display the result using `DBMS_OUTPUT.PUT_LINE`.

**Expected Output:**  
Sum of first 10 natural numbers is: 55

## PROGRAM
```
DECLARE
    n NUMBER := 10;
    sum NUMBER := 0;
    i NUMBER := 1;
BEGIN
    WHILE i <= n LOOP
        sum := sum + i;
        i := i + 1;
    END LOOP;

    DBMS_OUTPUT.PUT_LINE('Sum of first ' || n || ' natural numbers is: ' || sum);
END;
```
## OUTPUT
![image](https://github.com/user-attachments/assets/938b698d-f6f3-4087-bc3e-61634e883935)

---

## 3. Write a PL/SQL program to generate Fibonacci series

### Steps:
- Declare the variable `n` to indicate how many terms to generate.
- Initialize the first two Fibonacci numbers (0 and 1).
- Use a loop to generate the next terms using the formula `c = a + b`.
- Print each term in the series.

**Expected Output:**  
n = 7  
Fibonacci sequence: 0, 1, 1, 2, 3, 5, 8

## PROGRAM
```
DECLARE
    n NUMBER := 7;         -- Number of terms to generate
    a NUMBER := 0;         -- First term
    b NUMBER := 1;         -- Second term
    c NUMBER;              -- Variable for next term
    i NUMBER := 3;         -- Loop counter starting from 3 (first two terms already known)
BEGIN
    DBMS_OUTPUT.PUT_LINE('Fibonacci sequence:');
    DBMS_OUTPUT.PUT_LINE(a);
    DBMS_OUTPUT.PUT_LINE(b);

    WHILE i <= n LOOP
        c := a + b;
        DBMS_OUTPUT.PUT_LINE(c);
        a := b;
        b := c;
        i := i + 1;
    END LOOP;
END;
```

## OUTPUT

![image](https://github.com/user-attachments/assets/b8dc5e64-e1b3-4c51-946e-fd1ecd71e17c)

---



## 4. Write a PL/SQL Program to display the number in Reverse Order

### Steps:
- Declare a variable `n` and assign a value (e.g., 1535).
- Use a loop to extract each digit using modulo and reverse the number.
- Display the reversed number.

**Expected Output:**  
n = 1535  
Reversed number is 5351

## PROGRAM
```
DECLARE
    n NUMBER := 1535;
    reversed NUMBER := 0;
    digit NUMBER;
    original NUMBER := 1535;
BEGIN
    WHILE n > 0 LOOP
        digit := MOD(n, 10);           -- Get the last digit
        reversed := (reversed * 10) + digit;  -- Append digit to reversed number
        n := TRUNC(n / 10);            -- Remove the last digit
    END LOOP;

    DBMS_OUTPUT.PUT_LINE('n = ' || original);
    DBMS_OUTPUT.PUT_LINE('Reversed number is ' || reversed);
END;

```
## OUTPUT

![image](https://github.com/user-attachments/assets/206e669b-4045-4260-806b-6197cedd5b5b)


---

## 5. Write a PL/SQL program to find the largest of three numbers

### Steps:
- Declare three numeric variables `a`, `b`, and `c`.
- Use nested `IF-ELSIF-ELSE` conditions to find the largest among the three.
- Display the largest number.

**Expected Output:**  
a = 10, b = 9, c = 15  
Largest of three number is 15

## PROGRAM
```
DECLARE
    a NUMBER := 10;
    b NUMBER := 9;
    c NUMBER := 15;
BEGIN
    IF a >= b AND a >= c THEN
        DBMS_OUTPUT.PUT_LINE('a = ' || a || ', b = ' || b || ', c = ' || c);
        DBMS_OUTPUT.PUT_LINE('Largest of three number is ' || a);
    ELSIF b >= a AND b >= c THEN
        DBMS_OUTPUT.PUT_LINE('a = ' || a || ', b = ' || b || ', c = ' || c);
        DBMS_OUTPUT.PUT_LINE('Largest of three number is ' || b);
    ELSE
        DBMS_OUTPUT.PUT_LINE('a = ' || a || ', b = ' || b || ', c = ' || c);
        DBMS_OUTPUT.PUT_LINE('Largest of three number is ' || c);
    END IF;
END;
/

```

## OUTPUT

![image](https://github.com/user-attachments/assets/449c5ebf-1263-4d67-b7f8-8c7bafb6fcd5)


## RESULT
Thus, the PL/SQL programs using variables, conditionals, and loops were executed successfully.
