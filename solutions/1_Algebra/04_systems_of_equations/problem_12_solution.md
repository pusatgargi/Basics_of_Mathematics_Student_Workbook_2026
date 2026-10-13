# Problem 12: Homogeneous System

## Problem Statement
Solve

$$\begin{cases}x+2y-z=0,\\2x+4y-2z=0,\\x-y+2z=0.\end{cases}$$

Give all solutions in parametric form and explain why $(0,0,0)$ always satisfies a homogeneous system.

## Theoretical Background and Concepts
A system of linear equations is **homogeneous** when all constant terms on the right-hand side are zero:

$$Ax = 0.$$

1. **Trivial solution:** The zero vector $x = 0$ is always a solution because matrix multiplication satisfies $A \cdot 0 = 0$ for any matrix $A$. Thus, a homogeneous system is **never inconsistent**.
2. **Non-trivial solutions:** Non-trivial (non-zero) solutions exist if and only if $\text{rank}(A) < n$ (or equivalently for square systems, $\det A = 0$). The solution space is the **null space (kernel)** of $A$, which forms a vector subspace of $\mathbb{R}^n$.

## Detailed Step-by-Step Solution
1. **Set up the coefficient matrix:**
   $$A = \begin{pmatrix}1 & 2 & -1 \\ 2 & 4 & -2 \\ 1 & -1 & 2\end{pmatrix}.$$
   (We omit the zero column in the augmented matrix since row operations on zeros always yield zero).

2. **Step 1: Eliminate below $a_{11}$ in Column 1:**
   - $R_2 \leftarrow R_2 - 2R_1$:
     $$R_2 = (2 - 2(1),\; 4 - 2(2),\; -2 - 2(-1)) = (0, 0, 0).$$
   - $R_3 \leftarrow R_3 - R_1$:
     $$R_3 = (1 - 1,\; -1 - 2,\; 2 - (-1)) = (0, -3, 3).$$

   Matrix after Step 1:
   $$\begin{pmatrix}1 & 2 & -1 \\ 0 & 0 & 0 \\ 0 & -3 & 3\end{pmatrix}.$$

3. **Step 2: Reorder rows and normalize:**
   Swap $R_2 \leftrightarrow R_3$:
   $$\begin{pmatrix}1 & 2 & -1 \\ 0 & -3 & 3 \\ 0 & 0 & 0\end{pmatrix}.$$
   Scale $R_2 \leftarrow -\frac{1}{3}R_2$:
   $$\begin{pmatrix}1 & 2 & -1 \\ 0 & 1 & -1 \\ 0 & 0 & 0\end{pmatrix}.$$

4. **Identify pivot and free variables:**
   - Pivots: Column 1 ($x$) and Column 2 ($y$).
   - Free variable: Column 3 ($z$) has no pivot.
   Let $z = t \in \mathbb{R}$.

5. **Solve for basic variables:**
   - From Row 2:
     $$y - z = 0 \implies y = z = t.$$
   - From Row 1:
     $$x + 2y - z = 0 \implies x + 2(t) - t = 0 \implies x + t = 0 \implies x = -t.$$

6. **Write solution in parametric form:**
   $$\begin{pmatrix}x\\y\\z\end{pmatrix} = \begin{pmatrix}-t \\ t \\ t\end{pmatrix} = t \begin{pmatrix}-1 \\ 1 \\ 1\end{pmatrix},\quad t \in \mathbb{R}.$$

7. **Why $(0,0,0)$ always satisfies a homogeneous system:**
   In any linear equation $a_1 x_1 + \dots + a_n x_n = 0$, evaluating at $(x_1, \dots, x_n) = (0, \dots, 0)$ gives:
   $$a_1(0) + a_2(0) + \dots + a_n(0) = 0 + 0 + \dots + 0 = 0.$$
   In matrix terms, by the linearity of matrix multiplication, $A \cdot \mathbf{0} = \mathbf{0}$. Therefore, the trivial solution $\mathbf{0} = (0, 0, 0)^T$ is unconditionally an element of the solution set of every homogeneous system. Setting the parameter $t = 0$ in our parametric solution recovers this trivial solution directly.

## Verification and Consistency Checks
Substitute the general solution $(-t, t, t)$ into the original equations:
- Eq 1: $(-t) + 2(t) - (t) = -t + 2t - t = 0$ $\checkmark$
- Eq 2: $2(-t) + 4(t) - 2(t) = -2t + 4t - 2t = 0$ $\checkmark$
- Eq 3: $(-t) - (t) + 2(t) = -2t + 2t = 0$ $\checkmark$
All three equations hold identically for all $t \in \mathbb{R}$.
