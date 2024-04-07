 >Alek Hanušić

## Exercise 4.1
*Symbolize the following statements by propositional formulas.* 
*a) If the humidity is high, it will rain this afternoon or this evening.* 
*b) It requires courage and skills to climb that mountain.* 

*Provide appropriate natural-language definitions for all propositional symbols.*
### a)
HighHumidity = "Humidity is High"
AfternoonRain = "it will rain this afternoon"
EveningRain = "it will rain this evening"


>HighHumidity → (AfternoonRain ∨ EveningRain)

### b)
C = "it requires courage"
S = "it requires skills"
M = "climb that mountain"

> (C ∧ S) → M

## 4.2
*b) It requires courage and skills to climb that mountain.* 

|  C  |  S  | (C∧S) |  M  |
|:---:|:---:|:-----:|:---:|
|  T  |  T  |   T   |  T  |
|  T  |  F  |   F   |  F  |
|  F  |  T  |   F   |  F  |
|  F  |  F  |   F   |  F  |
## 4.3
### a)
![[Pasted image 20240406190130.png]]
### b)

![[Pasted image 20240406185812.png]]

## 4.4
>The language defined by the regular expression: `(0*1*)*000(0 + 1)*`

>`(0*1*)*`
>Starts with any number of alternating sequences of 0s and 1s 
>ex:(00001110001111 or None)

>`000`
>Contains a sequence of three 0s

>`(0 + 1)*``
>Ends on a sequence/string consisting of zero or more occurrences of '0's and '1's
>ex. (None, 0, 011, 101, 1001)

## 4.5
*Write a regular expression for the following language in algebraic notation, in UNIX syntax, and in Python syntax: The set of strings of x’s and y’s whose fourth symbol from the right end is x.*

### Algebraic:
`(x+y)*x(x+y)^3`

### UNIX:

### Python:

`r"(x|y)*x(x|y){3}"`