# Problem 13: Does Every Equation Add New Information?

## Problem Statement
Consider the system

$$x_1+x_2=10,\qquad x_2+x_3=8,\qquad x_1-x_3=2.$$

Solve it and check whether all three equations are independently necessary to describe the solution set. If one follows from the others, show this by calculation.

## Theoretical Background and Concepts
In a system of linear equations, an equation is **redundant** (adds no new information) if it is a linear combination of the other equations.
When an equation is redundant:
- Eliminating it does not change the solution set.
- In Gaussian elimination, the redundant equation reduces to a row of zeros $[0 \; 0 \; 0 \mid 0]$.
- The rank of the coefficient matrix is strictly less than the number of equations ($r < m$).

## Detailed Step-by-Step Solution
1. **Check for redundancy by linear combination:**
   Look closely at the left-hand sides:
   - Equation 1: $x_1 + x_2$
   - Equation 2: $x_2 + x_3$
   Subtract Equation 2 from Equation 1:
   $$(x_1 + x_2) - (x_2 + x_3) = x_1 - x_3.$$
   Subtract their right-hand sides:
   $$10 - 8 = 2.$$
   This gives precisely:
   $$x_1 - x_3 = 2,$$
   which is **identical to Equation 3**.
   Therefore, Equation 3 follows directly as the difference of Equation 1 and Equation 2:
   $$\text{Eq}_3 = \text{Eq}_1 - \text{Eq}_2.$$
   Equation 3 adds **no new information** to the system and is redundant.

2. **Solve the system via Gaussian elimination:**
   Set up the augmented matrix:
   $$\left[\begin{array}{ccc|c} 1 & 1 & 0 & 10 \\ 0 & 1 & 1 & 8 \\ 1 & 0 & -1 & 2 \end{array}\right]$$
   Apply $R_3 \leftarrow R_3 - R_1$:
   $$\left[\begin{array}{ccc|c} 1 & 1 & 0 & 10 \\ 0 & 1 & 1 & 8 \\ 0 & -1 & -1 & 2 - 10 \end{array}\right] = \left[\begin{array}{ccc|c} 1 & 1 & 0 & 10 \\ 0 & 1 & 1 & 8 \\ 0 & -1 & -1 & -8 \end{array}\right]$$
   Apply $R_3 \leftarrow R_3 + R_2$:
   $$\left[\begin{array}{ccc|c} 1 & 1 & 0 & 10 \\ 0 & 1 & 1 & 8 \\ 0 & 0 & 0 & 0 \end{array}\right]$$
   The third row becomes all zeros, formally proving that Equation 3 is linearly dependent on the first two.

3. **Parametric solution:**
   - Pivots in Columns 1 and 2 ($x_1, x_2$).
   - Free variable: $x_3 = t \in \mathbb{R}$.
   - From row 2: $x_2 + t = 8 \implies x_2 = 8 - t$.
   - From row 1: $x_1 + (8 - t) = 10 \implies x_1 = 2 + t$.

   The solution set is:
   $$\begin{pmatrix}x_1\\x_2\\x_3\end{pmatrix} = \begin{pmatrix}2 + t \\ 8 - t \\ t\end{pmatrix} = \begin{pmatrix}2\\8\\0\end{pmatrix} + t \begin{pmatrix}1\\-1\\1\end{pmatrix},\quad t \in \mathbb{R}.$$

## Verification and Consistency Checks
- Check with $t = 0$: $(x_1, x_2, x_3) = (2, 8, 0)$.
  - $2 + 8 = 10$ $\checkmark$
  - $8 + 0 = 8$ $\checkmark$
  - $2 - 0 = 2$ $\checkmark$
- Check with $t = 5$: $(x_1, x_2, x_3) = (7, 3, 5)$.
  - $7 + 3 = 10$ $\checkmark$
  - $3 + 5 = 8$ $\checkmark$
  - $7 - 5 = 2$ $\checkmark$
Because the third equation is a consequence of the first two, the two remaining independent equations in three unknowns describe a 1-dimensional line in $\mathbb{R}^3$.
