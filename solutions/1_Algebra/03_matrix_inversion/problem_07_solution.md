# Problem 7: Inverse of a Product

## Problem Statement
For

$$A=\begin{pmatrix}1&1\\0&1\end{pmatrix},\qquad B=\begin{pmatrix}2&0\\0&3\end{pmatrix}$$

compute $(AB)^{-1}$ and $B^{-1}A^{-1}$. Check that the results are the same and explain the meaning of the reversed order.

## Theoretical Background and Concepts
For any two invertible matrices $A$ and $B$ of the same size, the inverse of their product is:

$$(AB)^{-1} = B^{-1}A^{-1}.$$

**Meaning of the reversed order:**
Matrix multiplication represents a composition of transformations: $AB$ applies the transformation $B$ first, followed by $A$.
To undo the combined operation, one must first undo the last operation that was performed ($A$), and then undo the earlier operation ($B$):

$$(B^{-1}A^{-1})(AB) = B^{-1}(A^{-1}A)B = B^{-1}(I)B = B^{-1}B = I.$$

This is analogous to the "shoes and socks" rule: putting on socks then shoes is undone by taking off shoes first, then socks.

## Detailed Step-by-Step Solution
1. **Compute the product $AB$ and its inverse $(AB)^{-1}$:**
   $$AB = \begin{pmatrix}1&1\\0&1\end{pmatrix}\begin{pmatrix}2&0\\0&3\end{pmatrix} = \begin{pmatrix}1(2)+1(0) & 1(0)+1(3) \\ 0(2)+1(0) & 0(0)+1(3)\end{pmatrix} = \begin{pmatrix}2&3\\0&3\end{pmatrix}.$$
   Now find $(AB)^{-1}$:
   $$\det(AB) = (2)(3) - (3)(0) = 6.$$
   $$(AB)^{-1} = \frac{1}{6}\begin{pmatrix}3 & -3 \\ 0 & 2\end{pmatrix} = \begin{pmatrix}\frac{1}{2} & -\frac{1}{2} \\ 0 & \frac{1}{3}\end{pmatrix}.$$

2. **Compute individual inverses $A^{-1}$ and $B^{-1}$:**
   - For $A$: $\det A = 1(1) - 0 = 1$.
     $$A^{-1} = \begin{pmatrix}1 & -1 \\ 0 & 1\end{pmatrix}.$$
   - For $B$: $\det B = 2(3) - 0 = 6$.
     $$B^{-1} = \begin{pmatrix}\frac{1}{2} & 0 \\ 0 & \frac{1}{3}\end{pmatrix}.$$

3. **Compute the product in reversed order $B^{-1}A^{-1}$:**
   $$B^{-1}A^{-1} = \begin{pmatrix}\frac{1}{2} & 0 \\ 0 & \frac{1}{3}\end{pmatrix}\begin{pmatrix}1 & -1 \\ 0 & 1\end{pmatrix} = \begin{pmatrix}\frac{1}{2}(1) + 0 & \frac{1}{2}(-1) + 0 \\ 0 + \frac{1}{3}(0) & 0 + \frac{1}{3}(1)\end{pmatrix} = \begin{pmatrix}\frac{1}{2} & -\frac{1}{2} \\ 0 & \frac{1}{3}\end{pmatrix}.$$

4. **Comparison:**
   Comparing the two matrices:
   $$(AB)^{-1} = B^{-1}A^{-1} = \begin{pmatrix}\frac{1}{2} & -\frac{1}{2} \\ 0 & \frac{1}{3}\end{pmatrix}.$$
   The equality is verified.

## Verification and Consistency Checks
- Note what happens if the order is not reversed:
  $$A^{-1}B^{-1} = \begin{pmatrix}1 & -1 \\ 0 & 1\end{pmatrix}\begin{pmatrix}\frac{1}{2} & 0 \\ 0 & \frac{1}{3}\end{pmatrix} = \begin{pmatrix}\frac{1}{2} & -\frac{1}{3} \\ 0 & \frac{1}{3}\end{pmatrix} \neq (AB)^{-1}.$$
  This confirms that reversing the order is essential.
- Product verification:
  $$(AB)(B^{-1}A^{-1}) = \begin{pmatrix}2&3\\0&3\end{pmatrix}\begin{pmatrix}\frac{1}{2}&-\frac{1}{2}\\0&\frac{1}{3}\end{pmatrix} = \begin{pmatrix}1+0 & -1+1 \\ 0+0 & 0+1\end{pmatrix} = \begin{pmatrix}1&0\\0&1\end{pmatrix} = I.$$
