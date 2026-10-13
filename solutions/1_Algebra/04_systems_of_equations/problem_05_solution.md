# Problem 5: Row Echelon Form and Number of Solutions

## Problem Statement
For the augmented matrix

$$\left[\begin{array}{ccc|c}1&2&-1&3\\0&1&2&1\\0&0&0&0\end{array}\right]$$

determine the number of solutions and write them in parametric form. Explain how you know how many variables may be chosen freely.

## Theoretical Background and Concepts
In a system of linear equations with augmented matrix $[A \mid b]$ in row echelon form:
1. **Consistency:** If there is no row of the form $[0 \; 0 \; \dots \; 0 \mid c]$ with $c \neq 0$, the system is consistent.
2. **Pivots and Rank:** The number of leading non-zero entries (pivots) equals the rank $r$ of the coefficient matrix.
3. **Free Variables:** If the system has $n$ unknowns and rank $r$:
   $$\text{Number of free variables} = n - r.$$
   - If $r = n$, there are no free variables, and the solution is unique.
   - If $r < n$, there are $n - r > 0$ free variables, which can take any real value, yielding **infinitely many solutions**.

## Detailed Step-by-Step Solution
1. **Analyze the augmented matrix:**
   $$\left[\begin{array}{ccc|c}1&2&-1&3\\0&1&2&1\\0&0&0&0\end{array}\right]$$
   - Number of unknowns: $n = 3$ ($x_1, x_2, x_3$).
   - Pivots:
     - Row 1: Pivot is in Column 1 (entry $1$).
     - Row 2: Pivot is in Column 2 (entry $1$).
     - Row 3: All zeros (both left and right sides).
   - The rank is $r = 2$.
   - The bottom row $[0 \; 0 \; 0 \mid 0]$ represents $0 = 0$, so the system is consistent.

2. **Determine the number of free variables:**
   $$\text{Number of free variables} = n - r = 3 - 2 = 1.$$
   Column 3 contains no pivot, which means variable $x_3$ can be chosen completely freely.
   Because there is 1 free variable that can take any value in $\mathbb{R}$, the system has **infinitely many solutions**.

3. **Express the solutions in parametric form:**
   Let $x_3 = t \in \mathbb{R}$ be the free parameter.
   - From Row 2:
     $$x_2 + 2x_3 = 1 \implies x_2 + 2t = 1 \implies x_2 = 1 - 2t.$$
   - From Row 1:
     $$x_1 + 2x_2 - x_3 = 3$$
     Substitute $x_2 = 1 - 2t$ and $x_3 = t$:
     $$x_1 + 2(1 - 2t) - t = 3$$
     $$x_1 + 2 - 4t - t = 3$$
     $$x_1 + 2 - 5t = 3 \implies x_1 = 1 + 5t.$$

4. **Vector parametric form:**
   $$x = \begin{pmatrix}x_1\\x_2\\x_3\end{pmatrix} = \begin{pmatrix}1 + 5t \\ 1 - 2t \\ t\end{pmatrix} = \begin{pmatrix}1\\1\\0\end{pmatrix} + t \begin{pmatrix}5\\-2\\1\end{pmatrix},\quad t \in \mathbb{R}.$$

## Verification and Consistency Checks
- Test particular solution with $t = 0$: $x = (1, 1, 0)^T$.
  - Row 1: $1(1) + 2(1) - 1(0) = 1 + 2 = 3$ (Matches 3 $\checkmark$)
  - Row 2: $0(1) + 1(1) + 2(0) = 1$ (Matches 1 $\checkmark$)
- Test homogeneous direction with $v = (5, -2, 1)^T$:
  - Row 1: $1(5) + 2(-2) - 1(1) = 5 - 4 - 1 = 0$ $\checkmark$
  - Row 2: $0(5) + 1(-2) + 2(1) = -2 + 2 = 0$ $\checkmark$
Since $Av = 0$ and $A x_0 = b$, the solution set $x_0 + t v$ is fully verified.
