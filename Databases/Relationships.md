- One to one
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

- One to many
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

- Many to many
	- A many-to-many relationship is a type of cardinality that refers to the relationship between two entities, say, A and B, where A may contain a parent instance for which there are many children in B and vice versa.
	- *A student can register for many classes, and a class can include many students.*
 