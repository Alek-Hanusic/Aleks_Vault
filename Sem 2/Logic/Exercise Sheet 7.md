## 7.1 a)
### Nobody is watching:
![[Pasted image 20240505160448.png]]
### Two devices are watching:
![[Pasted image 20240505174448.png]]
### Four devices watching but 5th can not (no tokens left)

![[Pasted image 20240505180033.png]]
> had to add req_watch and request to be able to show that 5th device is requesting access, but can not receive it. **This could be added before every start_watch transition**

## 7.1 b)
### No devices watching
![[Pasted image 20240505191914.png]]
### Two devices watching

![[Pasted image 20240505191718.png]]

### Four watching & 5th wants to but can not
![[Pasted image 20240505191801.png]]
## 7.2
1. Loves(Mother(John), John) ∧ ¬∃x Loves(John, x)
   > Given sentence

2. Loves(Mother(John), John)
   >This is the first part of the conjunction in the given sentence, obtained by the Simplification rule.

3. ¬∃x Loves(John, x)
   > This is the second part of the conjunction in the given sentence, obtained by the Simplification rule.

4. ∀x ¬Loves(John, x)
   >This is the equivalent form of ¬∃x Loves(John, x), since rule says that "¬∃x P(x) is equivalent to ∀x ¬P(x)".

5. ¬Loves(John, x)
   > This is obtained by the Universal Instantiation rule, which allows us to replace the universal quantifier ∀x with a specific variable x (for all x, then also one of those x).

6. ¬Loves(John, John)
   > Universal Instantiation rule, where we replace the variable x with the constant John.

7. ¬Loves(Mother(John), John)
   >  Substitution rule, where we replace the variable x in step 6 with the term Mother(John).

8. Loves(Mother(John), John) ∧ ¬Loves(Mother(John), John)
   > This is obtained by the Conjunction Introduction rule, where we combine the results from steps 2 and 7.

The final step shows that the given sentence leads to a contradiction. This means that the original sentence is not a valid statement in first-order logic.

## 7.3

R(x): "x is a real number"
Q(x): "x is a rational number"

### a) Every rational number is a real number.
∀x (Q(x) ⇒ R(x))

### b) Some real numbers are rational numbers.
∃x (R(x) ∧ Q(x))

### c) Not every real number is a rational number.
¬∀x (R(x) ⇒ Q(x))

## 7.4
### a) ∃x (C(x))
There exists at least one used-car dealer.

### b) ∃x (H(x))
There exists at least one honest person.

### c) ∀x (C(x) ⇒ ¬H(x))
For all persons, if they are a used-car dealer, then they are not honest.

### d) ∃x (C(x) ∧ H(x))
There exists at least one person who is both a used-car dealer and honest.

