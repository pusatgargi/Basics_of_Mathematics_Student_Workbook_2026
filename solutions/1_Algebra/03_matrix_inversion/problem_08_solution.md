# Problem 8: Inverse of a Transformation

## Problem Statement
The matrix

$$S=\begin{pmatrix}2&0\\0&\frac12\end{pmatrix}$$

describes a scaling of the plane. Find $S^{-1}$ and explain geometrically what the inverse transformation does. Check the action of the pair $S,S^{-1}$ on one simple vector.

## Theoretical Background and Concepts
A diagonal matrix $D = \begin{pmatrix}d_1&0\\0&d_2\end{pmatrix}$ scales the $x$-coordinate by $d_1$ and the $y$-coordinate by $d_2$.
The inverse transformation reverses these scalings by multiplying each coordinate by the reciprocal factor:

$$D^{-1} = \begin{pmatrix}\frac{1}{d_1}&0\\0&\frac{1}{d_2}\end{pmatrix}.$$

Applying $S$ followed by $S^{-1}$ completes a round trip, restoring any vector to its original coordinates: $S^{-1}(S v) = v$.

## Detailed Step-by-Step Solution
1. **Find $S^{-1}$:**
   The matrix $S = \begin{pmatrix}2&0\\0&\frac{1}{2}\end{pmatrix}$ is diagonal with entries $2$ and $\frac{1}{2}$.
   Inverting each diagonal entry by taking its reciprocal:
   $$S^{-1} = \begin{pmatrix}\frac{1}{2} & 0 \\ 0 & 2\end{pmatrix}.$$

2. **Geometric interpretation:**
   - **Action of $S$:** Doubles the horizontal coordinate ($x \mapsto 2x$) and halves the vertical coordinate ($y \mapsto \frac{1}{2}y$).
   - **Action of $S^{-1}$:** Halves the horizontal coordinate ($x \mapsto \frac{1}{2}x$) and doubles the vertical coordinate ($y \mapsto 2y$).
   Geometrically, $S^{-1}$ exactly undoes the distortion caused by $S$, stretching along the axis that was compressed and compressing along the axis that was stretched.

3. **Check on a test vector:**
   Choose vector $v = \begin{pmatrix}2\\4\end{pmatrix}$.
   - Apply $S$:
     $$w = Sv = \begin{pmatrix}2&0\\0&\frac{1}{2}\end{pmatrix}\begin{pmatrix}2\\4\end{pmatrix} = \begin{pmatrix}2(2)\\\frac{1}{2}(4)\end{pmatrix} = \begin{pmatrix}4\\2\end{pmatrix}.$$
   - Apply $S^{-1}$ to $w$:
     $$S^{-1}w = \begin{pmatrix}\frac{1}{2}&0\\0&2\end{pmatrix}\begin{pmatrix}4\\2\end{pmatrix} = \begin{pmatrix}\frac{1}{2}(4)\\2(2)\end{pmatrix} = \begin{pmatrix}2\\4\end{pmatrix} = v.$$

## Verification and Consistency Checks
The test vector $v = \begin{pmatrix}2\\4\end{pmatrix}$ transforms under $S$ to $\begin{pmatrix}4\\2\end{pmatrix}$ and returns under $S^{-1}$ to $\begin{pmatrix}2\\4\end{pmatrix} = v$. This verified round-trip confirms that $S^{-1}$ is the geometric inverse of $S$.
