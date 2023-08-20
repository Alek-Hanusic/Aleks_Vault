# Primary Key
- a column in a relational database table that's distinctive for each record
- unique
- never changing
- not null
# Foreign Key
- integrity
- unique (multiple references to one value ex. multiple people having same membership)
- improves functionality
- less work
- allows for added complexity
# Superkey
- set of attributes that can uniquely identify a row in a table 
- can also be one attribute
- only for designing a database, not actual SQL feature
- Asks "Can every row be unique?"
# Candidate Key
- minimal set of superkey (all keys that can be primary key ex: userID, phone number)
- candidates for being a primary key
- can be more than one candidate key
- Asks "How many columns are needed"
# Alternate Key
- Alternate keys are those candidate keys which are not the Primary key
- only for designing a database, not actual SQL feature
# Natural Key
- a possible column that can be used as a primary key (ex: username)

| **username** | balance |
| ------------ | ------- |
| alekk        | 55$     |
	==username used as primary key==
# Surrogate Keys
- purposefully (made up) generated column to be used as primary key
- kept private


| **userID** | username |
| ------ | -------- |
| 1      | alekk    |
| 2      | james21  |
	==userID used as primary key==

==Use only surrogate or only Natural (stick to one or the other - consistency)==
