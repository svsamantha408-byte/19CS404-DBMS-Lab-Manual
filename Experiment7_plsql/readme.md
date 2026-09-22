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

<h3>Program:</h3>

```sql
DECLARE
    num1 NUMBER := 80;  -- First number
    num2 NUMBER := 50;  -- Second number
BEGIN
    IF num1 > num2 THEN
        DBMS_OUTPUT.PUT_LINE('Greater number is: ' || num1);
    ELSE
        DBMS_OUTPUT.PUT_LINE('Greater number is: ' || num2);
    END IF;
END;
```

<h3>Output</h3>


<img width="734" height="118" alt="image" src="https://github.com/user-attachments/assets/71d6a2bf-3337-48c4-9e10-fc5df44126e8" />


---

## 2. Write a PL/SQL program to Calculate Sum of First N Natural Numbers

### Steps:
- Declare a variable `n` and assign a value (e.g., 10).
- Initialize a `sum` variable to 0.
- Use a `WHILE` loop to iterate from 1 to `n`, adding each number to the sum.
- Display the result using `DBMS_OUTPUT.PUT_LINE`.

**Expected Output:**  
Sum of first 10 natural numbers is: 55


<h3>Program:</h3>

```sql
SET SERVEROUTPUT ON;

DECLARE
    n NUMBER := 10;       -- Number up to which sum is calculated
    i NUMBER := 1;        -- Loop counter
    total_sum NUMBER := 0; -- To store the sum
BEGIN
    WHILE i <= n LOOP
        total_sum := total_sum + i;
        i := i + 1;
    END LOOP;
    DBMS_OUTPUT.PUT_LINE('Sum of first ' || n || ' natural numbers is: ' || total_sum);
END;
```
<h3>Output:</h3>

<img width="734" height="117" alt="image" src="https://github.com/user-attachments/assets/c736ec95-df11-4e3b-b3f7-a433ce2bfcc0" />


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

<h3>Program:</h3>


```sql
DECLARE
    n NUMBER := 7;        -- Number of terms
    a NUMBER := 0;        -- First term
    b NUMBER := 1;        -- Second term
    c NUMBER;             -- Next term
    i NUMBER := 1;
BEGIN
    DBMS_OUTPUT.PUT_LINE('Fibonacci sequence:');

    -- Print first two terms
    DBMS_OUTPUT.PUT(a || ', ' || b);

    -- Loop to generate remaining terms
    FOR i IN 3..n LOOP
        c := a + b;
        DBMS_OUTPUT.PUT(', ' || c);
        a := b;
        b := c;
    END LOOP;

    DBMS_OUTPUT.NEW_LINE;
END;
/
```
<h3>Output</h3>



<img width="731" height="122" alt="image" src="https://github.com/user-attachments/assets/8fa452b5-f234-4b54-bd0f-72fff0a2ab4b" />

---

## 4. Write a PL/SQL Program to display the number in Reverse Order

### Steps:
- Declare a variable `n` and assign a value (e.g., 1535).
- Use a loop to extract each digit using modulo and reverse the number.
- Display the reversed number.

**Expected Output:**  
n = 1535  
Reversed number is 5351

<h3>Program:</h3>

```sql
DECLARE
    n NUMBER := 1535;     -- Original number
    rev NUMBER := 0;      -- Reversed number
    rem NUMBER;           -- Remainder (digit)
BEGIN
    WHILE n > 0 LOOP
        rem := MOD(n, 10);        -- Get last digit
        rev := rev * 10 + rem;    -- Build reversed number
        n := TRUNC(n / 10);       -- Remove last digit
    END LOOP;

    DBMS_OUTPUT.PUT_LINE('Reversed number is ' || rev);
END;
/
```
<h3>Output</h3>

<img width="739" height="91" alt="image" src="https://github.com/user-attachments/assets/2ac97172-00ec-43dc-a09f-0142e490bb2c" />


---

## 5. Write a PL/SQL program to find the largest of three numbers

### Steps:
- Declare three numeric variables `a`, `b`, and `c`.
- Use nested `IF-ELSIF-ELSE` conditions to find the largest among the three.
- Display the largest number.

**Expected Output:**  
a = 10, b = 9, c = 15  
Largest of three number is 15

<h3>Program</h3>

```sql
SET SERVEROUTPUT ON;

DECLARE
    a NUMBER := 10;
    b NUMBER := 9;
    c NUMBER := 15;
    largest NUMBER;
BEGIN
    IF a >= b AND a >= c THEN
        largest := a;
    ELSIF b >= a AND b >= c THEN
        largest := b;
    ELSE
        largest := c;
    END IF;
    DBMS_OUTPUT.PUT_LINE('a = ' || a || ', b = ' || b || ', c = ' || c);
    DBMS_OUTPUT.PUT_LINE('Largest of three number is ' || largest);
END;
```
<h3>Output</h3>


<img width="730" height="141" alt="image" src="https://github.com/user-attachments/assets/6aef402e-9773-4214-85d9-89f5ae200977" />


## RESULT
Thus, the PL/SQL programs using variables, conditionals, and loops were executed successfully.
