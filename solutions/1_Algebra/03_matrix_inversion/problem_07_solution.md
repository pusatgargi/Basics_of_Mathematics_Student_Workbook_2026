# Problem 7: Inverse of a Product

## Detailed Step-by-Step Solution
Here
$$AB=\begin{pmatrix}2&3\\0&3\end{pmatrix},\qquad
(AB)^{-1}=\begin{pmatrix}\frac12&-\frac12\\0&\frac13\end{pmatrix}.$$

Also,
$$A^{-1}=\begin{pmatrix}1&-1\\0&1\end{pmatrix},\qquad
B^{-1}=\begin{pmatrix}\frac12&0\\0&\frac13\end{pmatrix},$$
so

$$
B^{-1}A^{-1}
=\begin{pmatrix}\frac12&-\frac12\\0&\frac13\end{pmatrix}
=(AB)^{-1}.
$$

The order reverses because $AB$ applies $B$ first and then $A$; to undo this, apply $A^{-1}$ first and then $B^{-1}$, giving $B^{-1}A^{-1}$.

## Verification
Multiplying $AB$ by the displayed inverse gives $I$.