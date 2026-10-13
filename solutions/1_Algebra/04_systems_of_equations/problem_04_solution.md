# Problem 4: Infinitely Many Solutions

## Problem Statement
Solve

$$\begin{cases}x+y+z=2,\\2x+2y+2z=4,\\x-y+z=0.\end{cases}$$

Give the solution in parametric form, identify a free variable, and for one chosen parameter value check that the resulting point really satisfies the system.

## Theoretical Background and Concepts
When a consistent linear system has fewer independent equations (rank $r$) than unknowns ($n$), there are $n - r$ free variables.
A **free variable** is an unknown that may be chosen to be any arbitrary real number, while the remaining basic variables are determined in terms of it. The solution set is an infinite family of points forming an affine subspace (such as a line in $\mathbb{R}^3$).

## Detailed Step-by-Step Solution
1. **Set up the augmented matrix $[A \mid b]$:**
   $$\left[\begin{array}{ccc|c} 1 & 1 & 1 & 2 \\ 2 & 2 & 2 & 4 \\ 1 & -1 & 1 & 0 \end{array}\right]$$

2. **Elimination:**
   - Equation 2 is exactly twice equation 1 ($R_2 = 2R_1$).
     Applying $R_2 \leftarrow R_2 - 2R_1$ gives the zero row $[0 \; 0 \; 0 \mid 0]$, confirming that equation 2 is redundant.
   - Subtract equation 1 from equation 3 ($R_3 \leftarrow R_3 - R_1$):
     $$(1-1,\; -1-1,\; 1-1 \mid 0-2) = (0, -2, 0 \mid -2).$$
     This gives:
     $$-2y = -2 \implies y = 1.$$

3. **Identify the free variable and parametric form:**
   Substitute $y = 1$ back into the first equation $x + y + z = 2$:
   $$x + 1 + z = 2 \implies x + z = 1 \implies x = 1 - z.$$
   Here, $z$ may be any arbitrary real number $t \in \mathbb{R}$.
   Because $z$ is not constrained by any equation, **$z$ is the free variable**.
   Setting $z = t$, the parametric solution is:
   $$\begin{pmatrix}x\\y\\z\end{pmatrix} = \begin{pmatrix}1 - t \\ 1 \\ t\end{pmatrix} = \begin{pmatrix}1\\1\\0\end{pmatrix} + t\begin{pmatrix}-1\\0\\1\end{pmatrix},\quad t \in \mathbb{R}.$$
   The system has **infinitely many solutions**, parameterized by $t$.

4. **Check for a chosen parameter value ($t = 0$):**
   Setting $t = 0$ gives the particular point $(x, y, z) = (1, 1, 0)$.
   Substitute $(1, 1, 0)$ into all three original equations:
   - Equation 1: $1 + 1 + 0 = 2$ (Satisfied $\checkmark$)
   - Equation 2: $2(1) + 2(1) + 2(0) = 4$ (Satisfied $\checkmark$)
   - Equation 3: $1 - 1 + 0 = 0$ (Satisfied $\checkmark$)

## Verification and Consistency Checks
- Check another value, e.g. $t = 3 \implies (x, y, z) = (-2, 1, 3)$:
  - Eq 1: $-2 + 1 + 3 = 2$ $\checkmark$
  - Eq 2: $2(-2) + 2(1) + 2(3) = -4 + 2 + 6 = 4$ $\checkmark$
  - Eq 3: $-2 - 1 + 3 = 0$ $\checkmark$
The parametric family satisfies the entire system for every choice of $t \in \mathbb{R}$.
