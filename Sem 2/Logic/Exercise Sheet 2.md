> Alek Hanušić

## Exercise 2.1
Given the following, can you prove:
a) that the unicorn is horned?
b) that the unicorn is magical?
c) that the unicorn is mythical?

•If the unicorn is mythical, then it is immortal, but if it is not mythical, then it is a mortal mammal.
•If the unicorn is either immortal or a mammal, then it is horned.
•The unicorn is magical if it is horned.

*We know:*
>R1: Mythical ⇒ ¬Mortal. 
>R2: ¬Mythical ⇒ Mortal ∧ Mammal. 
>R3: (¬Mortal ∨ Mammal) ⇒ Horned. 
>R4: Horned ⇒ Magical.

> Implication elimination R1 and R2:
R5: ¬Mythical ∨ ¬Mortal.
R6: Mythical ∨ (Mortal ∧ Mammal).
• R6 to CNF:
R7: (Mythical ∨ Mortal) ∧ (Mythical ∨ Mammal).
• Resolution of R5 and R7 (after and-elimination):
R8: ¬Mortal ∨ Mammal.
• R8 modus ponens R3:
R9: Horned.


## Exercise 2.2
![[Pasted image 20240309191015.png]]