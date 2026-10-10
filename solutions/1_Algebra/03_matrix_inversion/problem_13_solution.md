# Problem 13: Undoing a Composite Transformation

## Detailed Step-by-Step Solution
First,
$$T=HS=\begin{pmatrix}2&1\\0&1\end{pmatrix},\qquad
T^{-1}=\begin{pmatrix}\frac12&-\frac12\\0&1\end{pmatrix}.$$

Alternatively,
$$
S^{-1}H^{-1}
=\begin{pmatrix}\frac12&0\\0&1\end{pmatrix}
\begin{pmatrix}1&-1\\0&1\end{pmatrix}
=\begin{pmatrix}\frac12&-\frac12\\0&1\end{pmatrix}.
$$

The incorrect order gives
$$
H^{-1}S^{-1}
=\begin{pmatrix}1&-1\\0&1\end{pmatrix}
\begin{pmatrix}\frac12&0\\0&1\end{pmatrix}
=\begin{pmatrix}\frac12&-1\\0&1\end{pmatrix},
$$
which differs. To undo $HS$, undo $H$ first, then $S$, so the inverse is $S^{-1}H^{-1}$.

## Verification
Both valid methods give the same $T^{-1}$, and $TT^{-1}=I$.