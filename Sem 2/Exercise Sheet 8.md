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
