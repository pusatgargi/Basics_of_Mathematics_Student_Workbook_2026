# Problem 11: Parameter and Invertibility

## Problem Statement
For

$$A(t)=\begin{pmatrix}1&t\\t&1\end{pmatrix}$$

find all $t$ for which the matrix is invertible, and then give a formula for $A(t)^{-1}$. Explain what happens to this formula at the excluded values.

## Theoretical Background and Concepts
For a $2\times2$ matrix $\begin{pmatrix}a&b\\c&d\end{pmatrix}$, the inverse exists if and only if $\det \neq 0$, in which case:
$$M^{-1} = \frac{1}{\det M}\begin{pmatrix}d & -b \\ -c & a\end{pmatrix}.$$
A nonzero determinant permits the inverse. When the determinant is zero, the formula requires division by zero, reflecting that the matrix has become singular.

## Detailed Step-by-Step Solution
1. **Compute determinant and condition for invertibility:**
   $$\det A(t) = 1 \cdot 1 - t \cdot t = 1 - t^2 = (1 - t)(1 + t).$$
   A nonzero determinant permits the inverse. Thus, $A(t)$ is invertible if and only if:
   $$\det A(t) \neq 0 \iff (1 - t)(1 + t) \neq 0 \iff t \neq 1 \quad \text{and} \quad t \neq -1.$$
   Thus, $A(t)$ is invertible for all $t \in \mathbb{R} \setminus \{-1, 1\}$.

2. **Formula for $A(t)^{-1}$:**
   Swapping the diagonal entries (which are both $1$) and negating the off-diagonal entries ($-t$) gives the numerator matrix:
   $$\begin{pmatrix}1 & -t \\ -t & 1\end{pmatrix}.$$
   Dividing by the determinant gives:
   $$A(t)^{-1} = \frac{1}{1 - t^2} \begin{pmatrix}1 & -t \\ -t & 1\end{pmatrix}.$$

3. **Explanation of what happens at the excluded values:**
   At $t = 1$ and $t = -1$, the determinant becomes $1 - t^2 = 0$, so the scalar factor $\frac{1}{1 - t^2}$ involves division by zero and is undefined.
   - **At $t = 1$:**
     $$A(1) = \begin{pmatrix}1 & 1 \\ 1 & 1\end{pmatrix}.$$
     The matrix has **equal rows** ($R_1 = R_2$).
   - **At $t = -1$:**
     $$A(-1) = \begin{pmatrix}1 & -1 \\ -1 & 1\end{pmatrix}.$$
     The matrix has **opposite rows** ($R_2 = -R_1$).
   In both cases, the rows are linearly dependent, so the rank drops to 1 and the matrix has no inverse.

## Verification and Consistency Checks
Multiply $A(t)$ by the formula for $t \neq \pm 1$:
$$A(t) A(t)^{-1} = \frac{1}{1-t^2}\begin{pmatrix}1&t\\t&1\end{pmatrix}\begin{pmatrix}1&-t\\-t&1\end{pmatrix} = \frac{1}{1-t^2}\begin{pmatrix}1-t^2 & 0 \\ 0 & 1-t^2\end{pmatrix} = \begin{pmatrix}1&0\\0&1\end{pmatrix} = I.$$
The product produces the identity matrix for all allowed $t$.
