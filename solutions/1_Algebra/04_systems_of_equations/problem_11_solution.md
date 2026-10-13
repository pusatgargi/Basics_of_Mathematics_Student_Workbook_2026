# Problem 11: A Parameter in a System of Three Equations

## Problem Statement
Analyze the number of solutions depending on $t$:

$$\begin{cases}x+y+z=1,\\x+ty+z=2,\\x+y+tz=3.\end{cases}$$

Use elimination and separately analyze the parameter values for which a standard calculation step ceases to be valid.

## Theoretical Background and Concepts
In systems with a parameter, standard Gaussian elimination row operations are applied to isolate pivots.
However, row operations involving division or multiplication by algebraic expressions like $(t - 1)$ are only valid when that expression is non-zero ($t - 1 \neq 0$).
When an expression becomes zero, it represents a critical bifurcation value of the parameter where:
- The pivot vanishes.
- The rank of the system drops.
- The system must be investigated separately to check whether it becomes inconsistent ($0 = c$, $c \neq 0$) or indeterminate ($0 = 0$).

## Detailed Step-by-Step Solution
1. **Set up the augmented matrix $[A \mid b]$:**
   $$\left[\begin{array}{ccc|c} 1 & 1 & 1 & 1 \\ 1 & t & 1 & 2 \\ 1 & 1 & t & 3 \end{array}\right]$$

2. **Step 1: Eliminate $x$ from rows 2 and 3 using row 1:**
   Apply $R_2 \leftarrow R_2 - R_1$ and $R_3 \leftarrow R_3 - R_1$:
   - For $R_2$:
     $$(1 - 1,\; t - 1,\; 1 - 1 \mid 2 - 1) = (0,\; t - 1,\; 0 \mid 1).$$
   - For $R_3$:
     $$(1 - 1,\; 1 - 1,\; t - 1 \mid 3 - 1) = (0,\; 0,\; t - 1 \mid 2).$$

   The transformed matrix is:
   $$\left[\begin{array}{ccc|c} 1 & 1 & 1 & 1 \\ 0 & t - 1 & 0 & 1 \\ 0 & 0 & t - 1 & 2 \end{array}\right]$$

3. **Analyze the critical parameter value $t = 1$:**
   Notice that the pivot elements in both row 2 and row 3 are $(t - 1)$.
   Division by $(t - 1)$ ceases to be valid when $t = 1$.
   Substitute $t = 1$ directly into the transformed matrix:
   $$\left[\begin{array}{ccc|c} 1 & 1 & 1 & 1 \\ 0 & 0 & 0 & 1 \\ 0 & 0 & 0 & 2 \end{array}\right]$$
   Row 2 states:
   $$0 \cdot x + 0 \cdot y + 0 \cdot z = 1 \implies 0 = 1.$$
   This is an explicit contradiction.
   Therefore, for **$t = 1$**, the system is inconsistent and has **no solution**.

4. **Analyze when $t \neq 1$:**
   When $t \neq 1$, $t - 1 \neq 0$, so both pivots are non-zero.
   The matrix is in full rank upper triangular echelon form with $3$ pivots.
   - From row 2:
     $$(t - 1)y = 1 \implies y = \frac{1}{t - 1}.$$
   - From row 3:
     $$(t - 1)z = 2 \implies z = \frac{2}{t - 1}.$$
   - From row 1:
     $$x + y + z = 1 \implies x = 1 - y - z = 1 - \frac{1}{t - 1} - \frac{2}{t - 1} = 1 - \frac{3}{t - 1} = \frac{(t - 1) - 3}{t - 1} = \frac{t - 4}{t - 1}.$$

   Thus, for every **$t \neq 1$**, the system has **exactly one unique solution**:
   $$(x, y, z) = \left(\frac{t - 4}{t - 1},\; \frac{1}{t - 1},\; \frac{2}{t - 1}\right).$$

5. **Summary of cases:**
   - If $t = 1$: **No solution** (inconsistent).
   - If $t \neq 1$: **Exactly one solution** (unique).
   - (The case of infinitely many solutions does not occur for any value of $t$).

## Verification and Consistency Checks
- Determinant check on the coefficient matrix:
  $$\det A = \det\begin{pmatrix}1&1&1\\0&t-1&0\\0&0&t-1\end{pmatrix} = 1 \cdot (t - 1) \cdot (t - 1) = (t - 1)^2.$$
  - For $t \neq 1$, $\det A = (t-1)^2 \neq 0$, confirming the unique solution exists.
  - For $t = 1$, $\det A = 0$, confirming the system is singular.
- Substitute the computed solution into equation 2 when $t \neq 1$:
  $$x + ty + z = \frac{t - 4}{t - 1} + t\left(\frac{1}{t - 1}\right) + \frac{2}{t - 1} = \frac{t - 4 + t + 2}{t - 1} = \frac{2t - 2}{t - 1} = \frac{2(t - 1)}{t - 1} = 2.$$
  This matches the RHS of equation 2 perfectly.
