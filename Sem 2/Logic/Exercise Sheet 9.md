Using the unary predicate Person denoting people,  the unary predicate "Time" denoting a point in time, and the binary predicate Fool denoting the relation "fool a person at a point in time", formalize the following sentence in first-order logic:  “You can fool some of the people all of the time, and all of the people some of the time, but you cannot fool all of the people all of the time.”


| Predicate  |     Meaning     |
| :--------: | :-------------: |
|   Person   |     people      |
|    Time    | a point in time |
| Fool (x,y) |    fool a p     |
`You can fool some of the people all of the time`

> ∃p∃t Fool(p, t) 

*"there exists at least one person and at least one point in time where that person is fooled"*

`Fool all of the people some of the time`

> ∀p∃t Fool(p, t)

*"for every person, there exists at least one point in time where that person is fooled."*

`You cannot fool all of the people all of the time`

> NOT FOR ALL P