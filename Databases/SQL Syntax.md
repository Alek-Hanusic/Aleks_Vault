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
|employee_id|first_name|last_name|email|hourly_pay|
|---|---|---|---|---|
|1|Eugene|Krabs|krabs@gmail.com|25.50|
|2|SpongeBob|SquarePants|spongebob@gmail.com|20.00|
|3|Patrick|Star|patrick@gmail.com|18.75|
|4|Squidward|Tentacles|squidward@gmail.com|22.00|
|5|Sandy|Cheeks|sandy@gmail.com|24.75|
|6|Pearl|Krabs|pearl@gmail.com|19.25|
|7|Gary|Snail|gary@gmail.com|15.50|
|8|Plankton|Plankton|plankton@gmail.com|30.00|
|9|Mrs. Puff|Puff|mrspuff@gmail.com|21.50|
|10|Larry|Lobster|larry@gmail.com|26.00|
|11|Mermaid|Man|mermaidman@gmail.com|23.75|


