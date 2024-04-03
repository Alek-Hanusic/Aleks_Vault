## Atomic Value
1 thing in each column

`Caleb Daniel Curry`

*Incorrect*

| Name    |     |
| --- | --- |
|Caleb Daniel Curry|     |

**Correct**

| Name  | Mid Name | Last Name |
| ------ | ------ | ----- |
| Caleb | Daniel  | Curry      |
## Attributes
The data about [[Entities]] that we store (username, password)

They are represented as columns in the database table.


## Cardinality vs Modality

### Cardinality
- cardinality refers to the number of unique values in a relational table column relative to the
- relationship type

![[Cardinality Ex.png]]
==This is a one to many relationship==

### Modality
- modality describes whether a relationship between two or more entities is needed or not 
- the modality can be classified into two types namely nullable modality and non−nullable modality

| **Cardinality**                                                                                                                                                   | **Modality**                                                                |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| It tells about the maximum number of associations between rows of tables.                                                                                         | It tells about the minimum number of row associations in a table.           |
| There are different types − One−to−one, one−to−many, many−to−many.                                                                                                | There are different types − Nullable and Not nullable.                      |
| Oneto one is where the occurrence of object 'A' can relate to one and only one occurrence of object 'B', and vice−versa.                                          | Nullable columns accept an empty field.                                     |
| Onetomany is where the occurrence of object 'A' can relate to multiple occurrences of object 'B', but object 'B' can relate to a single occurrence of object 'A'. | The non−nullable column doesn't accept null values.                         |
| Manytomany is where multiple occurrences of object 'A' can relate to multiple occurrences of object 'B', and vice−versa.                                          | Modality states the possibility of making relationships among data objects. |

## DDL
_DDL_ is a set of [[SQL]] commands used to create, modify, and delete database structures but not data.

Ex: `CREATE`

## DML
The [[SQL]] commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the [[SQL]] statements.

Ex: `UPDATE`

## Domain Integrity
Domain integrity is **the collection of processes that ensure the accuracy of each piece of data in a domain**. In this context, a domain is a set of acceptable values that a column is allowed to contain.

Example: "cake" in 10 digit phone number column

## Entities
The things we store data about (Person, Product, Customer)

==Multiple entities form [[Relationships]]==

## Entity Integrity

Entity integrity is concerned with **ensuring that each row of a table has a unique and non-null primary key value**

Example: ID

## Indexes
**Index** is used to quicken the search by reducing the number of records to search for.
Indexes are used to quickly locate data without having to search every row in a database table every time a database table is accessed. 
An index is a copy of selected columns of data from a table, called a database key that can be searched very efficiently that also includes a low-level disk block address or direct link to the complete row of data it was copied from.
### Clustered Index
The data is organized in a way that helps retrieve the data
ex: Phonebook, organized by the alphabet
### Nonclustered Index
A pointer towards the data
ex: Indexes at the end of a book
### Composite Index
Like a single index (Clustered Index), a composite index is also a data structure of records sorted on something. But unlike a single index, that something is not a field, but a concatenation of multiple fields.

## Keys
### Primary Key
- a column in a relational database table that's distinctive for each record
- unique
- never changing
- not null
- Attributes that are a part of the primary key are called **prime attributes**
### Foreign Key
- integrity
- links data in one table to the data in another table.
- unique (multiple references to one value ex. multiple people having same membership)
- improves functionality
- less work
- allows for added complexity
- [[SQL Constraints]]
### Superkey
- set of attributes that can uniquely identify a row in a table 
- can also be one attribute
- only for designing a database, not actual SQL feature
- Asks "Can every row be unique?"
### Candidate Key
- minimal set of superkey (all keys that can be primary key ex: userID, phone number)
- candidates for being a primary key
- can be more than one candidate key
- Asks "How many columns are needed"
### Alternate Key
- Alternate keys are those candidate keys which are not the Primary key
- only for designing a database, not actual SQL feature
### Natural Key
- a possible existing column that can be used as a primary key (ex: username)

| **username** | balance |
| ------------ | ------- |
| alekk        | 55$     |
	==username used as primary key==
### Surrogate Keys
- purposefully (made up) generated column to be used as primary key
- kept private


| **userID** | username |
| ------ | -------- |
| 1      | alekk    |
| 2      | james21  |
	==userID used as primary key==

==Use only surrogate or only Natural (stick to one or the other - consistency)==
### Simple Keys
- One column keys (natural key, ex: username)
### Composite/Compound Keys
- Multiple column keys (First Name + Last Name + Email)

![[Composite Keys.png]]
- In this case, StudentID and ClassID together count as the primary key.

- For example, a table for youtube video comments might include 3 columns, userID, videoID and timestamp. Since one user can have multiple comments on the same video, we need a third column to act as the "differentiator".

## Normalization
### 1NF
A 1NF database is an [[Atomic Value]] database. In this case, [[Atomic Value]] means that each cell contains one value and each row is unique. In the given example, we can see that the non-atomic table has cells with more than one value and non-unique rows.


