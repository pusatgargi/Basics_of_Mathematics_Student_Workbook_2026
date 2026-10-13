# Problem 8: Two Systems with the Same Coefficient Matrix

## Problem Statement
Solve by elimination the two systems

$$\begin{cases}2x+y=5,\\x-y=1,\end{cases}\qquad \begin{cases}2x+y=1,\\x-y=4.\end{cases}$$

Compare the successive elimination steps. Which part of the calculation is the same in both cases, and why?

## Theoretical Background and Concepts
In any linear system $Ax = b$, the elementary row operations used in Gaussian elimination are determined strictly by the entries of the coefficient matrix $A$.
When solving multiple systems that share the same coefficient matrix $A$ but have different right-hand sides $b_1, b_2$:
1. The exact same row operations transform $A$ into upper triangular form in both cases.
2. The systems can be solved simultaneously by augmenting $A$ with multiple right-hand columns:
   $$[A \mid b_1 \mid b_2].$$
This separates the transformation of the structure of the equations from the specific values of the targets.

## Detailed Step-by-Step Solution
1. **Solve simultaneously using double augmentation $[A \mid b_1 \mid b_2]$:**
   $$\left[\begin{array}{cc|cc} 2 & 1 & 5 & 1 \\ 1 & -1 & 1 & 4 \end{array}\right]$$

2. **Step 1: Swap rows $R_1 \leftrightarrow R_2$ for a leading 1 pivot:**
   $$\left[\begin{array}{cc|cc} 1 & -1 & 1 & 4 \\ 2 & 1 & 5 & 1 \end{array}\right]$$

3. **Step 2: Eliminate below the pivot ($R_2 \leftarrow R_2 - 2R_1$):**
   - Left side: $(2 - 2(1),\; 1 - 2(-1)) = (0, 3)$.
   - Column $b_1$: $5 - 2(1) = 3$.
   - Column $b_2$: $1 - 2(4) = -7$.

   The transformed matrix is:
   $$\left[\begin{array}{cc|cc} 1 & -1 & 1 & 4 \\ 0 & 3 & 3 & -7 \end{array}\right]$$

4. **Solve System 1 ($b_1$):**
   $$\begin{cases}x - y = 1 \\ 3y = 3\end{cases}$$
   - From row 2: $3y = 3 \implies y = 1$.
   - From row 1: $x - 1 = 1 \implies x = 2$.
   **Solution to System 1:** $(x, y) = (2, 1)$.

5. **Solve System 2 ($b_2$):**
   $$\begin{cases}x - y = 4 \\ 3y = -7\end{cases}$$
   - From row 2: $3y = -7 \implies y = -\frac{7}{3}$.
   - From row 1: $x - \left(-\frac{7}{3}\right) = 4 \implies x + \frac{7}{3} = \frac{12}{3} \implies x = \frac{5}{3}$.
   **Solution to System 2:** $(x, y) = \left(\frac{5}{3}, -\frac{7}{3}\right)$.

6. **Comparison and Explanation:**
   - **Which part is the same:** All row operations performed on the left-hand block (the row swap and $R_2 \leftarrow R_2 - 2R_1$) were completely identical in both calculations. The resulting triangular matrix coefficients $\begin{pmatrix}1&-1\\0&3\end{pmatrix}$ are the same.
   - **Why:** The choice of pivots, multipliers, and row operations depends solely on the coefficient matrix $A$. The right-hand side vectors simply follow along through the operations without influencing which operations are chosen.

## Verification and Consistency Checks
- Verify System 1 with $(2, 1)$:
  - $2(2) + 1 = 5$ (Matches 5 $\checkmark$)
  - $2 - 1 = 1$ (Matches 1 $\checkmark$)
- Verify System 2 with $(5/3, -7/3)$:
  - $2(5/3) + (-7/3) = 10/3 - 7/3 = 3/3 = 1$ (Matches 1 $\checkmark$)
  - $5/3 - (-7/3) = 12/3 = 4$ (Matches 4 $\checkmark$)
Both solutions satisfy their respective systems perfectly.
