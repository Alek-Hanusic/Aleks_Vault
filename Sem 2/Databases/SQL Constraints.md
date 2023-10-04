
# NOT NULL
- ensures that a column cannot have a NULL Value
# UNIQUE
- ensures all values in a column are different (like a primary key)
# ON UPDATE
- when parent is updated, children will update

```ON UPDATE [RESTRICT]```
	Forbids it from updating, no action is done if we try to update parent
`ON UPDATE [CASCADE]`
	If parent is updated, child is updated as well
	![[ON UPDATE CASCADE.png]]
# ON DELETE
- when parent is deleted, children will delete

```ON DELETE [RESTRICT]```
	Forbids it from deleting, no action is done if we try to delete parent
`ON DELETE [CASCADE]`
	If parent is deleted, child is deleted as well 
	![[ON DELETE CASCADE.png]]
		ParentID of 1 from **Parent Table** is deleted from **Child Table**
