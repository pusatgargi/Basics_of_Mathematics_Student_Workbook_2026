# Problem 8: Two Systems with the Same Coefficient Matrix

## Detailed Step-by-Step Solution
For each augmented matrix, use $R_2\leftarrow2R_2-R_1$:

$$
\left[\begin{array}{cc|c}2&1&5\\1&-1&1\end{array}\right]
\longrightarrow
\left[\begin{array}{cc|c}2&1&5\\0&-3&-3\end{array}\right],
$$
so $y=1$ and $x=2$.

For the second system,

$$
\left[\begin{array}{cc|c}2&1&1\\1&-1&4\end{array}\right]
\longrightarrow
\left[\begin{array}{cc|c}2&1&1\\0&-3&7\end{array}\right],
$$
so $y=-\frac73$ and $x=\frac53$.

## Verification
The same row operation produces the same coefficient row $(0,-3)$ in both cases; only the right-hand side changes because the coefficient matrices are identical.