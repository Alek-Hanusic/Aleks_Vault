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

