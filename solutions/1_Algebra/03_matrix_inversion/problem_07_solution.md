# Problem 7: Inverse of a Product

## Problem Statement
For

$$A=\begin{pmatrix}1&1\\0&1\end{pmatrix},\qquad B=\begin{pmatrix}2&0\\0&3\end{pmatrix}$$

compute $(AB)^{-1}$ and $B^{-1}A^{-1}$. Check that the results are the same and explain the meaning of the reversed order.

## Theoretical Background and Concepts
The inverse of a product of invertible matrices reverses the order of the factors:
$$(AB)^{-1} = B^{-1}A^{-1}.$$
**Meaning of the reversed order:**
Matrix multiplication represents a composition of operations where the right factor acts first: in $AB$, transformation $B$ is applied, followed by $A$. To undo this composite operation, the last operation applied ($A$) must be undone first by $A^{-1}$, and only then can $B$ be undone by $B^{-1}$. This is the "shoes and socks" rule: putting on socks then shoes is undone by taking off shoes first, then socks.

## Detailed Step-by-Step Solution
1. **Compute $AB$ and its inverse $(AB)^{-1}$:**
   $$AB = \begin{pmatrix}1&1\\0&1\end{pmatrix}\begin{pmatrix}2&0\\0&3\end{pmatrix} = \begin{pmatrix}1(2)+1(0) & 1(0)+1(3)\\0(2)+1(0) & 0(0)+1(3)\end{pmatrix} = \begin{pmatrix}2&3\\0&3\end{pmatrix}.$$
   Now invert $AB$ using the $2\times2$ inverse formula:
   $$\det(AB) = 2 \cdot 3 - 3 \cdot 0 = 6.$$
   $$(AB)^{-1} = \frac{1}{6}\begin{pmatrix}3 & -3 \\ 0 & 2\end{pmatrix} = \begin{pmatrix}\frac{1}{2} & -\frac{1}{2} \\ 0 & \frac{1}{3}\end{pmatrix}.$$

2. **Compute individual inverses $A^{-1}$ and $B^{-1}$:**
   - For $A = \begin{pmatrix}1&1\\0&1\end{pmatrix}$: $\det A = 1(1) - 0 = 1$, so swapping diagonal and negating off-diagonal entries gives:
     $$A^{-1} = \begin{pmatrix}1 & -1 \\ 0 & 1\end{pmatrix}.$$
   - For diagonal matrix $B = \begin{pmatrix}2&0\\0&3\end{pmatrix}$: taking the reciprocal diagonal entries gives:
     $$B^{-1} = \begin{pmatrix}\frac{1}{2} & 0 \\ 0 & \frac{1}{3}\end{pmatrix}.$$

3. **Compute $B^{-1}A^{-1}$:**
   $$B^{-1}A^{-1} = \begin{pmatrix}\frac{1}{2} & 0 \\ 0 & \frac{1}{3}\end{pmatrix}\begin{pmatrix}1 & -1 \\ 0 & 1\end{pmatrix}.$$
   Calculating representative row-column entries:
   - $(1,1)$: $\frac{1}{2}(1) + 0(0) = \frac{1}{2}$
   - $(1,2)$: $\frac{1}{2}(-1) + 0(1) = -\frac{1}{2}$
   - $(2,1)$: $0(1) + \frac{1}{3}(0) = 0$
   - $(2,2)$: $0(-1) + \frac{1}{3}(1) = \frac{1}{3}$

   Thus,
   $$B^{-1}A^{-1} = \begin{pmatrix}\frac{1}{2} & -\frac{1}{2} \\ 0 & \frac{1}{3}\end{pmatrix}.$$

4. **Comparison:**
   Both methods give the exact same matrix:
   $$(AB)^{-1} = B^{-1}A^{-1} = \begin{pmatrix}\frac{1}{2} & -\frac{1}{2} \\ 0 & \frac{1}{3}\end{pmatrix}.$$

## Verification and Consistency Checks
Check by multiplying $(AB)$ and $(B^{-1}A^{-1})$:
$$(AB)(B^{-1}A^{-1}) = \begin{pmatrix}2&3\\0&3\end{pmatrix}\begin{pmatrix}\frac{1}{2}&-\frac{1}{2}\\0&\frac{1}{3}\end{pmatrix} = \begin{pmatrix}2(1/2)+3(0) & 2(-1/2)+3(1/3)\\0(1/2)+3(0) & 0(-1/2)+3(1/3)\end{pmatrix} = \begin{pmatrix}1 & -1+1 \\ 0 & 1\end{pmatrix} = \begin{pmatrix}1&0\\0&1\end{pmatrix} = I.$$
The product produces the identity matrix, confirming the result.
