# Problem 10: Detecting Dependence

## Detailed Step-by-Step Solution
The second row is twice the first:
$(2,4,6)=2(1,2,3)$. Therefore the rows are linearly dependent, so the determinant is zero:

$$\det\begin{pmatrix}1&2&3\\2&4&6\\0&1&5\end{pmatrix}=0.$$

A square matrix with dependent rows is singular and therefore not invertible.

## Verification
The row dependence itself is sufficient to conclude that the determinant vanishes.