# Problem 1: From a System to a Matrix

## Problem Statement
Write the system

$$\begin{cases}2x-y+z=4,\\x+3y-2z=1,\\3x+y+z=7\end{cases}$$

in the form $Ax=b$.
Identify the coefficient matrix, the vector of unknowns, and the right-hand side vector. Explain how each row of the matrix corresponds to one equation.

## Theoretical Background and Concepts
A system of $m$ linear equations in $n$ unknowns can be represented compactly as a single matrix equation:

$$Ax = b,$$

where:
- $A \in \mathbb{R}^{m \times n}$ is the **coefficient matrix**, containing the coefficients of each unknown.
- $x \in \mathbb{R}^{n}$ is the **vector of unknowns**.
- $b \in \mathbb{R}^{m}$ is the **right-hand side vector** of constant terms.

By the definition of matrix-vector multiplication, the $i$-th entry of the product $Ax$ is the dot product of the $i$-th row of $A$ with the vector $x$:
$$(Ax)_i = \sum_{j=1}^n a_{ij} x_j = a_{i1} x_1 + a_{i2} x_2 + \dots + a_{in} x_n.$$
Setting this equal to $b_i$ reproduces the $i$-th equation of the system:
$$a_{i1} x_1 + a_{i2} x_2 + \dots + a_{in} x_n = b_i.$$
Thus, each row of matrix $A$, together with the corresponding entry of $b$, encodes exactly one equation.

## Detailed Step-by-Step Solution
1. **Identify the components:**
   - Unknowns: $x, y, z$, so the vector of unknowns is:
     $$\mathbf{x} = \begin{pmatrix}x\\y\\z\end{pmatrix}.$$
   - Equation 1: $2x - 1y + 1z = 4 \implies$ coefficients $(2, -1, 1)$, constant $4$.
   - Equation 2: $1x + 3y - 2z = 1 \implies$ coefficients $(1, 3, -2)$, constant $1$.
   - Equation 3: $3x + 1y + 1z = 7 \implies$ coefficients $(3, 1, 1)$, constant $7$.

2. **Assemble the matrix form $Ax = b$:**
   - Coefficient matrix $A$:
     $$A = \begin{pmatrix}2 & -1 & 1 \\ 1 & 3 & -2 \\ 3 & 1 & 1\end{pmatrix}.$$
   - Right-hand side vector $b$:
     $$b = \begin{pmatrix}4\\1\\7\end{pmatrix}.$$

   The complete matrix equation is:
   $$\begin{pmatrix}2 & -1 & 1 \\ 1 & 3 & -2 \\ 3 & 1 & 1\end{pmatrix} \begin{pmatrix}x\\y\\z\end{pmatrix} = \begin{pmatrix}4\\1\\7\end{pmatrix}.$$

3. **Explanation of the correspondence:**
   Multiplying row-by-column:
   - Row 1: $(2)(x) + (-1)(y) + (1)(z) = 4 \iff 2x - y + z = 4$.
   - Row 2: $(1)(x) + (3)(y) + (-2)(z) = 1 \iff x + 3y - 2z = 1$.
   - Row 3: $(3)(x) + (1)(y) + (1)(z) = 7 \iff 3x + y + z = 7$.
   Each row of the coefficient matrix contains the weights of the variables for that specific equation, and the corresponding component of $b$ represents the scalar target value.

## Verification and Consistency Checks
- Dimension check: $A$ is $3\times3$, $x$ is $3\times1$, and $b$ is $3\times1$. The multiplication $(3\times3)(3\times1)$ is valid and results in a $(3\times1)$ column vector matching $b$.
- Re-expanding the matrix product $Ax$ recovers the three original equations without loss or alteration of terms.
