## 7.2
To derive the sentence Loves(Mother(John), John) ∧ ¬∃x Loves(John, x) in first-order logic, we need to follow the rules of inference. Here is a step-by-step derivation:

1. Loves(Mother(John), John) ∧ ¬∃x Loves(John, x)  (Given)
2. Loves(Mother(John), John)  (Simplification)
3. ¬∃x Loves(John, x)  (Simplification)
4. ∀x ¬Loves(John, x)  (Equivalent form of ¬∃x Loves(John, x))
5. ¬Loves(John, x)  (Universal instantiation)
6. ¬Loves(John, John)  (Universal instantiation)
7. ¬Loves(Mother(John), John)  (Substitution in 6)
8. Loves(Mother(John), John) ∧ ¬Loves(Mother(John), John)  (Conjunction introduction from 2 and 7)

The derivation shows that the sentence Loves(Mother(John), John) ∧ ¬∃x Loves(John, x) leads to a contradiction, which is expected in this case due to the negation of an existential quantifier.

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

