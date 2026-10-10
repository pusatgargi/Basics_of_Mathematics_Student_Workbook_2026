# Problem 6: Transpose

## Problem Statement
For

$$A=\begin{pmatrix}1&2&3\\4&5&6\end{pmatrix},\qquad B=\begin{pmatrix}1&0\\2&1\\-1&3\end{pmatrix}$$
compute $A^T$, $B^T$, and $AB$. Then verify in this example that

$$(AB)^T=B^TA^T.$$

## Theoretical Background and Concepts
The transpose of a matrix switches rows and columns. For two compatible matrices $A$ and $B$, the identity $(AB)^T=B^TA^T$ holds.

## Detailed Step-by-Step Solution
Compute the transposes:

$$A^T = \begin{pmatrix}1&4\\2&5\\3&6\end{pmatrix},\qquad B^T = \begin{pmatrix}1&2&-1\\0&1&3\end{pmatrix}.$$

Now compute $AB$:

$$AB = \begin{pmatrix}1&2&3\\4&5&6\end{pmatrix}\begin{pmatrix}1&0\\2&1\\-1&3\end{pmatrix}
=\begin{pmatrix}1\cdot1+2\cdot2+3\cdot(-1) & 1\cdot0+2\cdot1+3\cdot3\\4\cdot1+5\cdot2+6\cdot(-1) & 4\cdot0+5\cdot1+6\cdot3\end{pmatrix}.
$$
So,

$$AB = \begin{pmatrix}2&11\\8&23\end{pmatrix}.$$

Then,

$$(AB)^T = \begin{pmatrix}2&8\\11&23\end{pmatrix}.$$

Now compute $B^TA^T$:

$$B^TA^T = \begin{pmatrix}1&2&-1\\0&1&3\end{pmatrix}\begin{pmatrix}1&4\\2&5\\3&6\end{pmatrix}
=\begin{pmatrix}1\cdot1+2\cdot2+(-1)\cdot3 & 1\cdot4+2\cdot5+(-1)\cdot6\\0\cdot1+1\cdot2+3\cdot3 & 0\cdot4+1\cdot5+3\cdot6\end{pmatrix}
=\begin{pmatrix}2&8\\11&23\end{pmatrix}.$$

Therefore,

$$(AB)^T = B^TA^T.$$

## Verification and Consistency Checks
Both sides of the identity give the same matrix, confirming the transpose rule for products. The order of factors reverses under transposition, which is a key property of matrix algebra.
