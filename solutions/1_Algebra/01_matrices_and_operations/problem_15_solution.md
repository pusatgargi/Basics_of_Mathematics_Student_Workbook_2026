# Problem 15: Associativity of Multiplication and Different Calculation Paths

## Problem Statement
Given

$$A=\begin{pmatrix}1&2&0\\0&1&1\end{pmatrix},\qquad B=\begin{pmatrix}1&0\\2&1\\-1&3\end{pmatrix},\qquad C=\begin{pmatrix}2&1\\0&-1\end{pmatrix}.$$

Compute $(AB)C$ and $A(BC)$. Compare the results and the number of intermediate operations. Explain what associativity of matrix multiplication means in this example.

## Theoretical Background and Concepts
Matrix multiplication is associative: for any dimension-compatible matrices $A, B, C$,
$$(AB)C = A(BC).$$
This means the grouping of operations does not affect the final result.

### Operation Count Convention
For ordinary dense row-column multiplication of an $m\times n$ matrix by an $n\times p$ matrix:
- The product has $mp$ entries.
- Each entry requires $n$ scalar multiplications and $n-1$ scalar additions.
- Total multiplications: $mp \cdot n = mnp$.
- Total additions: $mp \cdot (n - 1)$.

## Detailed Step-by-Step Solution
### Path 1: Computing $(AB)C$

1. **Step 1: Compute $AB$** ($A$ is $2\times3$, $B$ is $3\times2$):
   $$AB = \begin{pmatrix}1&2&0\\0&1&1\end{pmatrix}\begin{pmatrix}1&0\\2&1\\-1&3\end{pmatrix}
   =\begin{pmatrix}1\cdot1+2\cdot2+0(-1) & 1\cdot0+2\cdot1+0\cdot3\\0\cdot1+1\cdot2+1(-1) & 0\cdot0+1\cdot1+1\cdot3\end{pmatrix}
   =\begin{pmatrix}5&2\\1&4\end{pmatrix}.$$
   - Intermediate matrix size: $2\times2$.
   - Work for $AB$ ($m=2, n=3, p=2$):
     - Multiplications: $2 \cdot 3 \cdot 2 = 12$.
     - Additions: $(2 \cdot 2) \cdot (3 - 1) = 4 \cdot 2 = 8$.

2. **Step 2: Compute $(AB)C$** ($AB$ is $2\times2$, $C$ is $2\times2$):
   $$(AB)C = \begin{pmatrix}5&2\\1&4\end{pmatrix}\begin{pmatrix}2&1\\0&-1\end{pmatrix}
   =\begin{pmatrix}5\cdot2+2\cdot0 & 5\cdot1+2(-1)\\1\cdot2+4\cdot0 & 1\cdot1+4(-1)\end{pmatrix}
   =\begin{pmatrix}10&3\\2&-3\end{pmatrix}.$$
   - Work for $(AB)C$ ($m=2, n=2, p=2$):
     - Multiplications: $2 \cdot 2 \cdot 2 = 8$.
     - Additions: $(2 \cdot 2) \cdot (2 - 1) = 4 \cdot 1 = 4$.

- **Total Work for Path 1 $(AB)C$:**
  - Multiplications: $12 + 8 = 20$.
  - Additions: $8 + 4 = 12$.

---

### Path 2: Computing $A(BC)$

1. **Step 1: Compute $BC$** ($B$ is $3\times2$, $C$ is $2\times2$):
   $$BC = \begin{pmatrix}1&0\\2&1\\-1&3\end{pmatrix}\begin{pmatrix}2&1\\0&-1\end{pmatrix}
   =\begin{pmatrix}1\cdot2+0\cdot0 & 1\cdot1+0(-1)\\2\cdot2+1\cdot0 & 2\cdot1+1(-1)\\-1\cdot2+3\cdot0 & -1\cdot1+3(-1)\end{pmatrix}
   =\begin{pmatrix}2&1\\4&1\\-2&-4\end{pmatrix}.$$
   - Intermediate matrix size: $3\times2$.
   - Work for $BC$ ($m=3, n=2, p=2$):
     - Multiplications: $3 \cdot 2 \cdot 2 = 12$.
     - Additions: $(3 \cdot 2) \cdot (2 - 1) = 6 \cdot 1 = 6$.

2. **Step 2: Compute $A(BC)$** ($A$ is $2\times3$, $BC$ is $3\times2$):
   $$A(BC) = \begin{pmatrix}1&2&0\\0&1&1\end{pmatrix}\begin{pmatrix}2&1\\4&1\\-2&-4\end{pmatrix}
   =\begin{pmatrix}1\cdot2+2\cdot4+0(-2) & 1\cdot1+2\cdot1+0(-4)\\0\cdot2+1\cdot4+1(-2) & 0\cdot1+1\cdot1+1(-4)\end{pmatrix}
   =\begin{pmatrix}10&3\\2&-3\end{pmatrix}.$$
   - Work for $A(BC)$ ($m=2, n=3, p=2$):
     - Multiplications: $2 \cdot 3 \cdot 2 = 12$.
     - Additions: $(2 \cdot 2) \cdot (3 - 1) = 4 \cdot 2 = 8$.

- **Total Work for Path 2 $A(BC)$:**
  - Multiplications: $12 + 12 = 24$.
  - Additions: $6 + 8 = 14$.

---

### Comparison of Operation Counts and Intermediate Matrix Sizes
Comparing the two calculation paths:
- **$(AB)C$:** 20 multiplications, 12 additions.
- **$A(BC)$:** 24 multiplications, 14 additions.

**Explanation of the difference:**
The difference in total operations is caused by the sizes of the intermediate matrices:
- In Path 1, multiplying $A_{2\times3} B_{3\times2}$ creates a small $2\times2$ intermediate matrix with only $4$ entries. The second multiplication $(AB)_{2\times2} C_{2\times2}$ is between two small $2\times2$ matrices, which requires only $8$ multiplications.
- In Path 2, multiplying $B_{3\times2} C_{2\times2}$ creates a larger $3\times2$ intermediate matrix with $6$ entries. When $A_{2\times3}$ multiplies this $3\times2$ intermediate matrix, it requires $12$ multiplications instead of $8$.

Although both calculation paths yield the exact same final result due to associativity, Path 1 requires less computational effort.

## Verification and Consistency Checks
Both grouping paths produce the identical matrix:
$$(AB)C = A(BC) = \begin{pmatrix}10&3\\2&-3\end{pmatrix}.$$
This verifies associativity. The operation counts ($20$ vs $24$ multiplications) demonstrate that grouping factors to keep intermediate matrix dimensions smaller reduces computational complexity.
