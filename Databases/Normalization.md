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


