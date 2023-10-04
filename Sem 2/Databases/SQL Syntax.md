## Data Types
- `INT` Whole numbers
- `DECIMAL(M,N)` Decimal numbers
	- M = Max digits, N = max decimals
- `VARCHAR(l)` String of text of length l
- `BLOB` Binary Large Object, Stores large data
- `DATE` 'YYYY-MM-DD'
- `TIMESTAMP` 'YYYY-MM-DD HH:MM:SS'


## Tables
### Create
```
CREATE TABLE <database name>;
```


```
CREATE TABLE employees (
	employee_id INT,
	first_name VARCHAR(50),
	last_name VARCHAR(50),
	hourly_pay DECIMAL(5,2),
	hire_date DATE
);
```
### Rename
```
RENAME TABLE employees TO workers
```
### Select
```
SELECT * FROM employees;
```

### Drop
```
DROP TABLE employees;
```

### Alter
```
ALTER TABLE employees
ADD phone_number VARCHAR(15);
```

```
ALTER TABLE employees
RENAME COLUMN phone_number to email;
```

```
ALTER TABLE employees
MODIFY COLUMN email VARCHAR(100);
```


==Moving a column==
```
ALTER TABLE employees
MODIFY email VARCHAR(100)
AFTER last_name
```

```
ALTER TABLE employees
DROP COLUMN email;
```

## Inserting Rows
```
INSERT INTO employees
VALUES (1,"Eugene", "Krabs","krabs@gmail.com", 25.50);

```

Inserts only employee_id:
```
INSERT INTO employees (employee_id)
VALUES (1);

```

## SELECT
```
SELECT first_name, last_name
FROM employees
```
### Example 1
```
SELECT *
FROM employees
WHERE employee_id = 1;
```

Output:

| employee ID   | first name     | last name   | email           | hour pay     |
| --- | ------ | ----- | --------------- | ----- |
| 1   | Eugene | Krabs | krabs@gmail.com | 25.50 |
### Example 2

```
SELECT *
FROM employees
WHERE first_name = "Spongebob"
```
Output:

| employee ID   | first name     | last name   | email           | hour pay     |
|---|---|---|---|---|
|2|SpongeBob|SquarePants|spongebob@gmail.com|20.00|

==other uses==
```
WHERE employee_id >= 1;
#greater than or equal to

#also less than or equal to
```
```
WHERE employee_id != 1;
#not equal to 1
```

```
SELECT *
FROM employees
WHERE email IS NULL
# returns the row of the employees whose email column  is empty
```

```
SELECT *
FROM employees
WHERE email IS NOT NULL
# returns the row of the employees whose email column  is NOT empty
```

## UPDATE
```
UPDATE employees
SET email = "spongebobkrabs@gmail.com"
WHERE employee_id = 1;

# changes email to "" to employee_id 1
```

## DELETE
`DO NOT DO THIS:`

```
DELETE FROM employees
<blank>
# it will delete all entries into the database
```


## Commits

>This commits changes to the database
```
COMMIT;
```

>This reverts the database to the state it was on the last commit
```
ROLLBACK;
```


Auto commit can be disabled.
```
SET AUTOCOMMIT = OFF;
```
With this, transactions do NOT COMMIT automatically

> COMMIT basically acts as a "save point" to which we can return when we want to


## CURRENT_DATE&TIME()
SQL has these functions to enter time/date of entry to database
`CURRENT_DATE()`
`CURRENT_TIME()`
`NOW()`
Imagine this table:

|mydate|mytime|mydatetime|
|---|---|---|
|null|null|null|

```
INSERT INTO test
VALUES (CURRENT_DATE(),CURRENT_TIME(),NOW());
```

|mydate|mytime|mydatetime|
|---|---|---|
|2023-09-03|15:45:51|2023-09-03 15:45:51|

## Constraints

### NOT NULL
- ensures that a column cannot have a NULL Value
### UNIQUE
- ensures all values in a column are different (like a primary key)
### ON UPDATE
- when parent is updated, children will update

```ON UPDATE [RESTRICT]```
	Forbids it from updating, no action is done if we try to update parent
`ON UPDATE [CASCADE]`
	If parent is updated, child is updated as well
	![[ON UPDATE CASCADE.png]]
### ON DELETE
- when parent is deleted, children will delete

```ON DELETE [RESTRICT]```
	Forbids it from deleting, no action is done if we try to delete parent
