# Primary Key
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