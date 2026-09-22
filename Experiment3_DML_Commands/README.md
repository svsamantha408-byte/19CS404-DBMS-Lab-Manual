# Experiment 3: DML Commands

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**
--
<img width="1050" height="490" alt="image" src="https://github.com/user-attachments/assets/a7574cf5-136b-4d14-9e3f-640b572a34c0" />


```sql
update suppliers
set address='58 Lakeview, Magnolia'
where supplier_id=5;
```

**Output:**

<img width="1149" height="370" alt="image" src="https://github.com/user-attachments/assets/87f9c461-3cbe-45ec-9d17-1ad400aeb5ad" />


**Question 2**
---
<img width="1193" height="561" alt="image" src="https://github.com/user-attachments/assets/d3b09906-06f5-4d12-a946-312f1a22302a" />


```sql
SELECT *
FROM orders
WHERE NOT (
        ord_date = '2012-08-17'
        OR (customer_id > 3005 AND purch_amt < 1000)
      );
```

**Output:**

<img width="1150" height="783" alt="image" src="https://github.com/user-attachments/assets/37385fef-e48a-4744-aa6e-4d736c038905" />


**Question 3**
---
<img width="1198" height="495" alt="image" src="https://github.com/user-attachments/assets/70b19189-759d-473d-b4f8-06983d9f72fa" />


```sql
delete from customer
where CUST_CITY <> 'New York' and OUTSTANDING_AMT>5000;
```

**Output:**

<img width="1152" height="573" alt="image" src="https://github.com/user-attachments/assets/46a10683-4ecc-4447-be44-529ed109c9fb" />


**Question 4**
---
<img width="1194" height="521" alt="image" src="https://github.com/user-attachments/assets/dff8dd28-de40-4259-8106-efc40ab4a43e" />


```sql
UPDATE products
SET reorder_lvl = 20
WHERE quantity < 10
AND category = 'Snacks';
```

**Output:**

<img width="1148" height="548" alt="image" src="https://github.com/user-attachments/assets/1a5d109a-4518-4f73-bbac-cebf903af577" />


**Question 5**
---
<img width="1192" height="590" alt="image" src="https://github.com/user-attachments/assets/d5104730-5469-435b-b63d-5ad952d0d424" />


```sql
DELETE FROM customer
WHERE WORKING_AREA = 'New York';
```

**Output:**

<img width="1152" height="763" alt="image" src="https://github.com/user-attachments/assets/89c00f45-380a-48af-9a90-da9e35f8ed57" />


**Question 6**
---
<img width="1196" height="735" alt="image" src="https://github.com/user-attachments/assets/8583299e-ddb9-4b33-a7c6-dcf6bcde17d5" />


```sql
UPDATE employees
SET salary = salary + 500,
    email = 'updated'
WHERE job_id = 'SA_REP'
  AND commission_pct > 0.15;
```

**Output:**

<img width="1145" height="495" alt="image" src="https://github.com/user-attachments/assets/0b350360-a75c-4b7b-a600-9967aa21f296" />

**Question 7**
---
<img width="896" height="427" alt="image" src="https://github.com/user-attachments/assets/51688f5c-15bd-4dd4-9522-40e096621a27" />


```sql
SELECT CategoryName, Description
FROM Categories
ORDER BY CategoryName;
```

**Output:**

<img width="1154" height="524" alt="image" src="https://github.com/user-attachments/assets/d9a76f09-9847-4460-bad5-82ee70e66589" />


**Question 8**
---
<img width="1078" height="701" alt="image" src="https://github.com/user-attachments/assets/cc9aa00f-2cd6-4ca9-8fe8-07f4a84b84b7" />


```sql
SELECT 
    ename,
    CAST((julianday('2024-08-30') - julianday(hiredate)) / 365.25 AS INTEGER) AS Tenure
FROM emp;
```

**Output:**

<img width="912" height="350" alt="image" src="https://github.com/user-attachments/assets/8644459c-9fd9-447e-806e-76facea74110" />


**Question 9**
---
<img width="1094" height="583" alt="image" src="https://github.com/user-attachments/assets/5bc6a41c-efea-4d18-959a-45b13d991bc4" />


```sql
SELECT 
    product_id,
    original_price,
    discount_percentage,
    tax_rate,
    (original_price * (1 - discount_percentage) * (1 + tax_rate)) AS final_price
FROM Products;
```

**Output:**

<img width="1148" height="257" alt="image" src="https://github.com/user-attachments/assets/30ce6584-e1db-41d6-be89-82559036e88c" />

**Question 10**
---
<img width="906" height="525" alt="image" src="https://github.com/user-attachments/assets/756c1aa0-42c9-47c2-a2f3-a7a6188820d4" />


```sql
SELECT SUBSTR(EmpLname, 1, 4)
FROM EmployeeInfo;
```

**Output:**

<img width="1023" height="302" alt="image" src="https://github.com/user-attachments/assets/f900b3de-328d-4c9d-a325-2db1e104cd8c" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
