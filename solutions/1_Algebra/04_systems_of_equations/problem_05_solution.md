# Problem 5: Row Echelon Form and Number of Solutions

## Problem Statement
For the augmented matrix

$$\left[\begin{array}{ccc|c}1&2&-1&3\\0&1&2&1\\0&0&0&0\end{array}\right]$$

determine the number of solutions and write them in parametric form. Explain how you know how many variables may be chosen freely.

## Theoretical Background and Concepts
A **pivot** is the leading non-zero entry in a non-zero row of a matrix in row-echelon form.
- The columns containing pivots correspond to **basic (pivot) variables**.
- The columns without pivots correspond to **free variables**.
- The number of free variables is given by:
  $$\text{Number of free variables} = (\text{total unknowns } n) - (\text{number of pivots } r).$$
If the system is consistent and has at least one free variable ($n - r > 0$), it has **infinitely many solutions**.

## Detailed Step-by-Step Solution
1. **Analyze the augmented matrix:**
   $$\left[\begin{array}{ccc|c}1&2&-1&3\\0&1&2&1\\0&0&0&0\end{array}\right]$$
   - Total unknowns: $n = 3$ ($x_1, x_2, x_3$).
   - Pivots:
     - Row 1 has leading entry $1$ in column 1 (pivot variable $x_1$).
     - Row 2 has leading entry $1$ in column 2 (pivot variable $x_2$).
     - Row 3 is completely zero: $[0 \; 0 \; 0 \mid 0]$, representing $0 = 0$ (no contradiction).
   - Number of pivots: $r = 2$.
   - Column 3 contains no pivot.

2. **Determine the number of free variables and solutions:**
   $$\text{Number of free variables} = n - r = 3 - 2 = 1.$$
   Because column 3 has no pivot, variable $x_3$ can be chosen freely as any real number.
   Therefore, the system has **infinitely many solutions, with one free variable**.

3. **Parametric solution:**
   Let $x_3 = t \in \mathbb{R}$.
   - From Row 2:
     $$x_2 + 2x_3 = 1 \implies x_2 + 2t = 1 \implies x_2 = 1 - 2t.$$
   - From Row 1:
     $$x_1 + 2x_2 - x_3 = 3 \implies x_1 + 2(1 - 2t) - t = 3$$
     $$x_1 + 2 - 4t - t = 3 \implies x_1 - 5t = 1 \implies x_1 = 1 + 5t.$$

   In vector parametric form:
   $$\begin{pmatrix}x_1\\x_2\\x_3\end{pmatrix} = \begin{pmatrix}1 + 5t \\ 1 - 2t \\ t\end{pmatrix} = \begin{pmatrix}1\\1\\0\end{pmatrix} + t\begin{pmatrix}5\\-2\\1\end{pmatrix},\quad t \in \mathbb{R}.$$

## Verification and Consistency Checks
Test with $t = 0 \implies (x_1, x_2, x_3) = (1, 1, 0)$:
- Row 1: $1(1) + 2(1) - 1(0) = 1 + 2 = 3$ $\checkmark$
- Row 2: $0(1) + 1(1) + 2(0) = 1$ $\checkmark$
Test with $t = 1 \implies (x_1, x_2, x_3) = (6, -1, 1)$:
- Row 1: $1(6) + 2(-1) - 1(1) = 6 - 2 - 1 = 3$ $\checkmark$
- Row 2: $0(6) + 1(-1) + 2(1) = -1 + 2 = 1$ $\checkmark$
The parametric solution satisfies the system for all $t$.
