# Problem 6: A System with a Parameter — Which Cases Actually Occur?

## Problem Statement
Analyze, depending on the parameter $a$, the system

$$\begin{cases}x+y=2,\\ax+ay=4.\end{cases}$$

Among the three possibilities — exactly one solution, infinitely many solutions, no solution — determine which actually occur and for which values of $a$. If one type cannot occur, explain why.

## Theoretical Background and Concepts
For any linear system of 2 equations in 2 unknowns, the three theoretical cases are:
1. **Unique solution:** Lines intersect at a single point ($\text{rank}(A) = 2$).
2. **Infinitely many solutions:** Lines are identical ($\text{rank}(A) = \text{rank}[A \mid b] = 1$).
3. **No solution:** Lines are parallel and distinct ($\text{rank}(A) = 1 < \text{rank}[A \mid b] = 2$).

The coefficient matrix is:
$$A = \begin{pmatrix}1 & 1 \\ a & a\end{pmatrix}.$$
Notice that its determinant is:
$$\det A = (1)(a) - (1)(a) = a - a = 0 \quad \text{for ALL } a \in \mathbb{R}.$$
Because $\det A = 0$ for every $a$, $\text{rank}(A) \le 1 < 2$. Thus, **the unique solution case can NEVER occur**, regardless of the value of $a$.

## Detailed Step-by-Step Solution
1. **Set up the augmented matrix $[A \mid b]$:**
   $$\left[\begin{array}{cc|c} 1 & 1 & 2 \\ a & a & 4 \end{array}\right]$$

2. **Perform elimination on row 2 ($R_2 \leftarrow R_2 - aR_1$):**
   - Left side: $(a - a(1),\; a - a(1)) = (0, 0)$.
   - Right side: $4 - 2a$.

   Augmented matrix:
   $$\left[\begin{array}{cc|c} 1 & 1 & 2 \\ 0 & 0 & 4 - 2a \end{array}\right]$$

3. **Analyze cases depending on $4 - 2a$:**
   - **Case 1: $4 - 2a = 0 \iff 2a = 4 \iff a = 2$:**
     The second row becomes $[0 \; 0 \mid 0]$.
     The system reduces to the single equation:
     $$x + y = 2.$$
     This describes a single line. There is $2 - 1 = 1$ free variable ($y = t$), giving:
     $$(x, y) = (2 - t, t),\quad t \in \mathbb{R}.$$
     **Outcome:** **Infinitely many solutions** occur when **$a = 2$**.

   - **Case 2: $4 - 2a \neq 0 \iff a \neq 2$:**
     The second row is $[0 \; 0 \mid 4 - 2a]$ with $4 - 2a \neq 0$.
     This gives the contradiction:
     $$0 \cdot x + 0 \cdot y = 4 - 2a \neq 0 \implies 0 = 4 - 2a.$$
     **Outcome:** **No solution** occurs for all **$a \neq 2$**.
     (For example, if $a = 0$: $0 = 4$, no solution; if $a = 1$: $x+y=2$ and $x+y=4$, no solution).

   - **Case 3: Exactly one solution:**
     **Cannot occur** for any value of $a$.
     **Why:** For a $2\times2$ system to have a unique solution, the coefficient matrix must have full rank $2$ (i.e., $\det A \neq 0$). But here, row 2 of $A$ is $(a, a) = a(1, 1)$, which is always collinear with row 1 $(1, 1)$. Thus, $\det A = 0$ for all $a$, meaning the rank of $A$ is at most $1$. Since $\text{rank}(A) < 2$, the system can never have a unique solution.

## Verification and Consistency Checks
- When $a = 2$: $2x + 2y = 4$ is equivalent to $x + y = 2$. Both equations represent the same line, yielding infinitely many solutions.
- When $a = 0$: $0x + 0y = 4 \implies 0 = 4$, no solution.
- When $a = 3$: $3x + 3y = 4 \implies x + y = 4/3 \neq 2$, no solution.
- The classification is complete: $a=2$ gives infinitely many solutions, $a \neq 2$ gives no solution, and exactly one solution never occurs.
