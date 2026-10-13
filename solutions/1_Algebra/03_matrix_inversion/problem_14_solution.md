# Problem 14: A Matrix That Is Its Own Inverse

## Problem Statement
Assume that a square matrix $A$ satisfies

$$A^2=I.$$

Show that

$$A^{-1}=A.$$

Then give an example of a $2\times2$ matrix different from $I$ and $-I$ that satisfies this condition, and verify it by multiplication.

## Theoretical Background and Concepts
A matrix that is its own inverse is called an **involution** (or an **involutory matrix**).
By definition of the matrix inverse, a matrix $B$ is the inverse of $A$ if and only if $AB = BA = I$.
Geometrically, an involutory linear transformation satisfies $T(T(v)) = v$, which represents a reflection or an inversion across a subspace.

## Detailed Step-by-Step Solution
1. **Show that $A^2 = I \implies A^{-1} = A$:**
   By assumption:
   $$A^2 = A \cdot A = I.$$
   Multiplying this equation on the left by $A^{-1}$ (which exists because $\det(A^2) = (\det A)^2 = 1 \implies \det A = \pm 1 \neq 0$):
   $$A^{-1} (A \cdot A) = A^{-1} I$$
   $$(A^{-1} A) A = A^{-1}$$
   $$I \cdot A = A^{-1}$$
   $$A = A^{-1}.$$
   Thus, $A$ is its own inverse.

2. **Construct an example of a $2\times2$ matrix $A \neq \pm I$ with $A^2 = I$:**
   Consider the reflection matrix across the line $y = x$:
   $$A = \begin{pmatrix}0 & 1 \\ 1 & 0\end{pmatrix}.$$
   Notice that $A \neq I$ and $A \neq -I$.

3. **Verify by multiplication:**
   $$A^2 = \begin{pmatrix}0 & 1 \\ 1 & 0\end{pmatrix}\begin{pmatrix}0 & 1 \\ 1 & 0\end{pmatrix} = \begin{pmatrix}0(0) + 1(1) & 0(1) + 1(0) \\ 1(0) + 0(1) & 1(1) + 0(0)\end{pmatrix} = \begin{pmatrix}1 & 0 \\ 0 & 1\end{pmatrix} = I.$$

   Since $A^2 = I$, its inverse is indeed:
   $$A^{-1} = A = \begin{pmatrix}0 & 1 \\ 1 & 0\end{pmatrix}.$$

## Verification and Consistency Checks
- Using the $2\times2$ inverse formula on $A = \begin{pmatrix}0&1\\1&0\end{pmatrix}$:
  $$\det A = (0)(0) - (1)(1) = -1.$$
  $$A^{-1} = \frac{1}{-1}\begin{pmatrix}0 & -1 \\ -1 & 0\end{pmatrix} = \begin{pmatrix}0 & 1 \\ 1 & 0\end{pmatrix} = A.$$
- Geometric check: Reflecting a point $(x, y)$ across the line $y=x$ maps $(x,y) \mapsto (y,x)$. Reflecting a second time maps $(y,x) \mapsto (x,y)$, restoring the original point. This confirms geometrically that the transformation is an involution.
