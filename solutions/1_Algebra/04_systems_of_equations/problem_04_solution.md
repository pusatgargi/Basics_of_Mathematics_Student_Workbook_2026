# Problem 4: Infinitely Many Solutions

## Problem Statement
Solve

$$\begin{cases}x+y+z=2,\\2x+2y+2z=4,\\x-y+z=0.\end{cases}$$

Give the solution in parametric form, identify a free variable, and for one chosen parameter value check that the resulting point really satisfies the system.

## Theoretical Background and Concepts
When a consistent system of $m$ linear equations in $n$ variables has rank $r < n$, there are $n - r$ **free variables** (parameters).
- Variables corresponding to columns with leading entries (pivots) are **basic (pivot) variables**.
- Variables corresponding to columns without pivots are **free variables**, which can be assigned arbitrary real values.
The solution set is an affine subspace of dimension $n - r$ (e.g., a line in $\mathbb{R}^3$ when $n-r=1$).

## Detailed Step-by-Step Solution
1. **Set up the augmented matrix $[A \mid b]$:**
   $$\left[\begin{array}{ccc|c} 1 & 1 & 1 & 2 \\ 2 & 2 & 2 & 4 \\ 1 & -1 & 1 & 0 \end{array}\right]$$

2. **Step 1: Eliminate below $a_{11}$ in Column 1:**
   - $R_2 \leftarrow R_2 - 2R_1$:
     $$R_2 = (2 - 2(1),\; 2 - 2(1),\; 2 - 2(1) \mid 4 - 2(2)) = (0, 0, 0 \mid 0).$$
   - $R_3 \leftarrow R_3 - R_1$:
     $$R_3 = (1 - 1,\; -1 - 1,\; 1 - 1 \mid 0 - 2) = (0, -2, 0 \mid -2).$$

   Matrix after Step 1:
   $$\left[\begin{array}{ccc|c} 1 & 1 & 1 & 2 \\ 0 & 0 & 0 & 0 \\ 0 & -2 & 0 & -2 \end{array}\right]$$

3. **Step 2: Reorder rows to obtain echelon form:**
   Swap $R_2 \leftrightarrow R_3$:
   $$\left[\begin{array}{ccc|c} 1 & 1 & 1 & 2 \\ 0 & -2 & 0 & -2 \\ 0 & 0 & 0 & 0 \end{array}\right]$$
   Normalize $R_2 \leftarrow -\frac{1}{2}R_2$:
   $$\left[\begin{array}{ccc|c} 1 & 1 & 1 & 2 \\ 0 & 1 & 0 & 1 \\ 0 & 0 & 0 & 0 \end{array}\right]$$

4. **Identify pivot and free variables:**
   - Pivots are in Column 1 ($x$) and Column 2 ($y$). These are basic variables.
   - Column 3 ($z$) contains no pivot, so **$z$ is the free variable**.
   Let $z = t$, where $t \in \mathbb{R}$ is an arbitrary parameter.

5. **Express variables in parametric form:**
   - From row 2:
     $$y = 1.$$
   - From row 1:
     $$x + y + z = 2 \implies x + 1 + t = 2 \implies x = 1 - t.$$
   - Parametric vector solution:
     $$\begin{pmatrix}x\\y\\z\end{pmatrix} = \begin{pmatrix}1 - t \\ 1 \\ t\end{pmatrix} = \begin{pmatrix}1\\1\\0\end{pmatrix} + t\begin{pmatrix}-1\\0\\1\end{pmatrix},\quad t \in \mathbb{R}.$$

6. **Check for a chosen parameter value ($t = 0$):**
   Setting $t = 0$ yields $(x, y, z) = (1, 1, 0)$.
   Substitute $(1, 1, 0)$ into the original equations:
   - Eq 1: $1 + 1 + 0 = 2$ (True $\checkmark$)
   - Eq 2: $2(1) + 2(1) + 2(0) = 4$ (True $\checkmark$)
   - Eq 3: $1 - 1 + 0 = 0$ (True $\checkmark$)

## Verification and Consistency Checks
- Check another value, e.g., $t = 2 \implies (x, y, z) = (-1, 1, 2)$:
  - Eq 1: $-1 + 1 + 2 = 2$ $\checkmark$
  - Eq 2: $2(-1) + 2(1) + 2(2) = -2 + 2 + 4 = 4$ $\checkmark$
  - Eq 3: $-1 - 1 + 2 = 0$ $\checkmark$
- Rank check: $\text{rank}(A) = \text{rank}[A \mid b] = 2 < 3$. The nullity is $3 - 2 = 1$, confirming a 1-dimensional line of infinitely many solutions.
