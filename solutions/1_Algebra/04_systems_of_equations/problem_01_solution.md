# Problem 1: From a System to a Matrix

## Problem Statement
Write the system

$$\begin{cases}2x-y+z=4,\\x+3y-2z=1,\\3x+y+z=7\end{cases}$$

in the form $Ax=b$.
Identify the coefficient matrix, the vector of unknowns, and the right-hand side vector. Explain how each row of the matrix corresponds to one equation.

## Theoretical Background and Concepts
A system of $m$ linear equations in $n$ unknowns can be written as a single matrix equation:

$$Ax = b,$$

where:
- $A \in \mathbb{R}^{m \times n}$ is the coefficient matrix containing the coefficients of the unknowns.
- $x \in \mathbb{R}^n$ is the column vector of unknowns.
- $b \in \mathbb{R}^m$ is the right-hand side column vector of constants.

By the row-by-column rule of matrix-vector multiplication, the $i$-th entry of the product $Ax$ is the dot product of row $i$ of $A$ and the vector $x$:
$$(Ax)_i = a_{i1}x_1 + a_{i2}x_2 + \dots + a_{in}x_n.$$
Setting this equal to $b_i$ reproduces the $i$-th equation of the system.

## Detailed Step-by-Step Solution
1. **Identify the components:**
   - Vector of unknowns:
     $$x = \begin{pmatrix}x\\y\\z\end{pmatrix}.$$
   - Coefficient matrix $A$:
     - Row 1 (from $2x - 1y + 1z$): $(2, -1, 1)$
     - Row 2 (from $1x + 3y - 2z$): $(1, 3, -2)$
     - Row 3 (from $3x + 1y + 1z$): $(3, 1, 1)$
     $$A = \begin{pmatrix}2 & -1 & 1 \\ 1 & 3 & -2 \\ 3 & 1 & 1\end{pmatrix}.$$
   - Right-hand side vector $b$:
     $$b = \begin{pmatrix}4\\1\\7\end{pmatrix}.$$

2. **Assemble the matrix equation $Ax = b$:**
   $$\begin{pmatrix}2 & -1 & 1 \\ 1 & 3 & -2 \\ 3 & 1 & 1\end{pmatrix}\begin{pmatrix}x\\y\\z\end{pmatrix} = \begin{pmatrix}4\\1\\7\end{pmatrix}.$$

3. **Correspondence between rows and equations:**
   Each row of $A$ contains the coefficients multiplying the variables $x, y, z$ in that specific equation:
   - Row 1: $2x + (-1)y + 1z = 4 \iff 2x - y + z = 4$.
   - Row 2: $1x + 3y + (-2)z = 1 \iff x + 3y - 2z = 1$.
   - Row 3: $3x + 1y + 1z = 7 \iff 3x + y + z = 7$.
   Thus, row $i$ of the matrix equation pairs the linear combination of unknowns with the scalar constant $b_i$, representing equation $i$ exactly.

## Verification and Consistency Checks
Carrying out the matrix multiplication:
$$Ax = \begin{pmatrix}2x - y + z \\ x + 3y - 2z \\ 3x + y + z\end{pmatrix}.$$
Equating this with $b = \begin{pmatrix}4\\1\\7\end{pmatrix}$ returns the original three equations with identical signs and coefficients.
