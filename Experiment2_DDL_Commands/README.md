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


<img width="798" height="367" alt="image" src="https://github.com/user-attachments/assets/56a7b652-580e-461a-bf7c-36bd0fdadd3b" />


```sql
 CREATE TABLE Products (
    ProductID INTEGER PRIMARY KEY,
    ProductName TEXT NOT NULL,
    Price REAL CHECK (Price > 0),
    Stock INTEGER CHECK (Stock >= 0)
);
```

**Output:**

<img width="1148" height="244" alt="image" src="https://github.com/user-attachments/assets/fdcb9b2f-a7b0-4c76-a69b-4eb6df3ee490" />


**Question 2**
---
<img width="1194" height="595" alt="image" src="https://github.com/user-attachments/assets/538a4c14-6962-43ec-9ddb-b950f16540c8" />


```sql
ALTER TABLE customer
ADD COLUMN email VARCHAR(100);
```

**Output:**

<img width="1155" height="324" alt="image" src="https://github.com/user-attachments/assets/d7533229-f4ad-4c4c-9974-a0d4bc3acc4d" />


**Question 3**
---
<img width="1192" height="514" alt="image" src="https://github.com/user-attachments/assets/8f862f24-bc39-472b-993c-e2723d896c19" />


```sql
INSERT INTO Customers (CustomerID, Name, Address, City, ZipCode)
VALUES (306, 'Diana Prince', 'Themyscira', NULL, NULL);

INSERT INTO Customers (CustomerID, Name, Address, City, ZipCode)
VALUES (307, 'Bruce Wayne', 'Wayne Manor', 'Gotham', 10007);

INSERT INTO Customers (CustomerID, Name, Address, City, ZipCode)
VALUES (308, 'Peter Parker', 'Queens', NULL, 11375);
```

**Output:**

<img width="1149" height="253" alt="image" src="https://github.com/user-attachments/assets/5c3a3e19-f3d3-4e27-aaca-297583bf91d1" />


**Question 4**
---
<img width="1188" height="414" alt="image" src="https://github.com/user-attachments/assets/e4ef1c79-bfbd-477b-a428-1ebd1689992e" />


```sql
CREATE TABLE Events (
    EventID   INTEGER,
    EventName TEXT,
    EventDate DATE
);
```

**Output:**

<img width="1151" height="342" alt="image" src="https://github.com/user-attachments/assets/feed726b-e7dd-42e7-b024-7506ca949342" />


**Question 5**
---
<img width="1196" height="361" alt="image" src="https://github.com/user-attachments/assets/e41d98a6-d11e-4def-8d78-4d941921ea6e" />


```sql
ALTER TABLE Student_details
ADD COLUMN email TEXT NOT NULL DEFAULT 'Invalid';
```

**Output:**

<img width="1151" height="211" alt="image" src="https://github.com/user-attachments/assets/4c4c9ef6-137e-4c60-81cc-d1771ac97fcc" />


**Question 6**
---
<img width="1181" height="462" alt="image" src="https://github.com/user-attachments/assets/bdf9359f-8f4e-4a56-9204-2fff3bc4b2f9" />


```sql
CREATE TABLE Reviews (
    ReviewID INTEGER,
    ProductID INTEGER,
    Rating REAL,
    ReviewText TEXT
);
```

**Output:**

<img width="1151" height="366" alt="image" src="https://github.com/user-attachments/assets/14d974f5-b2fb-44f7-8daa-6b99dccb6253" />


**Question 7**
---
<img width="991" height="412" alt="image" src="https://github.com/user-attachments/assets/b1686939-79ac-44c0-a623-05a4dc327c37" />


```sql
CREATE TABLE Orders (
    OrderID INTEGER,
    OrderDate TEXT,
    CustomerID INTEGER
);
```

**Output:**

<img width="1148" height="338" alt="image" src="https://github.com/user-attachments/assets/ff402860-bf0f-4179-baeb-e48747a8b415" />


**Question 8**
---
<img width="1170" height="293" alt="image" src="https://github.com/user-attachments/assets/0810c7ae-8a28-4391-91de-bff14133ae38" />


```sql
INSERT INTO Books (ISBN, Title, Author, Publisher, Year)
VALUES ('978-1234567890', 'Data Science Essentials', 'Jane Doe', 'TechBooks', 2024);
```

**Output:**

<img width="1154" height="202" alt="image" src="https://github.com/user-attachments/assets/37019889-11cc-40ca-a82e-ea7ba343949f" />


**Question 9**
---
<img width="840" height="488" alt="image" src="https://github.com/user-attachments/assets/ecc24aad-c458-4426-aad7-596caebaec4c" />


```sql
INSERT INTO Customers(ID, NAME, AGE, ADDRESS, SALARY)
VALUES(1, 'Ramesh', 32, 'Ahmedabad', 2000);
INSERT INTO Customers(ID, NAME, AGE, ADDRESS, SALARY)
VALUES(2, 'Khilan', 25, 'Delhi', 1500);
INSERT INTO Customers(ID, NAME, AGE, ADDRESS, SALARY)
VALUES(3 , 'Kaushik', 23, 'Kota', 2000);
```

**Output:**

<img width="1151" height="248" alt="image" src="https://github.com/user-attachments/assets/a5fce891-ff6b-429e-a5eb-d4e9582df245" />

**Question 10**
---
<img width="1191" height="388" alt="image" src="https://github.com/user-attachments/assets/544570c7-e5e0-41da-ab83-c454e56f342f" />


```sql
CREATE TABLE Attendance(
  AttendanceID INTEGER PRIMARY KEY,
  EmployeeID INTEGER,
  AttendanceDate DATE,
  Status TEXT CHECK(Status IN ('Present','Absent','Leave')),
  FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID)

);
```

**Output:**
<img width="1146" height="251" alt="image" src="https://github.com/user-attachments/assets/4d8fa4e4-f4ef-4363-982a-f0b40bc8b3b6" />



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
