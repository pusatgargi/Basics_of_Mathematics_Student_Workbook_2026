# Problem 7: Choosing a Method Deliberately

## Detailed Step-by-Step Solution
1. The first system is triangular, so use back-substitution. From $4y=8$, $y=2$; then $2x-2=3$, giving $x=\frac52$.
2. For three right-hand sides with the same invertible $A$, reuse the known $A^{-1}$ and compute $x_i=A^{-1}b_i$ for each. The inverse need not be recomputed.
3. For one solution with no inverse supplied, use Gaussian elimination on the augmented matrix. Computing a full inverse would do unnecessary work.

## Verification
The first solution satisfies both equations; the other choices minimize repeated or irrelevant calculations based on the stated structure.