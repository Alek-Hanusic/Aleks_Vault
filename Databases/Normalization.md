# 1NF
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

# 2NF
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


# 3NF
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

## Update Anomalies
When updating data in a non-normalized database, sometimes not all of the data can get updated due to the lack of normalization. Another possible problem can be updating the wrong data. This is called an **update anomaly** and can be fixed by making sure the database has a higher level of normalization.

| ID | Name   | City          | Total Sales |
|----|--------|---------------|-------------|
| 1  | Arthur | New York City | $26,000     |
| 2  | Sarah  | **Cincinnati**    | NULL        |
| 3  | Josh   | **Cincinnati**    | $20,000     |
In the table above, if we updated the sales of an employee in cincinnati without specifics, we would end up updating either both of the sales for Sarah or Josh, or by possibly updating the wrong employee.
## Insertion Anomalies
Sometimes, when working with a non-normalized database, incomplete data being added to the database can lead to NULL values existing within the database. This is called an insertion anomaly and can be prevented by making sure the database has a higher level of normalization.

| ID | Name   | City          | Total Sales |
|----|--------|---------------|-------------|
| 1  | Arthur | New York City | $26,000     |
| 2  | Sarah  | Cincinnati    | NULL        |
| 3  | Josh   | Los Angeles   | $20,000     |
In the table above, new employees won't have any sales yet meaning that there will be a number of NULL values in the database until a set number exists.
## Deletion Anomalies
When working with a non-normalized database, a deletion anomaly can occur. A deletion anomaly is when a query ends up deleting more data from the database than was intended due to a lack of normalization.