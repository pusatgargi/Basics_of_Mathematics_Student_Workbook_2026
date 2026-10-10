# Problem 9: Composing Transformations

## Problem Statement
Let

$$S=\begin{pmatrix}2&0\\0&1\end{pmatrix},\qquad R=\begin{pmatrix}0&-1\\1&0\end{pmatrix}.$$
The matrix $S$ describes nonuniform scaling, while $R$ describes a $90^\circ$ counterclockwise rotation.
For

$$x=\begin{pmatrix}1\\2\end{pmatrix}$$
compute $RSx$ and $SRx$. Compare the results and explain geometrically why the order of these transformations matters.

## Theoretical Background and Concepts
For a vector $x$, the product $Sx$ applies scaling first, and $Rx$ applies rotation. When we compose transformations, the order matters because matrix multiplication is generally noncommutative.

## Detailed Step-by-Step Solution
First compute $Sx$:

$$Sx = \begin{pmatrix}2&0\\0&1\end{pmatrix}\begin{pmatrix}1\\2\end{pmatrix}
=\begin{pmatrix}2\\2\end{pmatrix}.$$

Then

$$RSx = R\begin{pmatrix}2\\2\end{pmatrix}
=\begin{pmatrix}0&-1\\1&0\end{pmatrix}\begin{pmatrix}2\\2\end{pmatrix}
=\begin{pmatrix}-2\\2\end{pmatrix}.$$

Now compute $Rx$:

$$Rx = \begin{pmatrix}0&-1\\1&0\end{pmatrix}\begin{pmatrix}1\\2\end{pmatrix}
=\begin{pmatrix}-2\\1\end{pmatrix}.$$

Then

$$SRx = S\begin{pmatrix}-2\\1\end{pmatrix}
=\begin{pmatrix}2&0\\0&1\end{pmatrix}\begin{pmatrix}-2\\1\end{pmatrix}
=\begin{pmatrix}-4\\1\end{pmatrix}.$$

Therefore,

$$RSx = \begin{pmatrix}-2\\2\end{pmatrix},\qquad SRx=\begin{pmatrix}-4\\1\end{pmatrix}.$$

Geometrically, the order matters because rotating and scaling are not interchangeable operations. Scaling first then rotating gives a different final vector than rotating first then scaling.

## Verification and Consistency Checks
The results are not equal, so the transformations do not commute. This matches the algebraic fact that matrices generally do not satisfy $RS=SR$.
