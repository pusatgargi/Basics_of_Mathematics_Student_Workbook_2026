# Problem 3: When Can Matrices Be Multiplied?

## Problem Statement
The matrix sizes are

$$A_{2\times3},\qquad B_{3\times4},\qquad C_{4\times2},\qquad D_{2\times2}.$$
For the products

$$AB,\ BA,\ BC,\ CB,\ AC,\ CA,\ AD,\ DA$$
determine whether they are defined. If so, state the size of the result. Justify each decision using the dimension compatibility condition.

## Theoretical Background and Concepts
A product $MN$ is defined only when the number of columns of $M$ equals the number of rows of $N$. If $M$ is $m\times n$ and $N$ is $n\times p$, then $MN$ is $(m\times p)$.

## Detailed Step-by-Step Solution
Check each product:

- $AB$: $A$ is $2\times3$, $B$ is $3\times4$. Since $3=3$, the product is defined, and the result has size $2\times4$.
- $BA$: $B$ is $3\times4$, $A$ is $2\times3$. Since $4\ne2$, the product is not defined.
- $BC$: $B$ is $3\times4$, $C$ is $4\times2$. Since $4=4$, the product is defined, and the result has size $3\times2$.
- $CB$: $C$ is $4\times2$, $B$ is $3\times4$. Since $2\ne3$, the product is not defined.
- $AC$: $A$ is $2\times3$, $C$ is $4\times2$. Since $3\ne4$, the product is not defined.
- $CA$: $C$ is $4\times2$, $A$ is $2\times3$. Since $2=2$, the product is defined, and the result has size $4\times3$.
- $AD$: $A$ is $2\times3$, $D$ is $2\times2$. Since $3\ne2$, the product is not defined.
- $DA$: $D$ is $2\times2$, $A$ is $2\times3$. Since $2=2$, the product is defined, and the result has size $2\times3$.

## Verification and Consistency Checks
The rule is always: inner dimensions must match. So the only defined products are:

$$AB\ (2\times4),\quad BC\ (3\times2),\quad CA\ (4\times3),\quad DA\ (2\times3).$$
All other products fail because the required compatibility condition is not met.
