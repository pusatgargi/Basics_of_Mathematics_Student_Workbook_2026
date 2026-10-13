# Problem 13: Undoing a Composite Transformation

## Problem Statement
The matrices

$$S=\begin{pmatrix}2&0\\0&1\end{pmatrix},\qquad H=\begin{pmatrix}1&1\\0&1\end{pmatrix}$$

describe nonuniform scaling and shear. For $T=HS$, find $T^{-1}$ in two ways:

1. first compute $T$, then its inverse,
2. use $(HS)^{-1}=S^{-1}H^{-1}$.

Compare the results. Additionally compute $H^{-1}S^{-1}$ and verify that the incorrect order gives a different matrix. Explain the rule: “when undoing a composition of operations, we undo them from the end.”

## Theoretical Background and Concepts
For two invertible transformations represented by matrices $S$ and $H$, the composition $T = HS$ applies $S$ first, then $H$.
The inverse transformation $(HS)^{-1}$ must undo these operations in the **reverse chronological order**:
$$(HS)^{-1} = S^{-1}H^{-1}.$$
If one were to apply the inverses in the original forward order ($H^{-1}S^{-1}$), the operations would not cancel:
$$(H^{-1}S^{-1})(HS) = H^{-1}(S^{-1}H)S \neq I,$$
because $S^{-1}$ and $H$ do not commute in general.

## Detailed Step-by-Step Solution
1. **Method 1: Compute $T$ first, then its inverse:**
   $$T = HS = \begin{pmatrix}1&1\\0&1\end{pmatrix}\begin{pmatrix}2&0\\0&1\end{pmatrix} = \begin{pmatrix}1(2)+1(0) & 1(0)+1(1) \\ 0(2)+1(0) & 0(0)+1(1)\end{pmatrix} = \begin{pmatrix}2&1\\0&1\end{pmatrix}.$$
   Now invert $T$:
   $$\det T = (2)(1) - (1)(0) = 2.$$
   $$T^{-1} = \frac{1}{2}\begin{pmatrix}1 & -1 \\ 0 & 2\end{pmatrix} = \begin{pmatrix}\frac{1}{2} & -\frac{1}{2} \\ 0 & 1\end{pmatrix}.$$

2. **Method 2: Use $(HS)^{-1} = S^{-1}H^{-1}$:**
   First compute individual inverses:
   - For $S = \begin{pmatrix}2&0\\0&1\end{pmatrix}$: $\det S = 2$, so $S^{-1} = \begin{pmatrix}\frac{1}{2}&0\\0&1\end{pmatrix}$.
   - For $H = \begin{pmatrix}1&1\\0&1\end{pmatrix}$: $\det H = 1$, so $H^{-1} = \begin{pmatrix}1&-1\\0&1\end{pmatrix}$.

   Now multiply in reverse order:
   $$S^{-1}H^{-1} = \begin{pmatrix}\frac{1}{2}&0\\0&1\end{pmatrix}\begin{pmatrix}1&-1\\0&1\end{pmatrix} = \begin{pmatrix}\frac{1}{2}(1) & \frac{1}{2}(-1) \\ 0(1)+1(0) & 0(-1)+1(1)\end{pmatrix} = \begin{pmatrix}\frac{1}{2} & -\frac{1}{2} \\ 0 & 1\end{pmatrix}.$$
   Both methods yield identical results: $T^{-1} = S^{-1}H^{-1}$.

3. **Compute $H^{-1}S^{-1}$ (the incorrect order):**
   $$H^{-1}S^{-1} = \begin{pmatrix}1&-1\\0&1\end{pmatrix}\begin{pmatrix}\frac{1}{2}&0\\0&1\end{pmatrix} = \begin{pmatrix}1\left(\frac{1}{2}\right) & -1(1) \\ 0 & 1(1)\end{pmatrix} = \begin{pmatrix}\frac{1}{2} & -1 \\ 0 & 1\end{pmatrix}.$$
   Notice that:
   $$\begin{pmatrix}\frac{1}{2} & -1 \\ 0 & 1\end{pmatrix} \neq \begin{pmatrix}\frac{1}{2} & -\frac{1}{2} \\ 0 & 1\end{pmatrix} = T^{-1}.$$
   The entry in row 1, column 2 is $-1$ instead of $-\frac{1}{2}$.

4. **Explanation of the rule:**
   When an object undergoes transformation $S$ and then $H$, the current state is $y = H(Sx)$. To recover the initial state $x$, the outer operation $H$ must be stripped away first by applying $H^{-1}$ (yielding $Sx$), and only then can $S^{-1}$ be applied to yield $x$. Reversing from the end is mathematically necessary because matrix operations are not commutative.

## Verification and Consistency Checks
Multiply $T$ by $T^{-1}$:
$$T T^{-1} = \begin{pmatrix}2&1\\0&1\end{pmatrix}\begin{pmatrix}\frac{1}{2}&-\frac{1}{2}\\0&1\end{pmatrix} = \begin{pmatrix}2(1/2)+0 & 2(-1/2)+1(1) \\ 0 & 0+1(1)\end{pmatrix} = \begin{pmatrix}1&0\\0&1\end{pmatrix} = I.$$
Multiply $T$ by the incorrect order $H^{-1}S^{-1}$:
$$T (H^{-1}S^{-1}) = \begin{pmatrix}2&1\\0&1\end{pmatrix}\begin{pmatrix}\frac{1}{2}&-1\\0&1\end{pmatrix} = \begin{pmatrix}1 & -2+1 \\ 0 & 1\end{pmatrix} = \begin{pmatrix}1&-1\\0&1\end{pmatrix} \neq I.$$
This clearly demonstrates that $H^{-1}S^{-1}$ fails to invert $T$.
