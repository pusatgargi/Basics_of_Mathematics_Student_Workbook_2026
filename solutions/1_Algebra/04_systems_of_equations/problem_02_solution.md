# Problem 2: Gaussian Elimination — One Solution

## Detailed Step-by-Step Solution
Use the augmented matrix and perform $R_2\leftarrow R_2-2R_1$ and $R_3\leftarrow R_3-R_1$:

$$
\left[\begin{array}{ccc|c}1&1&1&6\\2&-1&1&3\\1&2&-1&2\end{array}\right]
\longrightarrow
\left[\begin{array}{ccc|c}1&1&1&6\\0&-3&-1&-9\\0&1&-2&-4\end{array}\right].
$$

Elimination gives $3y+z=9$ and $y-2z=-4$. Hence $z=3$, $y=2$, and the first equation gives $x=1$.

## Verification
Substitution gives $1+2+3=6$, $2-2+3=3$, and $1+4-3=2$, so all three equations hold.