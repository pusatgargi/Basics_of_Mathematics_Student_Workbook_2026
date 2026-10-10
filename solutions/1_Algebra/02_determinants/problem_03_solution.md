# Problem 3: Swapping Two Rows

## Detailed Step-by-Step Solution
For
$$A=\begin{pmatrix}1&2&0\\0&3&1\\2&1&1\end{pmatrix},$$
expansion along the first row gives

$$
\det A=1(3\cdot1-1\cdot1)-2(0\cdot1-1\cdot2)=2+4=6.
$$

Swapping two rows changes the sign of the determinant, so the row-swapped matrix
$B=\begin{pmatrix}0&3&1\\1&2&0\\2&1&1\end{pmatrix}$ should have determinant $-6$.
Direct expansion along its first row confirms this:

$$
\det B=-3(1\cdot1-0\cdot2)+(1\cdot1-2\cdot2)=-3-3=-6.
$$

## Verification
The direct calculation agrees with $\det B=-\det A$.