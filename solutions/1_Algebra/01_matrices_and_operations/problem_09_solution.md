# Problem 9: Composing Transformations

## Problem Statement
Let

$$S=\begin{pmatrix}2&0\\0&1\end{pmatrix},\qquad R=\begin{pmatrix}0&-1\\1&0\end{pmatrix}.$$

The matrix $S$ describes nonuniform scaling, while $R$ describes a $90^\circ$ counterclockwise rotation.
For

$$x=\begin{pmatrix}1\\2\end{pmatrix}$$

compute $RSx$ and $SRx$. Compare the results and explain geometrically why the order of these transformations matters.

## Theoretical Background and Concepts
For any vector $\begin{pmatrix}u\\v\end{pmatrix}$, matrix multiplication maps the coordinates according to the rows of the transformation matrix. When transformations are composed, the order of multiplication represents the chronological order of operations (the rightmost transformation acts first).

## Detailed Step-by-Step Solution
### Coordinate Actions of $S$ and $R$
From the rows of matrix $S$:
- Row 1: $2u + 0v = 2u$
- Row 2: $0u + 1v = v$
Thus, the coordinate action of $S$ is:

$$S(u,v) = (2u, v).$$

From the rows of matrix $R$:
- Row 1: $0u - 1v = -v$
- Row 2: $1u + 0v = u$
Thus, the coordinate action of $R$ is:

$$R(u,v) = (-v, u).$$

### Applying the Rules in Both Orders for $x = \begin{pmatrix}1\\2\end{pmatrix}$

1. **Path 1: $RSx$ (Scaling first, then Rotation):**
   - First apply $S$ to $(1, 2)$:
     $$S(1, 2) = (2(1), 2) = (2, 2).$$
     As a vector, $Sx = \begin{pmatrix}2\\2\end{pmatrix}$.
   - Then apply $R$ to the result $(2, 2)$:
     $$R(2, 2) = (-2, 2).$$
     As a vector,
     $$RSx = \begin{pmatrix}-2\\2\end{pmatrix}.$$

2. **Path 2: $SRx$ (Rotation first, then Scaling):**
   - First apply $R$ to $(1, 2)$:
     $$R(1, 2) = (-2, 1).$$
     As a vector, $Rx = \begin{pmatrix}-2\\1\end{pmatrix}$.
   - Then apply $S$ to the result $(-2, 1)$:
     $$S(-2, 1) = (2(-2), 1) = (-4, 1).$$
     As a vector,
     $$SRx = \begin{pmatrix}-4\\1\end{pmatrix}.$$

Comparing the results:

$$RSx = \begin{pmatrix}-2\\2\end{pmatrix},\qquad SRx = \begin{pmatrix}-4\\1\end{pmatrix}.$$

### Geometric Explanation: Why the Two Paths Differ
The scaling transformation $S$ doubles the horizontal coordinate along the fixed $x$-axis.
- In **$RSx$**, $S$ acts first on the original vector, doubling its initial horizontal component ($1 \to 2$). Then rotation rotates this scaled vector by $90^\circ$.
- In **$SRx$**, the $90^\circ$ rotation occurs first. This rotation maps the original vertical coordinate ($2$) into the new horizontal position (as $-v = -2$). When $S$ is subsequently applied, it doubles this new horizontal coordinate ($-2 \to -4$).
Thus, scaling after rotation affects what was originally the **vertical** direction of the vector. Because the scaling acts along a fixed spatial axis while rotation redirects the vector's components, changing the order scales different original directions, leading to different final vectors ($RSx \neq SRx$).

## Verification and Consistency Checks
Direct matrix product comparison:
$$RS = \begin{pmatrix}0&-1\\1&0\end{pmatrix}\begin{pmatrix}2&0\\0&1\end{pmatrix} = \begin{pmatrix}0&-1\\2&0\end{pmatrix},\qquad RS\begin{pmatrix}1\\2\end{pmatrix} = \begin{pmatrix}-2\\2\end{pmatrix}.$$
$$SR = \begin{pmatrix}2&0\\0&1\end{pmatrix}\begin{pmatrix}0&-1\\1&0\end{pmatrix} = \begin{pmatrix}0&-2\\1&0\end{pmatrix},\qquad SR\begin{pmatrix}1\\2\end{pmatrix} = \begin{pmatrix}-4\\1\end{pmatrix}.$$
The matrix products $RS$ and $SR$ are unequal ($RS \neq SR$), confirming that the transformations do not commute.
