# Problem 13: Does Every Equation Add New Information?

## Problem Statement
Consider the system

$$x_1+x_2=10,\qquad x_2+x_3=8,\qquad x_1-x_3=2.$$

Solve it and check whether all three equations are independently necessary to describe the solution set. If one follows from the others, show this by calculation.

## Theoretical Background and Concepts
An equation in a linear system is redundant (adds no new information) if it can be obtained as a linear combination of the other equations. When an equation is redundant, removing it does not change the solution set of the system.

## Detailed Step-by-Step Solution
1. **Show that equation 3 follows from equations 1 and 2:**
   Subtract equation 2 from equation 1:
   $$(x_1 + x_2) - (x_2 + x_3) = 10 - 8$$
   $$x_1 - x_3 = 2.$$
   This result is **identical to the third equation**.
   Because equation 3 is simply the difference of equation 1 and equation 2:
   $$\text{Eq}_3 = \text{Eq}_1 - \text{Eq}_2,$$
   it provides no new information and is redundant. The three equations are not independently necessary.

2. **Solve the system:**
   Since equation 3 is redundant, the solution set is determined by the first two equations:
   $$\begin{cases}x_1 + x_2 = 10 \\ x_2 + x_3 = 8\end{cases}$$
   Express $x_1$ and $x_2$ in terms of $x_3$:
   - Let $x_3 = t \in \mathbb{R}$ be the free parameter.
   - From equation 2: $x_2 = 8 - t$.
   - From equation 1: $x_1 = 10 - x_2 = 10 - (8 - t) = 2 + t$.

   The solution set is:
   $$\begin{pmatrix}x_1\\x_2\\x_3\end{pmatrix} = \begin{pmatrix}2 + t \\ 8 - t \\ t\end{pmatrix} = \begin{pmatrix}2\\8\\0\end{pmatrix} + t\begin{pmatrix}1\\-1\\1\end{pmatrix},\quad t \in \mathbb{R}.$$

## Verification and Consistency Checks
Test with $t = 2 \implies (x_1, x_2, x_3) = (4, 6, 2)$:
- Eq 1: $4 + 6 = 10$ $\checkmark$
- Eq 2: $6 + 2 = 8$ $\checkmark$
- Eq 3: $4 - 2 = 2$ $\checkmark$
All three equations are satisfied, confirming the parametric line of solutions.
