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