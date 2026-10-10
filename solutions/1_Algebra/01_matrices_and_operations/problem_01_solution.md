# Problem 1: Matrix Size and Entries

## Problem Statement
Given

$$A=\begin{pmatrix}2&-1&3\\0&4&5\end{pmatrix},\qquad B=\begin{pmatrix}1&0\\-2&3\\4&1\end{pmatrix}.$$

1. State the sizes of matrices $A$ and $B$.
2. Read off the entries $a_{12}$, $a_{23}$, $b_{21}$, and $b_{32}$.
3. Write the second row of $A$ and the first column of $B$ as vectors.

## Theoretical Background and Concepts
A matrix of size $m\times n$ has $m$ rows and $n$ columns. The entry $a_{ij}$ is the element in row $i$, column $j$. Rows and columns are vectors when extracted from the matrix.

## Detailed Step-by-Step Solution
- Matrix $A$ has 2 rows and 3 columns, so $A$ is $2\times 3$.
- Matrix $B$ has 3 rows and 2 columns, so $B$ is $3\times 2$.
- From $A$:
  - $a_{12}=-1$
  - $a_{23}=5$
- From $B$:
  - $b_{21}=-2$
  - $b_{32}=1$
- The second row of $A$ is
  $$\begin{pmatrix}0&4&5\end{pmatrix}.$$
- The first column of $B$ is
  $$\begin{pmatrix}1\\-2\\4\end{pmatrix}.$$

## Verification and Consistency Checks
The entries match the positions in the matrices exactly:
- In $A$, the element in row 1, column 2 is $-1$.
- In $A$, the element in row 2, column 3 is $5$.
- In $B$, the element in row 2, column 1 is $-2$.
- In $B$, the element in row 3, column 2 is $1$.

Therefore, the answers are consistent with the given matrix notation.
