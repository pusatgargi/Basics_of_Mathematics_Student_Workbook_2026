# Problem 5: Matrix Times Vector

## Problem Statement
Let

$$A=\begin{pmatrix}2&-1\\1&3\end{pmatrix},\qquad x=\begin{pmatrix}4\\2\end{pmatrix}.$$
Compute $Ax$. Then express $Ax$ as a linear combination of the columns of $A$, with coefficients coming from the vector $x$.

## Theoretical Background and Concepts
For a matrix $A$ with columns $c_1,c_2,\dots$, and a vector $x=(x_1,x_2,\dots)^T$, the product $Ax$ is a linear combination of the columns of $A$ with coefficients given by the entries of $x$.

## Detailed Step-by-Step Solution
First compute the product:

$$Ax=
\begin{pmatrix}2&-1\\1&3\end{pmatrix}\begin{pmatrix}4\\2\end{pmatrix}
=
\begin{pmatrix}2\cdot4+(-1)\cdot2\\1\cdot4+3\cdot2\end{pmatrix}
=\begin{pmatrix}8-2\\4+6\end{pmatrix}
=\begin{pmatrix}6\\10\end{pmatrix}.$$

Now write the columns of $A$:

$$A = \begin{pmatrix}2&-1\\1&3\end{pmatrix} = \big(c_1\quad c_2\big),$$
where

$$c_1=\begin{pmatrix}2\\1\end{pmatrix},\qquad c_2=\begin{pmatrix}-1\\3\end{pmatrix}.$$
Since $x=\begin{pmatrix}4\\2\end{pmatrix}$, we get

$$Ax = 4c_1 + 2c_2
=4\begin{pmatrix}2\\1\end{pmatrix}+2\begin{pmatrix}-1\\3\end{pmatrix}
=\begin{pmatrix}8\\4\end{pmatrix}+\begin{pmatrix}-2\\6\end{pmatrix}
=\begin{pmatrix}6\\10\end{pmatrix}.$$

## Verification and Consistency Checks
The two methods give the same result:

$$Ax=\begin{pmatrix}6\\10\end{pmatrix}.$$
This confirms the column-combination interpretation of matrix-vector multiplication.
