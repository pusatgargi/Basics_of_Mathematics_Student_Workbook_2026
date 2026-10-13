# Problem 8: Two Systems with the Same Coefficient Matrix

## Problem Statement
Solve by elimination the two systems

$$\begin{cases}2x+y=5,\\x-y=1,\end{cases}\qquad \begin{cases}2x+y=1,\\x-y=4.\end{cases}$$

Compare the successive elimination steps. Which part of the calculation is the same in both cases, and why?

## Theoretical Background and Concepts
When two systems share the exact same coefficient matrix $A$, the row operations that eliminate the unknowns depend only on the entries of $A$.
Both systems can be solved simultaneously by augmenting $A$ with both right-hand sides: $[A \mid b_1 \mid b_2]$.

## Detailed Step-by-Step Solution
1. **Set up the combined augmented matrix $[A \mid b_1 \mid b_2]$:**
   $$\left[\begin{array}{cc|cc} 2 & 1 & 5 & 1 \\ 1 & -1 & 1 & 4 \end{array}\right]$$

2. **Elimination step:**
   Subtract $2 \times$ row 2 from row 1 ($R_1 \leftarrow R_1 - 2R_2$), or equivalently $R_2 \leftarrow 2R_2 - R_1$:
   Applying $2R_2 - R_1$ cancels $x$ because:
   $$2(1) - 2 = 0.$$
   For the remaining entries:
   - Unknown $y$: $2(-1) - 1 = -3$, translating the row to $-3y$.
   - Right-hand side 1: $2(1) - 5 = -3$.
   - Right-hand side 2: $2(4) - 1 = 7$.

   The second row translates to:
   $$-3y = -3 \quad (\text{for system 1}),\qquad -3y = 7 \quad (\text{for system 2}).$$

3. **Back substitution for System 1:**
   - From $-3y = -3$: $y = 1$.
   - Substitute $y = 1$ into equation 1 ($2x + y = 5$):
     $$2x + 1 = 5 \implies 2x = 4 \implies x = 2.$$
   **Solution 1:** $(x, y) = (2, 1)$.

4. **Back substitution for System 2:**
   - From $-3y = 7$: $y = -\frac{7}{3}$.
   - Substitute $y = -\frac{7}{3}$ into equation 1 ($2x + y = 1$):
     $$2x - \frac{7}{3} = 1 \implies 2x = 1 + \frac{7}{3} = \frac{10}{3} \implies x = \frac{5}{3}.$$
   **Solution 2:** $(x, y) = \left(\frac{5}{3}, -\frac{7}{3}\right)$.

5. **Comparison of elimination steps:**
   - **What is the same:** The row operations and left-hand coefficients ($2x+y$ and $-3y$) are identical in both cases.
   - **Why:** The operations chosen to eliminate $x$ depend solely on the coefficient matrix $A$. The right-hand sides simply carry through the exact same arithmetic operations.

## Verification and Consistency Checks
- System 1 check: $2(2) + 1 = 5$ and $2 - 1 = 1$ $\checkmark$
- System 2 check: $2(5/3) - 7/3 = 3/3 = 1$ and $5/3 - (-7/3) = 12/3 = 4$ $\checkmark$
Both solutions are confirmed.
