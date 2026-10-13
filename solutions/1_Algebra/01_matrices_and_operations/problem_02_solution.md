# Problem 2: Addition and Scalar Multiplication

## Problem Statement
For

$$A=\begin{pmatrix}1&2\\-1&3\end{pmatrix},\qquad B=\begin{pmatrix}4&-2\\0&5\end{pmatrix}$$

compute

$$A+B,\qquad A-B,\qquad 3A-2B.$$

Explain why matrix addition is possible only for matrices of the same size.

## Theoretical Background and Concepts
Matrix addition and subtraction are performed entry-by-entry. This is valid only when the matrices have the same dimensions, because each entry must be paired with the corresponding entry in the other matrix. Scalar multiplication scales each entry of the matrix individually by that scalar.

## Detailed Step-by-Step Solution
First compute:

$$A+B=\begin{pmatrix}1&2\\-1&3\end{pmatrix}+\begin{pmatrix}4&-2\\0&5\end{pmatrix}
=\begin{pmatrix}1+4&2+(-2)\\-1+0&3+5\end{pmatrix}
=\begin{pmatrix}5&0\\-1&8\end{pmatrix}.$$

Next,

$$A-B=\begin{pmatrix}1&2\\-1&3\end{pmatrix}-\begin{pmatrix}4&-2\\0&5\end{pmatrix}
=\begin{pmatrix}1-4&2-(-2)\\-1-0&3-5\end{pmatrix}
=\begin{pmatrix}-3&4\\-1&-2\end{pmatrix}.$$

Multiplying a matrix by a scalar multiplies every entry by that number. For example, for $3A$, the entry in row 2, column 1 is:

$$(3A)_{21} = 3 \cdot (-1) = -3.$$

Applying this scalar multiplication to all entries of $A$ and $B$:

$$3A=\begin{pmatrix}3&6\\-3&9\end{pmatrix},\qquad 2B=\begin{pmatrix}8&-4\\0&10\end{pmatrix}.$$

Then, to compute $3A - 2B$, we subtract the two scaled matrices entry by entry:

$$3A-2B=
\begin{pmatrix}3&6\\-3&9\end{pmatrix}-\begin{pmatrix}8&-4\\0&10\end{pmatrix}
=\begin{pmatrix}3-8 & 6-(-4)\\-3-0 & 9-10\end{pmatrix}
=\begin{pmatrix}-5&10\\-3&-1\end{pmatrix}.$$

Matrix addition requires matching dimensions because each entry is added to its corresponding entry. If the matrices have different sizes, some entries would have no partner.

## Verification and Consistency Checks
Each result was computed by combining corresponding entries. The dimensions remain $2\times2$ throughout, which is consistent with the fact that both matrices are $2\times2$.
