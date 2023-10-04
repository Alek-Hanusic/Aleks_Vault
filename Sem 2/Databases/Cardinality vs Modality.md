# Cardinality
- cardinality refers to the number of unique values in a relational table column relative to the
- relationship type

![[Cardinality Ex.png]]
==This is a one to many relationship==

# Modality
- modality describes whether a relationship between two or more entities is needed or not 
- the modality can be classified into two types namely nullable modality and non−nullable modality

|**Cardinality**|**Modality**|
|---|---|
|It tells about the maximum number of associations between rows of tables.|It tells about the minimum number of row associations in a table.|
|There are different types − One−to−one, one−to−many, many−to−many.|There are different types − Nullable and Not nullable.|
|Oneto one is where the occurrence of object 'A' can relate to one and only one occurrence of object 'B', and vice−versa.|Nullable columns accept an empty field.|
|Onetomany is where the occurrence of object 'A' can relate to multiple occurrences of object 'B', but object 'B' can relate to a single occurrence of object 'A'.|The non−nullable column doesn't accept null values.|
|Manytomany is where multiple occurrences of object 'A' can relate to multiple occurrences of object 'B', and vice−versa.|Modality states the possibility of making relationships among data objects.|

