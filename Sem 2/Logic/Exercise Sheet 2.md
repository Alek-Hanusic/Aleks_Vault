> Alek Hanušić

## Exercise 2.1
Given the following, can you prove:
a) that the unicorn is horned?
b) that the unicorn is magical?
c) that the unicorn is mythical?

•If the unicorn is mythical, then it is immortal, but if it is not mythical, then it is a mortal mammal.
•If the unicorn is either immortal or a mammal, then it is horned.
•The unicorn is magical if it is horned.
```
a) We know it is either immortal or a mammal (1) and we know that it is horned if it is either of the two (2). Therefore, it is horned either way.

b) Because we proved it is horned when it is either immortal or a mammal, then it has to be magical (3)

c) Can not be proven
```

*We know:*
```
R1: Mythical ⇒ ¬Mortal
>R2: ¬Mythical ⇒ Mortal ∧ Mammal
>R3: (¬Mortal ∨ Mammal) ⇒ Horned
>R4: Horned ⇒ Magical
```
### a)
- We must "Translate" R6 to Conj. Normal Form:
```
***Implication elimination: (*remove if-then)

R5: ¬Mythical ∨ ¬Mortal
R6: Mythical ∨ (Mortal ∧ Mammal)
```

```
*** Distrubitivity law (distributing ∨ over ∧ wher possible):

R7: (Mythical ∨ Mortal) ∧ (Mythical ∨ Mammal)
```

```
***Resolution:
R8: ¬Mortal ∨ Mammal

Modus ponens of R3 (R8 is true so according to R3, horned -> R9 ):
R9: Horned
```
### b)
```
Modus ponens of R4 (R9 is true so Magical is true -> R10):
R10: Magical
```

### c)
```
Can not be proven
```
## Exercise 2.2
![[Pasted image 20240309191015.png]]