# Problem 8: Row Operations and Their Reversibility

## Problem Statement
For

$$A=\begin{pmatrix}1&2&-1\\2&4&1\\-1&1&3\end{pmatrix}$$
perform, in order:
1. $R_2\leftarrow R_2-2R_1$,
2. $R_3\leftarrow R_3+R_1$,
3. interchange $R_2$ and $R_3$.

Write the matrix after each step. Then, for each of the three operations, state an operation that reverses it.

## Theoretical Background and Concepts
Elementary row operations are reversible. This is essential in Gaussian elimination and matrix inversion.

## Detailed Step-by-Step Solution
Start with

$$A=\begin{pmatrix}1&2&-1\\2&4&1\\-1&1&3\end{pmatrix}.$$

### Step 1: $R_2\leftarrow R_2-2R_1$

$$R_2=(2,4,1)-2(1,2,-1)=(0,0,3).$$
So the new matrix is

$$A_1=\begin{pmatrix}1&2&-1\\0&0&3\\-1&1&3\end{pmatrix}.$$

### Step 2: $R_3\leftarrow R_3+R_1$

$$R_3=(-1,1,3)+(1,2,-1)=(0,3,2).$$
So the matrix becomes

$$A_2=\begin{pmatrix}1&2&-1\\0&0&3\\0&3&2\end{pmatrix}.$$

### Step 3: interchange $R_2$ and $R_3$

$$A_3=\begin{pmatrix}1&2&-1\\0&3&2\\0&0&3\end{pmatrix}.$$

## Reverses of the Operations
- The operation $R_2\leftarrow R_2-2R_1$ is reversed by $R_2\leftarrow R_2+2R_1$.
- The operation $R_3\leftarrow R_3+R_1$ is reversed by $R_3\leftarrow R_3-R_1$.
- The operation interchange of $R_2$ and $R_3$ is reversed by interchanging $R_2$ and $R_3$ again.

## Verification and Consistency Checks
Each row operation is algebraically controlled and reversible. This is exactly the principle used in elimination-based methods for solving systems and computing inverses.
