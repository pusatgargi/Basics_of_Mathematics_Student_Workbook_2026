# Problem 4: Matrix Multiplication and Noncommutativity

## Problem Statement
For

$$A=\begin{pmatrix}1&2\\0&1\end{pmatrix},\qquad B=\begin{pmatrix}2&0\\3&1\end{pmatrix}$$
compute $AB$ and $BA$. Is $AB=BA$? Use this example to explain what noncommutativity of matrix multiplication means.

## Theoretical Background and Concepts
Matrix multiplication is defined row-by-column. In general, the order matters: $AB$ and $BA$ need not be equal, even when both products are defined.

## Detailed Step-by-Step Solution
Compute $AB$:

$$AB = \begin{pmatrix}1&2\\0&1\end{pmatrix}\begin{pmatrix}2&0\\3&1\end{pmatrix}
=\begin{pmatrix}1\cdot2+2\cdot3 & 1\cdot0+2\cdot1\\0\cdot2+1\cdot3 & 0\cdot0+1\cdot1\end{pmatrix}
=\begin{pmatrix}8&2\\3&1\end{pmatrix}.$$

Compute $BA$:

$$BA = \begin{pmatrix}2&0\\3&1\end{pmatrix}\begin{pmatrix}1&2\\0&1\end{pmatrix}
=\begin{pmatrix}2\cdot1+0\cdot0 & 2\cdot2+0\cdot1\\3\cdot1+1\cdot0 & 3\cdot2+1\cdot1\end{pmatrix}
=\begin{pmatrix}2&4\\3&7\end{pmatrix}.$$

Thus,

$$AB=\begin{pmatrix}8&2\\3&1\end{pmatrix},\qquad BA=\begin{pmatrix}2&4\\3&7\end{pmatrix}.$$
Therefore,

$$AB\ne BA.$$

This shows that matrix multiplication is generally noncommutative: changing the order of the factors changes the result.

## Verification and Consistency Checks
The products have the same size ($2\times2$), but their entries are different. This is a standard example showing that matrix multiplication does not behave like ordinary number multiplication, where the order of factors does not matter.
