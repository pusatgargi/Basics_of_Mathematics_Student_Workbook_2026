# Problem 10: Columns of a Matrix Product

## Problem Statement
Given

$$A=\begin{pmatrix}1&2&0\\0&1&1\end{pmatrix},\qquad B=\begin{pmatrix}1&2\\-1&0\\3&1\end{pmatrix}.$$
Denote the columns of $B$ by $b_1,b_2$.

1. Compute $Ab_1$ and $Ab_2$.
2. Compute the matrix $AB$.
3. Compare the results and explain why the columns of $AB$ are exactly the vectors $Ab_1$ and $Ab_2$.

## Theoretical Background and Concepts
If a matrix $B$ has columns $b_1,b_2,\dots$, then the columns of $AB$ are exactly $Ab_1,Ab_2,\dots$. This follows directly from the definition of matrix multiplication.

## Detailed Step-by-Step Solution
Write the columns of $B$:

$$b_1=\begin{pmatrix}1\\-1\\3\end{pmatrix},\qquad b_2=\begin{pmatrix}2\\0\\1\end{pmatrix}.$$

Now compute:

$$Ab_1 = \begin{pmatrix}1&2&0\\0&1&1\end{pmatrix}\begin{pmatrix}1\\-1\\3\end{pmatrix}
=\begin{pmatrix}1\cdot1+2(-1)+0\cdot3\\0\cdot1+1(-1)+1\cdot3\end{pmatrix}
=\begin{pmatrix}-1\\2\end{pmatrix}.$$

$$Ab_2 = \begin{pmatrix}1&2&0\\0&1&1\end{pmatrix}\begin{pmatrix}2\\0\\1\end{pmatrix}
=\begin{pmatrix}1\cdot2+2\cdot0+0\cdot1\\0\cdot2+1\cdot0+1\cdot1\end{pmatrix}
=\begin{pmatrix}2\\1\end{pmatrix}.$$

Now compute the full product:

$$AB = \begin{pmatrix}1&2&0\\0&1&1\end{pmatrix}\begin{pmatrix}1&2\\-1&0\\3&1\end{pmatrix}
=\begin{pmatrix}1\cdot1+2(-1)+0\cdot3 & 1\cdot2+2\cdot0+0\cdot1\\0\cdot1+1(-1)+1\cdot3 & 0\cdot2+1\cdot0+1\cdot1\end{pmatrix}
=\begin{pmatrix}-1&2\\2&1\end{pmatrix}.$$

The columns of this product are exactly:

$$\begin{pmatrix}-1\\2\end{pmatrix},\qquad \begin{pmatrix}2\\1\end{pmatrix}.$$

## Verification and Consistency Checks
These are exactly the vectors $Ab_1$ and $Ab_2$ computed earlier. Therefore, the columns of $AB$ are obtained by applying $A$ to each column of $B$ individually.
