# Problem 10: Columns of a Matrix Product

## Problem Statement
Given

$$A=\begin{pmatrix}1&2&0\\0&1&1\end{pmatrix},\qquad B=\begin{pmatrix}1&2\\-1&0\\3&1\end{pmatrix}.$$

Denote the columns of $B$ by $b_1,b_2$.

1. Compute $Ab_1$ and $Ab_2$.
2. Compute the matrix $AB$.
3. Compare the results and explain why the columns of $AB$ are exactly the vectors $Ab_1$ and $Ab_2$.

## Theoretical Background and Concepts
The product of a matrix $A$ and a matrix $B = (b_1 \; b_2 \; \dots \; b_p)$ can be understood column-by-column:

$$AB = A(b_1 \; b_2 \; \dots \; b_p) = (Ab_1 \; Ab_2 \; \dots \; Ab_p).$$

This fundamental connection arises because entry $(i, j)$ of $AB$ is defined by taking row $i$ of $A$ and column $j$ of $B$, which is identical to entry $i$ of the matrix-vector product $Ab_j$.

## Detailed Step-by-Step Solution
Write the columns of $B$:

$$b_1=\begin{pmatrix}1\\-1\\3\end{pmatrix},\qquad b_2=\begin{pmatrix}2\\0\\1\end{pmatrix}.$$

1. **Compute $Ab_1$ and $Ab_2$:**

   $$Ab_1 = \begin{pmatrix}1&2&0\\0&1&1\end{pmatrix}\begin{pmatrix}1\\-1\\3\end{pmatrix}
   =\begin{pmatrix}1\cdot1+2(-1)+0\cdot3\\0\cdot1+1(-1)+1\cdot3\end{pmatrix}
   =\begin{pmatrix}1 - 2 + 0\\0 - 1 + 3\end{pmatrix}
   =\begin{pmatrix}-1\\2\end{pmatrix}.$$

   $$Ab_2 = \begin{pmatrix}1&2&0\\0&1&1\end{pmatrix}\begin{pmatrix}2\\0\\1\end{pmatrix}
   =\begin{pmatrix}1\cdot2+2\cdot0+0\cdot1\\0\cdot2+1\cdot0+1\cdot1\end{pmatrix}
   =\begin{pmatrix}2 + 0 + 0\\0 + 0 + 1\end{pmatrix}
   =\begin{pmatrix}2\\1\end{pmatrix}.$$

2. **Compute the matrix product $AB$:**

   $$AB = \begin{pmatrix}1&2&0\\0&1&1\end{pmatrix}\begin{pmatrix}1&2\\-1&0\\3&1\end{pmatrix}$$
   $$=\begin{pmatrix}1\cdot1+2(-1)+0\cdot3 & 1\cdot2+2\cdot0+0\cdot1\\0\cdot1+1(-1)+1\cdot3 & 0\cdot2+1\cdot0+1\cdot1\end{pmatrix}
   =\begin{pmatrix}-1&2\\2&1\end{pmatrix}.$$

3. **Link between the column calculations and the matrix product:**
   Notice the exact algebraic correspondence:
   - For entry $(1, 1)$ of $AB$:
     $$(AB)_{11} = 1\cdot1 + 2(-1) + 0\cdot3 = -1,$$
     which is identical to the first entry of $Ab_1$: $(Ab_1)_1 = 1\cdot1 + 2(-1) + 0\cdot3 = -1$.
   - For entry $(2, 1)$ of $AB$:
     $$(AB)_{21} = 0\cdot1 + 1(-1) + 1\cdot3 = 2,$$
     which is identical to the second entry of $Ab_1$: $(Ab_1)_2 = 0\cdot1 + 1(-1) + 1\cdot3 = 2$.

   Generally, entry $i$ of the vector $Ab_j$ is computed as the sum of corresponding products from row $i$ of $A$ and column $j$ of $B$:
   $$(Ab_j)_i = \sum_k a_{ik} b_{kj}.$$
   By definition of matrix multiplication, entry $(i, j)$ of $AB$ is defined by the exact same formula:
   $$(AB)_{ij} = \sum_k a_{ik} b_{kj}.$$
   Because every entry $i$ in column $j$ of $AB$ matches entry $i$ of $Ab_j$, the entire $j$-th column of $AB$ is precisely the vector $Ab_j$:
   $$AB = \big(Ab_1 \quad Ab_2\big) = \begin{pmatrix}-1 & 2 \\ 2 & 1\end{pmatrix}.$$

## Verification and Consistency Checks
The computed columns of $AB$ are $\begin{pmatrix}-1\\2\end{pmatrix}$ and $\begin{pmatrix}2\\1\end{pmatrix}$, which match the independently calculated vectors $Ab_1$ and $Ab_2$ entry for entry.
