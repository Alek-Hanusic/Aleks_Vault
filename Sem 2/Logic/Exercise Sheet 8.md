> By: Alek Hanušić
## 8.1

### “Getting angry does not solve anything.”
> ¬∃x (Angry(x)∧Solve(x))

### “Getting angry does not solve anything.”
> ¬∀x (Angry(x)→Solve(x))

## 8.2

### Determine the truth value of the following formulas:
• P(1, 1) is True
• P(1, 2) is False
• P(2, 1) is False
• P(2, 2) is True

| Formula                      | Truth Value | Translation                                             |
| ---------------------------- | :---------: | ------------------------------------------------------- |
| a) ∀x ∃y P(x, y)             |      T      | for every x, there exists a y such that P(x,y) is true  |
| b) ∀x, y P(x, y)             |      F      | P(x,y) is true for all possible combinations of x and y |
| c) ∃x ∀y P(x, y)             |      F      | there exists an x such that for all y, P(x,y) is true   |
| d) ∃y (¬P(1, y))             |      T      | there exists a y such that P(1,y) is false              |
| e) ∀x, y (P(x, y) ⇒ P(y, x)) |      F      | if P(x,y) is true, then P(y,x) also is true             |
| f) ∀x P(x, x)                |      T      | P(x,x) is true for all x (P(1,1) and P(2,2))            |

## 8.3
### All horses are animals:
> ∀x (Horse(x)→Animal(x))

### Therefore, the head of a horse is the head of an animal:
> ∀x (Horse(x)→Head(x) ∧ Head(Animal(x)))


## 8.4
### Original
```c
innocent(Suspect) :- motive(Suspect), not guilty(Suspect).

motive(harry).
motive(sally).
guilty(harry).
```

#### Output:
```c
motive(harry) motive(sally) guilty(harry) innocent(sally)
```

> The rule above says that the suspect is innocent if they have a motive and they are not guilty
### Altered
```c
innocent(Suspect) :- motive(Suspect), not guilty(Suspect).

motive(harry).
motive(sally).
guilty(harry).
guilty(sally).

```

#### Output:
```c
motive(harry) motive(sally) guilty(harry) guilty(sally)
```

> so, if we add the fact that sally is now guilty, she is no longer 

### b)
> I had difficuilties installing clingo as well as finding the Towers of Hanoi puzzle. Assuming this is the correct ToH code:
```python
peg(a;b;c).
disk(1..4).
init_on(1..4,a).
goal_on(1..4,c).
moves(15).
```
#### Output:
```python
clingo version 5.7.0
Reading from stdin
Solving...
Answer: 1
disk(1) disk(2) disk(3) disk(4) init_on(1,a) init_on(2,a) init_on(3,a) init_on(4,a) goal_on(1,c) goal_on(2,c) goal_on(3,c) goal_on(4,c) moves(15) peg(a) peg(b) peg(c)
SATISFIABLE

Models       : 1
Calls        : 1
Time         : 0.014s (Solving: 0.00s 1st Model: 0.00s Unsat: 0.00s)
CPU Time     : 0.000s
```




