# Problem 8: Inverse of a Transformation

## Detailed Step-by-Step Solution
For $S=\begin{pmatrix}2&0\\0&\frac12\end{pmatrix}$,

$$S^{-1}=\begin{pmatrix}\frac12&0\\0&2\end{pmatrix}.$$

The inverse scales the horizontal coordinate by $\frac12$ and the vertical coordinate by $2$, undoing $S$.

## Verification
For example, $v=\begin{pmatrix}2\\4\end{pmatrix}$ maps under $S$ to
$\begin{pmatrix}4\\2\end{pmatrix}$, and applying $S^{-1}$ returns
$\begin{pmatrix}2\\4\end{pmatrix}$.