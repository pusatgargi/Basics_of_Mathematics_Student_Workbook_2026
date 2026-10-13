# Problem 13: Undoing a Composite Transformation

## Problem Statement
The matrices

$$S=\begin{pmatrix}2&0\\0&1\end{pmatrix},\qquad H=\begin{pmatrix}1&1\\0&1\end{pmatrix}$$

describe nonuniform scaling and shear. For $T=HS$, find $T^{-1}$ in two ways:

1. first compute $T$, then its inverse,
2. use $(HS)^{-1}=S^{-1}H^{-1}$.

Compare the results. Additionally compute $H^{-1}S^{-1}$ and verify that the incorrect order gives a different matrix. Explain the rule: “when undoing a composition of operations, we undo them from the end.”

## Theoretical Background and Concepts
The product $T = HS$ represents scaling by $S$ followed by horizontal shear by $H$.
- $S^{-1} = \begin{pmatrix}\frac{1}{2}&0\\0&1\end{pmatrix}$ reverses horizontal scaling by halving the $x$-coordinate.
- $H^{-1} = \begin{pmatrix}1&-1\\0&1\end{pmatrix}$ reverses horizontal shear by shifting $x$ back by $-y$.
To undo $HS$, the shear $H$ must be undone first by $H^{-1}$, and then the scaling $S$ undone by $S^{-1}$. Thus, $(HS)^{-1} = S^{-1}H^{-1}$.

## Detailed Step-by-Step Solution
1. **Method 1: Compute $T$ first, then its inverse:**
   $$T = HS = \begin{pmatrix}1&1\\0&1\end{pmatrix}\begin{pmatrix}2&0\\0&1\end{pmatrix} = \begin{pmatrix}1(2)+1(0) & 1(0)+1(1)\\0(2)+1(0) & 0(0)+1(1)\end{pmatrix} = \begin{pmatrix}2&1\\0&1\end{pmatrix}.$$
   Now invert $T$ using the $2\times2$ inverse rule:
   $$\det T = 2 \cdot 1 - 1 \cdot 0 = 2.$$
   $$T^{-1} = \frac{1}{2}\begin{pmatrix}1 & -1 \\ 0 & 2\end{pmatrix} = \begin{pmatrix}\frac{1}{2} & -\frac{1}{2} \\ 0 & 1\end{pmatrix}.$$

2. **Method 2: Use $(HS)^{-1} = S^{-1}H^{-1}$:**
   The inverses reversing scaling and shear are:
   $$S^{-1} = \begin{pmatrix}\frac{1}{2} & 0 \\ 0 & 1\end{pmatrix},\qquad H^{-1} = \begin{pmatrix}1 & -1 \\ 0 & 1\end{pmatrix}.$$
   Multiplying in reverse order:
   $$S^{-1}H^{-1} = \begin{pmatrix}\frac{1}{2} & 0 \\ 0 & 1\end{pmatrix}\begin{pmatrix}1 & -1 \\ 0 & 1\end{pmatrix} = \begin{pmatrix}\frac{1}{2} & -\frac{1}{2} \\ 0 & 1\end{pmatrix}.$$
   Both methods yield the exact same inverse matrix: $T^{-1} = S^{-1}H^{-1}$.

3. **Compute the incorrect order $H^{-1}S^{-1}$:**
   $$H^{-1}S^{-1} = \begin{pmatrix}1 & -1 \\ 0 & 1\end{pmatrix}\begin{pmatrix}\frac{1}{2} & 0 \\ 0 & 1\end{pmatrix} = \begin{pmatrix}\frac{1}{2} & -1 \\ 0 & 1\end{pmatrix}.$$

4. **Comparison of distinguishing top-right entries:**
   - In $S^{-1}H^{-1}$, the top-right entry is:
     $$\frac{1}{2}(-1) + 0(1) = -\frac{1}{2}.$$
   - In $H^{-1}S^{-1}$, the top-right entry is:
     $$1(0) + (-1)(1) = -1.$$
   Because $-\frac{1}{2} \neq -1$, $H^{-1}S^{-1} \neq T^{-1}$.

5. **Explanation of the rule:**
   When an object is transformed by $S$ and then $H$, the result is $y = H(Sx)$. To recover $x$, the last applied operation $H$ must be undone first by applying $H^{-1}$ (yielding $Sx$), and then $S^{-1}$ is applied to yield $x$. Reversing from the end is mathematically essential because matrix operations do not commute.

## Verification and Consistency Checks
$T(S^{-1}H^{-1}) = \begin{pmatrix}2&1\\0&1\end{pmatrix}\begin{pmatrix}1/2&-1/2\\0&1\end{pmatrix} = \begin{pmatrix}1&0\\0&1\end{pmatrix} = I$.
Meanwhile, $T(H^{-1}S^{-1}) = \begin{pmatrix}2&1\\0&1\end{pmatrix}\begin{pmatrix}1/2&-1\\0&1\end{pmatrix} = \begin{pmatrix}1&-1\\0&1\end{pmatrix} \neq I$, confirming that the incorrect order fails.