This would be a **non-atomic** table

| Title           | Length     | Type |
| --------------- | ---------- | ---- |
| Example A, B, C | 125 inches | B, C |
| Example A, B, C | 125 inches | B, C |

This would be an **atomic** table

| ID | Title     | Length     | Type |
|----|-----------|------------|------|
| 1  | Example A | 125 inches | B    |
| 2  | Example A | 125 inches | C    |

### 2NF
When a database is said to be 2NF, that means the database is both 1NF and contains no partial dependencies. A partial dependency is when an attribute depends partly on the table’s primary key.

==Each non-key attribute must depend on the entire primary key==

A 1NF Database with partial dependencies

| ID | Name    | Address ID | Address               |
|----|---------|------------|-----------------------|
| 1  | Logan   | 1          | 7777 Willow Drive     |
| 2  | Charlie | 2          | 8888 Blue Bonnet Road |
| 3  | Johanna | 1          | 7777 Willow Drive     |
A 2NF database

*Name.db*

| ID | Name    | Address ID |
|----|---------|------------|
| 1  | Logan   | 1          |
| 2  | Charlie | 2          |
| 3  | Johanna | 1          |

*Address.db*

| Address ID | Address               |
|------------|-----------------------|
| 1          | 7777 Willow Drive     |
| 2          | 8888 Blue Bonnet Road |


### 3NF
==Each non-key attribute depends on the key, the whole key and nothing but the key. ==
When making a 3NF database, two goals need to be accomplished. The first being that the database is already 2NF, and the second being that the database contains no transitive functional dependencies. A transitive functional dependency is when a non-prime attribute is dependent on another non-prime attribute.

==When an attribute depends on another non-primary key attribute==
ex:

| Review_ID | Review   | Star          | Star_Meaning |
|----|--------|---------------|-------------|
| 1  | abcd | 4 | Very good    |

==Star_Meaning depends on Star so its best to make Star a foreign key linking to a stars table w meaning for each star==

![[Transitive Dependency.png]]

A 2NF database **with transitive functional dependency**:

| ID | Name | Address |
|----|---------|-----------------------|
| 1 | Logan | 7777 Willow Drive |
| 2 | Charlie | 4444 Blue Bonnet Road |
| 4 | Hannah | 4444 Blue Bonnet Road |


A 3NF database with **no transitive functional dependencies**:

*name.db

| ID | Name | Address ID |
|----|---------|------------|
| 1 | Logan | 1 |
| 2 | Charlie | 2 |
| 4 | Hannah | 2 |


*Address.db

| Address ID | Address |
|------------|-----------------------|
| 1 | 7777 Willow Drive |
| 2 | 4444 Blue Bonnet Road |

#### Update Anomalies
When updating data in a non-normalized database, sometimes not all of the data can get updated due to the lack of normalization. Another possible problem can be updating the wrong data. This is called an **update anomaly** and can be fixed by making sure the database has a higher level of normalization.

| ID | Name   | City          | Total Sales |
|----|--------|---------------|-------------|
| 1  | Arthur | New York City | $26,000     |
| 2  | Sarah  | **Cincinnati**    | NULL        |
| 3  | Josh   | **Cincinnati**    | $20,000     |
In the table above, if we updated the sales of an employee in cincinnati without specifics, we would end up updating either both of the sales for Sarah or Josh, or by possibly updating the wrong employee.
#### Insertion Anomalies
Sometimes, when working with a non-normalized database, incomplete data being added to the database can lead to NULL values existing within the database. This is called an insertion anomaly and can be prevented by making sure the database has a higher level of normalization.

| ID | Name   | City          | Total Sales |
|----|--------|---------------|-------------|
| 1  | Arthur | New York City | $26,000     |
| 2  | Sarah  | Cincinnati    | NULL        |
| 3  | Josh   | Los Angeles   | $20,000     |
In the table above, new employees won't have any sales yet meaning that there will be a number of NULL values in the database until a set number exists.
#### Deletion Anomalies
When working with a non-normalized database, a deletion anomaly can occur. A deletion anomaly is when a query ends up deleting more data from the database than was intended due to a lack of normalization.


### Boyce Codd NF
With the exception of trivial functional dependencies, every functional dependency in a table must be a dependency on a superkey

## Query
A database query is used  to retrieve information from and take action on databases.
Primarily, queries are used to find specific data by filtering explicit criteria.

A database query is either an action query or a select query. A select query is one that retrieves data from a database. An action query asks for additional operations on data, such as insertion, updating, deleting or other forms of data manipulation.

## RDBMS
The software used to store, manage, [[Query]], and retrieve data stored in a [[Relational Database]].

It also enables [[Views]]

## Referential Integrity

Referential integrity is **a constraint on the database design that makes certain that each foreign key in a table point to a unique primary key value in another table**.

