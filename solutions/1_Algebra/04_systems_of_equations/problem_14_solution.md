# Problem 14: A Small Change in the Right-Hand Side

## Problem Statement
Compare the systems

$$\begin{cases}x+y=2,\\2x-y=1,\\3x=3\end{cases}\qquad \text{and}\qquad \begin{cases}x+y=2,\\2x-y=1,\\3x=3.1.\end{cases}$$

Check the consistency of each system and explain why a small change in one number can change the type of the system.

## Theoretical Background and Concepts
An **overdetermined system** has more equations than unknowns ($m > n$, here $3$ equations and $2$ unknowns).
For an overdetermined system to be consistent, the right-hand side vector $b$ must lie precisely within the column space of $A$ (a subspace of dimension at most $n$).
In geometric terms:
- Each equation represents a line in $\mathbb{R}^2$.
- Three lines in $\mathbb{R}^2$ intersect at a single common point only under an exact algebraic alignment.
- A tiny perturbation to the right-hand side shifts one line parallel to itself, immediately destroying the triple intersection and turning a consistent system into an inconsistent one.

## Detailed Step-by-Step Solution
1. **Analyze System 1:**
   $$\begin{cases}x + y = 2 \\ 2x - y = 1 \\ 3x = 3\end{cases}$$
   - From equation 3:
     $$3x = 3 \implies x = 1.$$
   - Substitute $x = 1$ into equation 1:
     $$1 + y = 2 \implies y = 1.$$
   - Check compatibility with equation 2:
     $$2(1) - (1) = 2 - 1 = 1.$$
     The left side equals the right side ($1 = 1$).
   All three equations agree at $(x, y) = (1, 1)$.
   **System 1 is consistent** and has the **unique solution** $(1, 1)$.

2. **Analyze System 2:**
   $$\begin{cases}x + y = 2 \\ 2x - y = 1 \\ 3x = 3.1\end{cases}$$
   - The first two equations are identical to System 1. Adding them:
     $$(x + y) + (2x - y) = 2 + 1 \implies 3x = 3 \implies x = 1,\quad y = 1.$$
     Thus, the unique intersection of the first two lines remains at $(1, 1)$.
   - Now test the third equation at $(1, 1)$:
     $$3x = 3(1) = 3.$$
     However, equation 3 requires:
     $$3x = 3.1.$$
     This gives the contradiction:
     $$3 = 3.1.$$
   No point $(x, y)$ can satisfy all three equations simultaneously.
   **System 2 is inconsistent** and has **no solution**.

3. **Explanation of the sensitivity to small perturbations:**
   - In System 1, the three lines are concurrent (all pass through the single point $(1, 1)$). The third equation $3x = 3$ is a linear combination of the first two equations ($(x+y) + (2x-y) = 3x$).
   - Changing the constant from $3$ to $3.1$ in System 2 shifts the vertical line $x = 1$ to $x = 1.0333$. The three lines now form a small triangle instead of meeting at a single point.
   - Because the system has $3$ equations for only $2$ unknowns, consistency requires the right-hand side vector $b = (2, 1, 3.1)^T$ to lie in the 2-dimensional plane spanned by the columns of $A$. Perturbing the vector moves it off this plane into the 3rd dimension, rendering the system inconsistent.

## Verification and Consistency Checks
- Augmented matrix for System 2:
  $$\left[\begin{array}{cc|c} 1 & 1 & 2 \\ 2 & -1 & 1 \\ 3 & 0 & 3.1 \end{array}\right]$$
  Applying $R_2 \leftarrow R_2 - 2R_1$ and $R_3 \leftarrow R_3 - 3R_1$:
  $$\left[\begin{array}{cc|c} 1 & 1 & 2 \\ 0 & -3 & -3 \\ 0 & -3 & -2.9 \end{array}\right]$$
  Applying $R_3 \leftarrow R_3 - R_2$:
  $$\left[\begin{array}{cc|c} 1 & 1 & 2 \\ 0 & -3 & -3 \\ 0 & 0 & 0.1 \end{array}\right]$$
  The last row $[0 \; 0 \mid 0.1]$ states $0 = 0.1$, rigorously proving that System 2 is inconsistent.