`ON DELETE [CASCADE]`
	If parent is deleted, child is deleted as well 
	![[ON DELETE CASCADE.png]]
		ParentID of 1 from **Parent Table** is deleted from **Child Table**

### CHECK
Example usage
```
CREATE TABLE employees (
	employee_id INT,
	first_name VARCHAR(50),
	last_name VARCHAR(50),
  email VARCHAR(100),
	hourly_pay DECIMAL(5,2)
	CHECK (hourly_pay >= 10.00)
	
);
```

| employee_id | first_name | hourly_pay |
| ----------- | ---------- | ---------- |
| 1           | Eugene     | 25.50      |
| 2           | SpongeBob  | 20.00      |
| 3           | Patrick    | 18.75      |
| 4           | Squidward  | 22.00      |
| 5           | Sandy      | 24.75      |
| 6           | Pearl      | 19.25      |
| 7           | Gary       | 15.50      |
| 8           | Plankton   | 30.00      |
| 9           | Mrs. Puff  | 21.50      |
| 10          | Larry      | 26.00      |
| 11          | Mermaid    | 23.75      |

> all would pass however, it is good practice to name our constraints

`CONSTRAINT chk_hourly_pay CHECK (hourly_pay >= 10.00)`

```
CREATE TABLE employees (
	employee_id INT,
	first_name VARCHAR(50),
	last_name VARCHAR(50),
  email VARCHAR(100),
	hourly_pay DECIMAL(5,2)
	CONSTRAINT chk_hourly_pay CHECK (hourly_pay >= 10.00)
	
);
```

> IF TABLE EXISTS ALREADY:

```
ALTER TABLE employees
ADD CONSTRAINT chk_hourly_pay CHECK(hourly_pay >= 10.00)
```

> Output:
>Error Code: 3819 Check constraint "chk_h_pay" is violated

> TO DELETE THE CHECK

```
ALTER TABLE employees
DROP CHECK chk_hourly_pay;
```
### DEFAULT

| product_id | product_name | price |
| ----------- | ---------- | ---------- |
| null          | null     | null      |

```
INSERT INTO employees
VALUES 
(1,"Eugene", "Krabs","<email>", 15.00),
(2, "SpngB", "SqrPnts", "<email>", 15.00)
```
> Maybe all our employees have the same hourly pay
> We have to repeatedly enter the hourly pay

> To circumvent this, use DEFAULT constraint

```
CREATE TABLE employees (
	employee_id INT,
	first_name VARCHAR(50),
	last_name VARCHAR(50),
  email VARCHAR(100),
	hourly_pay DECIMAL(5,2) DEFAULT 15
```

> Now default pay is 15, and we do not need to list it when INSERTing values
> HOWEVER, we need to list which columns we are inserting into

```
INSERT INTO employees(employeeID,first_n,last_n,email)

VALUES 
(1,"Eugene", "Krabs","<email>");
```

==GOOD TO USE WITH DATES==

```
CREATE TABLE transactions(
transaction_id INT,
amount DECIMAL(5,2),
transaction_date DATETIME DEFAULT NOW());
```

### Primary Key
> we set transactionID as the PRIMARY KEY
```
CREATE TABLE transactions(
transaction_id INT PRIMARY KEY,
amount DECIMAL(5,2),
```

#### AUTO_INCREMENT
> can be used as an attribute next to primary key

```
CREATE TABLE transactions(
transaction_id INT PRIMARY KEY AUTO_INCREMENT,
amount DECIMAL(5,2);
```
Usage:
```
INSERT INTO transactions(amount)
VALUES (4.99)
```

### Foreign Keys
```
CREATE TABLE customers(
customer_id INT PRIMARY KEY AUTO_INCREMENT,
name VARCHAR(100));

INSERT INTO customers(name)
VALUES ("James"),("John");

CREATE TABLE transactions(
transaction_id INT PRIMARY KEY AUTO_INCREMENT,
amount DECIMAL(5,2),
customer_id INT,
FOREIGN KEY(customer_id) REFERENCES customers(customer_id));

INSERT INTO transactions(amount,customer_id) VALUES
(7.99,1),(55.22,2);
```

|customer_id|name|
|---|---|
|1|James|
|2|John|


|transaction_id|amount|customer_id|
|---|---|---|
|1|7.99|1|
|2|55.22|2|

> or alter an existing table and add constraint

```
ALTER TABLE transactions
ADD CONSTRAINT fk_customer_id
FOREIGN KEY(customer_id) REFERENCES customers(customer_id)
```