## Relational Database
Consists of [[Attributes]] and [[Entities]]


## Relationships

==Parent-Child Relationship:==
A parent record can have many child records, but a child record belongs to one and only one parent record.


- One to one **1:1**
	- One entity has a connection to only one other entity
	- *One person has one Social Security Number, one Social Security Number is assigned to one person*

**Incorrect:**
Users (and Card) Table


| First Name | Last Name | Card Number     | CVV |
| ---------- | --------- | --------------- | --- |
| Alek       | Holmes    | 213 213 123 132 | 213 |

**Correct:**

| First Name | Last Name | Card ID |
|------------|-----------|---------|
| Alek       | Holmes    | 25      |

| Card ID | Card Number         | CVV | Expiry Date |
| ------- | ------------------- | --- | ----------- |
| 25      | 2131 2312 3213 2131 | 211 | 12/05       |

- One to many **1:N**
	- One entity has multiple connections to other entities
	- *One person can have multiple YouTube comments, a comment only has one author*

| userID | First Name |
| ------ | ---------- |
| 1      | Alek       |
| 2      | Jimmy      |

| cardID | Card Number    | userID |
|--------|----------------|--------|
| 32     | 1231 2312 3121 | 1      |
| 33     | 2313 2311 3211 | 2      |
| 34     | 5325 3242 3242 | 1      |

==One user can have many cards. Notice how they are connected! ==
==Multiple cards point to one user! ==

- Many to many **M:N**
	- A many-to-many relationship is a type of cardinality that refers to the relationship between two entities, say, A and B, where A may contain a parent instance for which there are many children in B and vice versa.
	- *A student can register for many classes, and a class can include many students.*


## SQL
### Structured Query Language

- used to **define** ([[DDL]]) database structure 
- used to **manipulate** ([[DML]]) data within database structure (INSERT,SEARCH,DELETE...)
## SQL Constraints
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

## SQL Synthax
### Data Types
- `INT` Whole numbers
- `DECIMAL(M,N)` Decimal numbers
	- M = Max digits, N = max decimals
- `VARCHAR(l)` String of text of length l
- `BLOB` Binary Large Object, Stores large data
- `DATE` 'YYYY-MM-DD'
- `TIMESTAMP` 'YYYY-MM-DD HH:MM:SS'


### Tables
#### Create
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
#### Rename
```
RENAME TABLE employees TO workers
```
#### Select
```
SELECT * FROM employees;
```

#### Drop
```
DROP TABLE employees;
```

#### Alter
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

### Inserting Rows
```
INSERT INTO employees
VALUES (1,"Eugene", "Krabs","krabs@gmail.com", 25.50);

```

Inserts only employee_id:
```
INSERT INTO employees (employee_id)
VALUES (1);

```

### SELECT
```
SELECT first_name, last_name
FROM employees
```
#### Example 1
```
SELECT *
FROM employees
WHERE employee_id = 1;
```

Output:

| employee ID   | first name     | last name   | email           | hour pay     |
| --- | ------ | ----- | --------------- | ----- |
| 1   | Eugene | Krabs | krabs@gmail.com | 25.50 |
#### Example 2

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

### UPDATE
```
UPDATE employees
SET email = "spongebobkrabs@gmail.com"
WHERE employee_id = 1;

# changes email to "" to employee_id 1
```

### DELETE
`DO NOT DO THIS:`

```
DELETE FROM employees
<blank>
# it will delete all entries into the database
```


### Commits

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


### CURRENT_DATE&TIME()
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

### Constraints

#### NOT NULL
- ensures that a column cannot have a NULL Value
#### UNIQUE
- ensures all values in a column are different (like a primary key)
#### ON UPDATE
- when parent is updated, children will update

```ON UPDATE [RESTRICT]```
	Forbids it from updating, no action is done if we try to update parent
`ON UPDATE [CASCADE]`
	If parent is updated, child is updated as well
	![[ON UPDATE CASCADE.png]]
#### ON DELETE
- when parent is deleted, children will delete

```ON DELETE [RESTRICT]```
	Forbids it from deleting, no action is done if we try to delete parent
`ON DELETE [CASCADE]`
	If parent is deleted, child is deleted as well 
	![[ON DELETE CASCADE.png]]
		ParentID of 1 from **Parent Table** is deleted from **Child Table**

#### CHECK
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
#### DEFAULT

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

#### Primary Key
> we set transactionID as the PRIMARY KEY
```
CREATE TABLE transactions(
transaction_id INT PRIMARY KEY,
amount DECIMAL(5,2),
```

##### AUTO_INCREMENT
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

#### Foreign Keys
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

## Views

A database view is **a subset of a database and is based on a query that runs on one or more database tables**. Database views are saved in the database as named queries and can be used to save frequently used, complex queries.

*Simplified:* A view of a user is what data from the table the user can see. For example, only their username and password, while they do not see their USER ID or SIGNUP TIME.