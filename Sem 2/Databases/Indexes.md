**Index** is used to quicken the search by reducing the number of records to search for.
Indexes are used to quickly locate data without having to search every row in a database table every time a database table is accessed. 
An index is a copy of selected columns of data from a table, called a database key that can be searched very efficiently that also includes a low-level disk block address or direct link to the complete row of data it was copied from.
# Clustered Index
The data is organized in a way that helps retrieve the data
ex: Phonebook, organized by the alphabet
# Nonclustered Index
A pointer towards the data
ex: Indexes at the end of a book
# Composite Index
Like a single index (Clustered Index), a composite index is also a data structure of records sorted on something. But unlike a single index, that something is not a field, but a concatenation of multiple fields.