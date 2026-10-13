# Problem 10: Inverse of a Diagonal Matrix

## Problem Statement
Given

$$D=\begin{pmatrix}2&0&0\\0&-3&0\\0&0&5\end{pmatrix},\qquad E=\begin{pmatrix}2&0&0\\0&0&0\\0&0&5\end{pmatrix}.$$

Without using Gauss–Jordan elimination, decide which matrix is invertible. For the invertible matrix, give the inverse and check the result by multiplication.

## Theoretical Background and Concepts
A diagonal matrix $M = \text{diag}(d_1, d_2, d_3)$ scales the three coordinate axes by $d_1, d_2, d_3$ respectively.
- If all diagonal entries are non-zero, each scaling is reversible, and the inverse matrix is formed by the reciprocal diagonal entries:
  $$M^{-1} = \text{diag}\left(\frac{1}{d_1},\; \frac{1}{d_2},\; \frac{1}{d_3}\right).$$
- If any diagonal entry is zero, the transformation collapses that coordinate to zero (information is permanently lost), so the transformation cannot be reversed and no inverse exists. Under the determinant criterion, $\det M = d_1 d_2 d_3$; if any diagonal entry is zero, $\det M = 0$, making the matrix singular.

## Detailed Step-by-Step Solution
1. **Analyze matrix $D$:**
   $$D = \begin{pmatrix}2&0&0\\0&-3&0\\0&0&5\end{pmatrix}.$$
   Matrix $D$ scales the three coordinates by $2, -3, 5$. Since all three diagonal entries are non-zero, its determinant is $\det D = 2(-3)(5) = -30 \neq 0$.
   Therefore, $D$ is **invertible**. Its inverse reverses these scalings by taking reciprocals:
   $$D^{-1} = \begin{pmatrix}\frac{1}{2} & 0 & 0 \\ 0 & -\frac{1}{3} & 0 \\ 0 & 0 & \frac{1}{5}\end{pmatrix}.$$

2. **Check $DD^{-1}$ by multiplication:**
   $$DD^{-1} = \text{diag}\left(2 \cdot \frac{1}{2},\; (-3)\left(-\frac{1}{3}\right),\; 5 \cdot \frac{1}{5}\right) = \text{diag}(1, 1, 1) = \begin{pmatrix}1&0&0\\0&1&0\\0&0&1\end{pmatrix} = I,$$
   with all off-diagonal entries remaining $0$.

3. **Analyze matrix $E$:**
   $$E = \begin{pmatrix}2&0&0\\0&0&0\\0&0&5\end{pmatrix}.$$
   In matrix $E$, the middle diagonal entry is $0$. Under the transformation $x \mapsto Ex$, the second input coordinate is completely lost because its output is always zero ($E(x, y, z)^T = (2x, 0, 5z)^T$). Because the original value of $y$ cannot be recovered from the output, the action cannot be reversed.
   Equivalently, by the determinant criterion, $\det E = 2 \cdot 0 \cdot 5 = 0$.
   Therefore, matrix $E$ is **not invertible**.

## Verification and Consistency Checks
The product $D D^{-1} = I$ is confirmed by the diagonal reciprocal products $2(1/2)=1, (-3)(-1/3)=1, 5(1/5)=1$. For $E$, $E(0, 1, 0)^T = (0, 0, 0)^T$, confirming a non-trivial kernel and lack of invertibility.
