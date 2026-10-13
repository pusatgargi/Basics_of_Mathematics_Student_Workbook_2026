# Problem 2: Gaussian Elimination — One Solution

## Problem Statement
Solve using Gaussian elimination:

$$\begin{cases}x+y+z=6,\\2x-y+z=3,\\x+2y-z=2.\end{cases}$$

After solving, substitute the result into all equations and check consistency.

## Theoretical Background and Concepts
Gaussian elimination systematically solves a linear system by converting its augmented matrix into row-echelon form.
Subtracting multiples of equations removes one unknown without changing the solutions of the system, because each elementary row operation is reversible.
Once in echelon form, back substitution solves the reduced equations in reverse order (from bottom to top). This reverse order is necessary because the lowest non-zero row contains only one unknown; finding it allows us to substitute its value into the row above (which has two unknowns), and so on up to the first equation.

## Detailed Step-by-Step Solution
1. **Set up the augmented matrix $[A \mid b]$:**
   $$\left[\begin{array}{ccc|c} 1 & 1 & 1 & 6 \\ 2 & -1 & 1 & 3 \\ 1 & 2 & -1 & 2 \end{array}\right]$$

2. **Step 1: Eliminate $x$ from rows 2 and 3 using row 1:**
   Subtracting multiples of equation 1 removes unknown $x$ without altering the solution set:
   - $R_2 \leftarrow R_2 - 2R_1$:
     $$R_2 = (2 - 2(1),\; -1 - 2(1),\; 1 - 2(1) \mid 3 - 2(6)) = (0, -3, -1 \mid -9).$$
     Equivalently, multiplying by $-1$ gives: $3y + z = 9$.
   - $R_3 \leftarrow R_3 - R_1$:
     $$R_3 = (1 - 1,\; 2 - 1,\; -1 - 1 \mid 2 - 6) = (0, 1, -2 \mid -4).$$
     This gives: $y - 2z = -4$.

   The system in $y$ and $z$ is:
   $$\begin{cases}3y + z = 9 \\ y - 2z = -4\end{cases}$$

3. **Step 2: Eliminate $y$ from the reduced system:**
   Subtracting $3 \times$ (the second reduced equation) from (the first reduced equation):
   $$(3y + z) - 3(y - 2z) = 9 - 3(-4)$$
   $$3y + z - 3y + 6z = 9 + 12$$
   $$7z = 21 \implies z = 3.$$

4. **Step 3: Back substitution in reverse order:**
   Now solve the reduced equations from bottom to top:
   - Substitute $z = 3$ into the equation $y - 2z = -4$:
     $$y = -4 + 2z = -4 + 2(3) = -4 + 6 = 2.$$
   - Substitute $y = 2$ and $z = 3$ into the first equation $x + y + z = 6$:
     $$x = 6 - y - z = 6 - 2 - 3 = 1.$$

   Thus, the unique solution is:
   $$(x, y, z) = (1, 2, 3).$$

## Verification and Consistency Checks
Substitute $(x, y, z) = (1, 2, 3)$ into all three original equations:
- Equation 1: $1 + 2 + 3 = 6$ (Consistent $\checkmark$)
- Equation 2: $2(1) - 2 + 3 = 2 - 2 + 3 = 3$ (Consistent $\checkmark$)
- Equation 3: $1 + 2(2) - 3 = 1 + 4 - 3 = 2$ (Consistent $\checkmark$)
All three original equations are satisfied, verifying the solution.
