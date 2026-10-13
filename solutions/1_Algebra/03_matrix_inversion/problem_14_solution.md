# Problem 14: A Matrix That Is Its Own Inverse

## Problem Statement
Assume that a square matrix $A$ satisfies

$$A^2=I.$$

Show that

$$A^{-1}=A.$$

Then give an example of a $2\times2$ matrix different from $I$ and $-I$ that satisfies this condition, and verify it by multiplication.

## Theoretical Background and Concepts
By definition, a matrix $B$ is the inverse of $A$ if and only if $AB = BA = I$.
When a matrix satisfies $A^2 = I$, the definition of the inverse is satisfied directly by $A$ itself.
Such a matrix is called an **involutory matrix** (or an involution), representing a transformation that is its own inverse (such as a reflection).

## Detailed Step-by-Step Solution
1. **Show that $A^2 = I \implies A^{-1} = A$:**
   By assumption:
   $$A^2 = A \cdot A = I.$$
   By definition of the multiplicative inverse, if multiplying $A$ by a matrix yields the identity matrix $I$, that matrix is the inverse of $A$. Since multiplying $A$ by $A$ gives $I$, it follows immediately that:
   $$A^{-1} = A.$$

2. **Example of a $2\times2$ matrix different from $I$ and $-I$:**
   Consider the diagonal reflection matrix:
   $$A = \begin{pmatrix}1 & 0 \\ 0 & -1\end{pmatrix} = \text{diag}(1, -1).$$
   Notice that $A \neq I$ and $A \neq -I$.

3. **Verify by multiplication:**
   $$\text{diag}(1, -1) \cdot \text{diag}(1, -1) = \text{diag}(1 \cdot 1,\; (-1) \cdot (-1)) = \text{diag}(1, 1) = \begin{pmatrix}1&0\\0&1\end{pmatrix} = I,$$
   with the off-diagonal entries evaluating to zero:
   $$A^2 = \begin{pmatrix}1&0\\0&-1\end{pmatrix}\begin{pmatrix}1&0\\0&-1\end{pmatrix} = \begin{pmatrix}1(1)+0(0) & 1(0)+0(-1) \\ 0(1)+(-1)(0) & 0(0)+(-1)(-1)\end{pmatrix} = \begin{pmatrix}1&0\\0&1\end{pmatrix} = I.$$

   Since $A^2 = I$, $A^{-1} = A$ is verified.

## Verification and Consistency Checks
- Using the $2\times2$ inverse formula on $A = \begin{pmatrix}1&0\\0&-1\end{pmatrix}$:
  $$\det A = 1(-1) - 0(0) = -1.$$
  $$A^{-1} = \frac{1}{-1}\begin{pmatrix}-1 & 0 \\ 0 & 1\end{pmatrix} = \begin{pmatrix}1 & 0 \\ 0 & -1\end{pmatrix} = A.$$
- The reflection matrix satisfies $A^2 = I$ and $A^{-1} = A$, with $A \neq \pm I$.
