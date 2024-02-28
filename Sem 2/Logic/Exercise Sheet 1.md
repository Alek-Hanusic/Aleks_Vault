
Submit your solutions as a single PDF document to the Teams assignment by
March 3, 23:59.

## Exercise 1.1 (Score: 5)

Symbolize the following statements by formulas in propositional logic. Provide
a definition in natural language for each propositional symbol you use.


>a) Wolfram likes a dish if and only if it is vegetarian and does not contain
celery.
```
L: likes a dish
V: vegetarian dish
C: dish with celery

L ⇔ (V ∧ ¬C)
```

>b) Two sets are the same if and only if they have the same members.

```
SS: Same sets
SM: Same members

SS ⇔ SM
```

>c) If you do not eat up, it will rain tomorrow.

```
Rain: It will rain tomorrow
Eat: the person eats up

¬Eat ⇒ Rain
```

>d) Cancer will not be cured unless its cause is determined and a new drug
for cancer is found.

```
Cured: cancer cured
Cause: cancer cause determined
Drug: cancer drug found

¬(Cause ∧ Drug) ⇒ ¬Cured

```

>e) It requires knowing the right people to get this job.

```
Job: Get this job
Knowing: requires knowing people

Job ⇒ Knowing
```

## Exercise 1.2 (Score: 5)

>Let
A ≜ They have an accident,
S ≜ They are sick,
I ≜ They are injured,
D ≜ They need a doctor,
L ≜ They need a lawyer.

>State the following formulas in English.


>a)¬(S∨I)⇒ ¬D
```
If they are neither sick nor injured, they do not need a doctor
```
>b) (D∧L)⇔(S∧I)
```
They need (both?) a doctor and a lawyer if and only if they are sick and injured
```
>c) (D∧L)⇒A
```
If they need a doctor and a lawyer, then they have an accident
```
d) D⇒(S∨I)
```
If they need a doctor, then they are sick or injured
```
e) (S⇒D)∧(A⇒L)
```
If they are sick then they need a doctor, and if they had an accident, then they need a lawyer
```
## Exercise 1.3 (Score: 5)

>Construct a truth table for the formula (¬P∨Q)∧(¬(P∧ ¬Q)). Make a
column for each significant subformula to improve comprehensibility (i.e., the truth table must have more than three columns).


| P     | Q     | ¬P    | ¬Q    | ¬P∨Q  | P∧¬Q  | ¬(P∧¬Q) | (¬P∨Q)∧(¬(P∧¬Q)) |
| ----- | ----- | ----- | ----- | ----- | ----- | ------- | ---------------- |
| true  | true  | false | false | true  | false | true    | true             |
| true  | false | false | true  | false | true  | false   | false            |
| false | true  | true  | false | true  | false | true    | true             |
| false | false | true  | true  | true  | false | true    | true             |



## Exercise 1.4 (Score: 5)

>Familiarise yourself with the logical equivalences shown in the lecture and prove
at least three of them (each involving at least two variables,αandβ) by con-
structing truth tables. Make a column for each significant subformula to improve
comprehensibility.

>(^1) Hint:“Unless” is to be understood as “if not” here.
Page 1 of 1

# (α∧β)≡(β∧α)

# (α ⇒ β) ≡ (¬β ⇒ ¬α)

# 3 


