# Problem 15: Associativity of Multiplication and Different Calculation Paths

## Problem Statement
Given

$$A=\begin{pmatrix}1&2&0\\0&1&1\end{pmatrix},\qquad B=\begin{pmatrix}1&0\\2&1\\-1&3\end{pmatrix},\qquad C=\begin{pmatrix}2&1\\0&-1\end{pmatrix}.$$
Compute $(AB)C$ and $A(BC)$. Compare the results and the number of intermediate operations. Explain what associativity of matrix multiplication means in this example.

## Theoretical Background and Concepts
Matrix multiplication is associative: for compatible matrices,

$$(AB)C=A(BC).$$
This means that although the grouping may differ, the final product is the same.

## Detailed Step-by-Step Solution
First compute $AB$:

$$AB = \begin{pmatrix}1&2&0\\0&1&1\end{pmatrix}\begin{pmatrix}1&0\\2&1\\-1&3\end{pmatrix}
=\begin{pmatrix}1\cdot1+2\cdot2+0(-1) & 1\cdot0+2\cdot1+0\cdot3\\0\cdot1+1\cdot2+1(-1) & 0\cdot0+1\cdot1+1\cdot3\end{pmatrix}
=\begin{pmatrix}5&2\\1&4\end{pmatrix}.$$

Then

$$(AB)C = \begin{pmatrix}5&2\\1&4\end{pmatrix}\begin{pmatrix}2&1\\0&-1\end{pmatrix}
=\begin{pmatrix}5\cdot2+2\cdot0 & 5\cdot1+2(-1)\\1\cdot2+4\cdot0 & 1\cdot1+4(-1)\end{pmatrix}
=\begin{pmatrix}10&3\\2&-3\end{pmatrix}.$$

Now compute $BC$:

$$BC = \begin{pmatrix}1&0\\2&1\\-1&3\end{pmatrix}\begin{pmatrix}2&1\\0&-1\end{pmatrix}
=\begin{pmatrix}2&1\\4&1\\-2&-4\end{pmatrix}.$$

Then

$$A(BC)=\begin{pmatrix}1&2&0\\0&1&1\end{pmatrix}\begin{pmatrix}2&1\\4&1\\-2&-4\end{pmatrix}
=\begin{pmatrix}1\cdot2+2\cdot4+0(-2) & 1\cdot1+2\cdot1+0(-4)\\0\cdot2+1\cdot4+1(-2) & 0\cdot1+1\cdot1+1(-4)\end{pmatrix}
=\begin{pmatrix}10&3\\2&-3\end{pmatrix}.$$

Hence,

$$(AB)C=A(BC).$$

## Verification and Consistency Checks
The two calculation paths yield the same final matrix. Although the intermediate products differ, the final result is identical because matrix multiplication is associative. This means we may regroup factors without changing the outcome, even though the order of factors cannot be changed in general.
