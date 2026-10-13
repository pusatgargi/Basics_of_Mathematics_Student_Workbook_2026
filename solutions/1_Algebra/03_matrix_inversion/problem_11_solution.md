# Problem 11: Parameter and Invertibility

## Problem Statement
For

$$A(t)=\begin{pmatrix}1&t\\t&1\end{pmatrix}$$

find all $t$ for which the matrix is invertible, and then give a formula for $A(t)^{-1}$. Explain what happens to this formula at the excluded values.

## Theoretical Background and Concepts
For a symmetric parameterized $2\times2$ matrix:
$$A(t) = \begin{pmatrix}a & b \\ c & d\end{pmatrix} = \begin{pmatrix}1 & t \\ t & 1\end{pmatrix},$$
its determinant is:
$$\det A(t) = ad - bc = 1 - t^2.$$
The matrix is invertible if and only if $\det A(t) \neq 0$, which is equivalent to $t^2 \neq 1$, i.e., $t \neq \pm 1$.
The explicit formula for the inverse is:
$$A(t)^{-1} = \frac{1}{\det A(t)} \begin{pmatrix}1 & -t \\ -t & 1\end{pmatrix}.$$

## Detailed Step-by-Step Solution
1. **Determine invertibility condition:**
   Compute the determinant:
   $$\det A(t) = (1)(1) - (t)(t) = 1 - t^2.$$
   The matrix is invertible if and only if:
   $$1 - t^2 \neq 0 \implies t^2 \neq 1 \implies t \neq 1 \quad \text{and} \quad t \neq -1.$$
   Thus, $A(t)$ is invertible for all $t \in \mathbb{R} \setminus \{-1, 1\}$.

2. **Give the formula for $A(t)^{-1}$:**
   For $t \neq \pm 1$:
   $$A(t)^{-1} = \frac{1}{1 - t^2} \begin{pmatrix}1 & -t \\ -t & 1\end{pmatrix}.$$

3. **Explain what happens at the excluded values ($t = 1$ and $t = -1$):**
   - **At $t = 1$:**
     The matrix becomes:
     $$A(1) = \begin{pmatrix}1 & 1 \\ 1 & 1\end{pmatrix}.$$
     The two rows are identical ($R_1 = R_2$). In the formula, the factor $\frac{1}{1 - t^2}$ becomes $\frac{1}{0}$, which is undefined (division by zero). Geometrically, $A(1)$ projects $\mathbb{R}^2$ onto the line $y = x$, losing one dimension.
   - **At $t = -1$:**
     The matrix becomes:
     $$A(-1) = \begin{pmatrix}1 & -1 \\ -1 & 1\end{pmatrix}.$$
     The rows are negatives of each other ($R_2 = -R_1$). Again, $\frac{1}{1 - (-1)^2} = \frac{1}{0}$ is undefined. The matrix collapses $\mathbb{R}^2$ onto the line $y = -x$.
   In both cases, the kernel contains non-trivial vectors:
   $$A(1)\begin{pmatrix}1\\-1\end{pmatrix} = \begin{pmatrix}0\\0\end{pmatrix},\qquad A(-1)\begin{pmatrix}1\\1\end{pmatrix} = \begin{pmatrix}0\\0\end{pmatrix},$$
   confirming that the transformations cannot be inverted.

## Verification and Consistency Checks
For any $t \neq \pm 1$, compute the product:
$$A(t) A(t)^{-1} = \begin{pmatrix}1 & t \\ t & 1\end{pmatrix} \left[ \frac{1}{1 - t^2} \begin{pmatrix}1 & -t \\ -t & 1\end{pmatrix} \right]$$
$$= \frac{1}{1 - t^2} \begin{pmatrix}1(1) + t(-t) & 1(-t) + t(1) \\ t(1) + 1(-t) & t(-t) + 1(1)\end{pmatrix} = \frac{1}{1 - t^2} \begin{pmatrix}1 - t^2 & 0 \\ 0 & 1 - t^2\end{pmatrix} = \begin{pmatrix}1 & 0 \\ 0 & 1\end{pmatrix} = I.$$
The product is the identity matrix for all $t \neq \pm 1$.
