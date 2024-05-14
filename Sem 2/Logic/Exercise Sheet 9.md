> Alek Hanušić


## 9.1
**Using the unary predicate Person denoting people,  the unary predicate "Time" denoting a point in time, and the binary predicate Fool denoting the relation "fool a person at a point in time", formalize the following sentence in first-order logic:  “You can fool some of the people all of the time, and all of the people some of the time, but you cannot fool all of the people all of the time.”**


| Predicate  |     Meaning     |
| :--------: | :-------------: |
|   Person   |     people      |
|    Time    | a point in time |
| Fool (x,y) |    fool a p     |

(p,t) are used instead of (x,y) for the sake of simplicity

`You can fool some of the people all of the time`

> ∃p∀t Fool(p, t) 

*"there exists at least one person that can be fooled at any point in time"*

`Fool all of the people some of the time`

> ∀p∃t Fool(p, t)

*"for every person, there exists at least one point in time where that person is fooled."*

`You cannot fool all of the people all of the time`

> ¬∀p∀t Fool(p, t)

*it is not the case that for every person and every point in time, that person is fooled*



### Final:

***∃p∀t Fool(p, t) ∧ ∀p∃t Fool(p, t) ∧ ¬∀p∀t Fool(p, t)***

