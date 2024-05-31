## Vocabulary

>Formal language is a set of strings over a finite alphabet

>In the context of logic and computer science, natural language refers to human language, such as English, Spanish, or Chinese, which is used for communication between humans.

### ASP vs Python

>The biggest conceptual difference between using Python and Answer Set Programming (ASP) to solve problems is that Python is an imperative language focused on how to achieve a solution, while ASP is a declarative language that specifies what the solution should be.

>In Python, you write step-by-step instructions to guide the computer to the answer, whereas in ASP you state the rules, constraints and facts that define the problem, and the ASP solver figures out the solution. ASP is well-suited for solving complex, combinatorial search problems by finding stable models that satisfy all the given conditions.

### ASP

>Answer Set Programming (ASP) is a programming paradigm used for solving combinatorial search problems. It revolves around defining a set of rules and constraints and then finding solutions that satisfy these rules and constraints. It's particularly well-suited for solving problems in domains such as artificial intelligence, planning, scheduling, and optimization.

>Key elements and vocabulary used in Answer Set Programming include:

1. **Facts**: These are statements about the problem domain that are considered to be true. They are typically represented using predicates without any variables.
    
2. **Rules**: Rules define relationships between variables and conditions that must be satisfied for a solution to be valid. They are written in a logical form using predicates, variables, and logical connectives like AND, OR, and NOT.
    
3. **Predicates**: Predicates represent properties or relationships within the problem domain. They are symbols that can be assigned true or false values.
    
4. **Variables**: Variables are placeholders that can take on different values. They are used to represent unknowns or parameters in the problem.
    
5. **Constraints**: Constraints impose limitations on the valid solutions to a problem. They specify conditions that must be satisfied by any solution.
    
6. **Negation as Failure**: In ASP, negation is treated as failure. This means that if a condition cannot be proven to be true, it is assumed to be false.
    
7. **Answer Sets**: Answer sets are solutions to the logic program that satisfy all the rules and constraints. They represent valid interpretations of the problem domain.
    
8. **ASP Solver**: An ASP solver is a tool or software program that takes an ASP program as input and computes its answer sets.




### First-Order Logic (FOL):

1. **Predicates**: Symbols representing properties or relations between objects in the domain.
2. **Variables**: Symbols representing unspecified elements of the domain.
3. **Constants**: Symbols representing specific elements of the domain.
4. **Quantifiers**: Symbols indicating the scope of variables (e.g., ∀ for universal quantification, ∃ for existential quantification).
5. **Functions**: Symbols representing operations on objects in the domain.
6. **Terms**: Expressions representing objects in the domain, formed from constants, variables, and functions.
7. **Formulas**: Expressions representing statements about objects in the domain, formed from predicates, variables, quantifiers, and logical connectives.
8. **Interpretation**: Assignment of meaning to symbols and expressions in a logical system.
9. **Model**: A structure that satisfies all the axioms or formulas of a logical system.
10. **Inference Rules**: Rules governing the derivation of new formulas from existing ones.

### Deterministic Finite Automata (DFA) and Petri Nets:

1. **States**: Nodes representing specific conditions or configurations.
2. **Transitions**: Edges or arcs representing possible state changes or events.
3. **Alphabet**: Set of symbols that the automaton or Petri net can read or use.
4. **Initial State**: Starting point of the automaton or Petri net.
5. **Final States (Accepting States)**: States indicating successful completion or acceptance of input.
6. **Transition Functions**: Rules governing state transitions based on input symbols or current states.
7. **Marking**: Distribution of tokens in a Petri net representing the current state.
8. **Firing**: Execution of a transition in a Petri net, resulting in a change of marking.
9. **Deadlock**: Situation in a Petri net where no transition can fire.
10. **Concurrency**: Ability of multiple transitions to fire simultaneously in a Petri net, representing concurrent processes.






