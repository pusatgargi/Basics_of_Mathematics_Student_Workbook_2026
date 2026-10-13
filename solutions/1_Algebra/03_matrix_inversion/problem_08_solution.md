# Problem 8: Inverse of a Transformation

## Problem Statement
The matrix

$$S=\begin{pmatrix}2&0\\0&\frac12\end{pmatrix}$$

describes a scaling of the plane. Find $S^{-1}$ and explain geometrically what the inverse transformation does. Check the action of the pair $S,S^{-1}$ on one simple vector.

## Theoretical Background and Concepts
A diagonal matrix $D = \begin{pmatrix}d_1 & 0 \\ 0 & d_2\end{pmatrix}$ represents axis-aligned scaling: it stretches (or compresses) the $x$-direction by a factor of $d_1$ and the $y$-direction by a factor of $d_2$.
The inverse matrix $D^{-1}$ represents the reverse geometric operation: it scales each axis by the reciprocal factor:

$$D^{-1} = \begin{pmatrix}\frac{1}{d_1} & 0 \\ 0 & \frac{1}{d_2}\end{pmatrix}.$$

Applying $S$ followed by $S^{-1}$ restores every point in the plane to its original position: $S^{-1}(S v) = I v = v$.

## Detailed Step-by-Step Solution
1. **Find $S^{-1}$:**
   The matrix $S = \begin{pmatrix}2&0\\0&\frac{1}{2}\end{pmatrix}$ has determinant:
   $$\det S = (2)\left(\frac{1}{2}\right) - (0)(0) = 1 \neq 0.$$
   Applying the $2\times2$ inverse formula (or reciprocal diagonal rule):
   $$S^{-1} = \begin{pmatrix}\frac{1}{2} & 0 \\ 0 & 2\end{pmatrix}.$$

2. **Geometric interpretation:**
   - **Forward transformation $S$:** Stretches the plane horizontally by a factor of $2$ and compresses it vertically by a factor of $\frac{1}{2}$ (halving the $y$-coordinate).
   - **Inverse transformation $S^{-1}$:** Compresses the plane horizontally by a factor of $\frac{1}{2}$ and stretches it vertically by a factor of $2$.
   Geometrically, $S^{-1}$ exactly undoes the distortion introduced by $S$, restoring the original coordinates and shapes.

3. **Check the action on a test vector:**
   Choose vector $v = \begin{pmatrix}2\\4\end{pmatrix}$.
   - Apply $S$:
     $$w = Sv = \begin{pmatrix}2&0\\0&\frac{1}{2}\end{pmatrix}\begin{pmatrix}2\\4\end{pmatrix} = \begin{pmatrix}2(2) + 0 \\ 0 + \frac{1}{2}(4)\end{pmatrix} = \begin{pmatrix}4\\2\end{pmatrix}.$$
   - Apply $S^{-1}$ to $w$:
     $$S^{-1}w = \begin{pmatrix}\frac{1}{2}&0\\0&2\end{pmatrix}\begin{pmatrix}4\\2\end{pmatrix} = \begin{pmatrix}\frac{1}{2}(4) + 0 \\ 0 + 2(2)\end{pmatrix} = \begin{pmatrix}2\\4\end{pmatrix} = v.$$

## Verification and Consistency Checks
- Algebraic product:
  $$S S^{-1} = \begin{pmatrix}2&0\\0&\frac{1}{2}\end{pmatrix}\begin{pmatrix}\frac{1}{2}&0\\0&2\end{pmatrix} = \begin{pmatrix}1&0\\0&1\end{pmatrix} = I.$$
- Area preservation:
  Notice $\det S = 1$, which means $S$ is an area-preserving transformation (hyperbolic shear/squeeze mapping). Its inverse also has determinant $\det(S^{-1}) = 1$, preserving area as expected.
