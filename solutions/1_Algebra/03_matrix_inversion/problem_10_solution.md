# Problem 10: Inverse of a Diagonal Matrix

## Problem Statement
Given

$$D=\begin{pmatrix}2&0&0\\0&-3&0\\0&0&5\end{pmatrix},\qquad E=\begin{pmatrix}2&0&0\\0&0&0\\0&0&5\end{pmatrix}.$$

Without using Gauss–Jordan elimination, decide which matrix is invertible. For the invertible matrix, give the inverse and check the result by multiplication.

## Theoretical Background and Concepts
For a diagonal matrix $M = \text{diag}(d_1, d_2, \dots, d_n)$:
1. Its determinant is the product of its diagonal entries:
   $$\det M = d_1 \cdot d_2 \cdots d_n.$$
2. Therefore, a diagonal matrix is invertible if and only if **all its diagonal entries are nonzero** ($d_i \neq 0$ for all $i$).
3. If invertible, its inverse is also a diagonal matrix obtained simply by replacing each diagonal entry with its reciprocal:
   $$M^{-1} = \text{diag}\left(\frac{1}{d_1}, \frac{1}{d_2}, \dots, \frac{1}{d_n}\right).$$

## Detailed Step-by-Step Solution
1. **Analyze matrix $D$:**
   $$D = \begin{pmatrix}2&0&0\\0&-3&0\\0&0&5\end{pmatrix}.$$
   The diagonal entries are $2, -3, 5$.
   Since none of the diagonal entries is zero:
   $$\det D = (2)(-3)(5) = -30 \neq 0.$$
   Therefore, matrix $D$ is **invertible**.

2. **Compute $D^{-1}$:**
   Inverting each diagonal entry:
   $$D^{-1} = \begin{pmatrix}\frac{1}{2} & 0 & 0 \\ 0 & -\frac{1}{3} & 0 \\ 0 & 0 & \frac{1}{5}\end{pmatrix}.$$

3. **Analyze matrix $E$:**
   $$E = \begin{pmatrix}2&0&0\\0&0&0\\0&0&5\end{pmatrix}.$$
   The second diagonal entry is $e_{22} = 0$.
   $$\det E = (2)(0)(5) = 0.$$
   Because $\det E = 0$ (and Row 2 is completely zero), matrix $E$ is **not invertible**.

4. **Check $D D^{-1}$ by multiplication:**
   $$DD^{-1} = \begin{pmatrix}2&0&0\\0&-3&0\\0&0&5\end{pmatrix}\begin{pmatrix}\frac{1}{2}&0&0\\0&-\frac{1}{3}&0\\0&0&\frac{1}{5}\end{pmatrix}$$
   Since both are diagonal matrices:
   - $(1,1)$ entry: $2 \cdot \frac{1}{2} = 1$
   - $(2,2)$ entry: $(-3) \cdot \left(-\frac{1}{3}\right) = 1$
   - $(3,3)$ entry: $5 \cdot \frac{1}{5} = 1$
   - All off-diagonal entries are $0$.

   $$DD^{-1} = \begin{pmatrix}1&0&0\\0&1&0\\0&0&1\end{pmatrix} = I_3.$$

## Verification and Consistency Checks
- $D D^{-1} = I_3$ and $D^{-1} D = I_3$ are confirmed.
- For $E$, notice that $E \begin{pmatrix}0\\1\\0\end{pmatrix} = \begin{pmatrix}0\\0\\0\end{pmatrix}$, proving the kernel is non-trivial, so $E$ is definitely singular.
