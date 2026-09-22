Skip to content
MonikaVenkatesan25
19CS404-DBMS-Lab-Manual
Repository navigation
Code
Pull requests
Actions
Projects
Security and quality
Insights
19CS404-DBMS-Lab-Manual
/Experiment3_DML_Commands/
Go to file
t
T
MonikaVenkatesan25
MonikaVenkatesan25
Update README.md
b73c776
 · 
last month
This branch is 10 commits ahead of abinaya-g/19CS404-DBMS-Lab-Manual:main.
19CS404-DBMS-Lab-Manual
/Experiment3_DML_Commands/
Name	Last commit message	Last commit date
..
README.md
Update README.md
last month
README.md
Experiment 3: DML Commands
AIM
To study and implement DML (Data Manipulation Language) commands.

THEORY
1. INSERT INTO
Used to add records into a relation. These are three type of INSERT INTO queries which are as A)Inserting a single record Syntax (Single Row):

INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
Syntax (Multiple Rows):

INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
Syntax (Insert from another table):

INSERT INTO table_name SELECT * FROM other_table WHERE condition;
2. UPDATE
Used to modify records in a relation. Syntax:

UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
3. DELETE
Used to delete records from a relation. Syntax (All rows):

DELETE FROM table_name;
Syntax (Specific condition):

DELETE FROM table_name WHERE condition;
4. SELECT
Used to retrieve records from a table. Syntax:

SELECT column1, column2 FROM table_name WHERE condition;
Question 1
image
update suppliers
set address='58 Lakeview, Magnolia'
where supplier_id=5;
Output:

image
Question 2
image
SELECT *
FROM orders
WHERE NOT (
        ord_date = '2012-08-17'
        OR (customer_id > 3005 AND purch_amt < 1000)
      );
Output:

image
Question 3
image
delete from customer
where CUST_CITY <> 'New York' and OUTSTANDING_AMT>5000;
Output:

image
Question 4
image
UPDATE products
SET reorder_lvl = 20
WHERE quantity < 10
AND category = 'Snacks';
Output:

image
Question 5
image
DELETE FROM customer
WHERE WORKING_AREA = 'New York';
Output:

image
Question 6
image
UPDATE employees
SET salary = salary + 500,
    email = 'updated'
WHERE job_id = 'SA_REP'
  AND commission_pct > 0.15;
Output:

image
Question 7
image
SELECT CategoryName, Description
FROM Categories
ORDER BY CategoryName;
Output:

image
Question 8
image
SELECT 
    ename,
    CAST((julianday('2024-08-30') - julianday(hiredate)) / 365.25 AS INTEGER) AS Tenure
FROM emp;
Output:

image
Question 9
image
SELECT 
    product_id,
    original_price,
    discount_percentage,
    tax_rate,
    (original_price * (1 - discount_percentage) * (1 + tax_rate)) AS final_price
FROM Products;
Output:

image
Question 10
image
SELECT SUBSTR(EmpLname, 1, 4)
FROM EmployeeInfo;
Output:

image
RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.

 
