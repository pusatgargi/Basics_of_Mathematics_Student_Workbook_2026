# Problem 2: Gaussian Elimination — One Solution

## Problem Statement
Solve using Gaussian elimination:

$$\begin{cases}x+y+z=6,\\2x-y+z=3,\\x+2y-z=2.\end{cases}$$

After solving, substitute the result into all equations and check consistency.

## Theoretical Background and Concepts
Gaussian elimination is an algorithmic method for solving systems of linear equations. It operates on the augmented matrix:
$$[A \mid b]$$
using three types of elementary row operations:
1. Swapping two rows ($R_i \leftrightarrow R_j$).
2. Multiplying a row by a nonzero constant ($R_i \leftarrow cR_i$).
3. Adding a multiple of one row to another ($R_i \leftarrow R_i + cR_j$).

The goal is to convert the matrix into row echelon form (upper triangular form), after which the variables are found systematically by back substitution.

## Detailed Step-by-Step Solution
1. **Set up the augmented matrix $[A \mid b]$:**
   $$\left[\begin{array}{ccc|c} 1 & 1 & 1 & 6 \\ 2 & -1 & 1 & 3 \\ 1 & 2 & -1 & 2 \end{array}\right]$$

2. **Step 1: Eliminate $x$ from rows 2 and 3 using row 1:**
   - $R_2 \leftarrow R_2 - 2R_1$:
     $$R_2 = (2 - 2(1),\; -1 - 2(1),\; 1 - 2(1) \mid 3 - 2(6)) = (0, -3, -1 \mid -9).$$
   - $R_3 \leftarrow R_3 - R_1$:
     $$R_3 = (1 - 1,\; 2 - 1,\; -1 - 1 \mid 2 - 6) = (0, 1, -2 \mid -4).$$

   Augmented matrix:
   $$\left[\begin{array}{ccc|c} 1 & 1 & 1 & 6 \\ 0 & -3 & -1 & -9 \\ 0 & 1 & -2 & -4 \end{array}\right]$$

3. **Step 2: Eliminate $y$ from row 3 using row 2:**
   Multiply $R_2$ by $-1$ or swap rows for simplicity.
   Swap $R_2 \leftrightarrow R_3$:
   $$\left[\begin{array}{ccc|c} 1 & 1 & 1 & 6 \\ 0 & 1 & -2 & -4 \\ 0 & -3 & -1 & -9 \end{array}\right]$$
   Now apply $R_3 \leftarrow R_3 + 3R_2$:
   $$R_3 = (0 + 3(0),\; -3 + 3(1),\; -1 + 3(-2) \mid -9 + 3(-4)) = (0, 0, -7 \mid -21).$$

   Matrix in row echelon form:
   $$\left[\begin{array}{ccc|c} 1 & 1 & 1 & 6 \\ 0 & 1 & -2 & -4 \\ 0 & 0 & -7 & -21 \end{array}\right]$$

4. **Step 3: Back substitution:**
   - From row 3:
     $$-7z = -21 \implies z = \frac{-21}{-7} = 3.$$
   - From row 2:
     $$y - 2z = -4 \implies y - 2(3) = -4 \implies y - 6 = -4 \implies y = 2.$$
   - From row 1:
     $$x + y + z = 6 \implies x + 2 + 3 = 6 \implies x + 5 = 6 \implies x = 1.$$

   The unique solution is:
   $$(x, y, z) = (1, 2, 3).$$

## Verification and Consistency Checks
Substitute $(x, y, z) = (1, 2, 3)$ into all three original equations:
- Equation 1: $x + y + z = 1 + 2 + 3 = 6$. (Matches 6 $\checkmark$)
- Equation 2: $2x - y + z = 2(1) - 2 + 3 = 2 - 2 + 3 = 3$. (Matches 3 $\checkmark$)
- Equation 3: $x + 2y - z = 1 + 2(2) - 3 = 1 + 4 - 3 = 2$. (Matches 2 $\checkmark$)

All three equations are satisfied, verifying that $(1, 2, 3)$ is the correct unique solution.
