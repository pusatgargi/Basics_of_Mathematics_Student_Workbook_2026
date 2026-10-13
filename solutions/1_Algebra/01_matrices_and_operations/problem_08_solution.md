# Problem 8: Row Operations and Their Reversibility

## Problem Statement
For

$$A=\begin{pmatrix}1&2&-1\\2&4&1\\-1&1&3\end{pmatrix}$$

perform, in order:
1. $R_2\leftarrow R_2-2R_1$,
2. $R_3\leftarrow R_3+R_1$,
3. interchange $R_2$ and $R_3$.

Write the matrix after each step. Then, for each of the three operations, state an operation that reverses it.

## Theoretical Background and Concepts
In row operation notation, $R_i$ denotes row $i$. The assignment arrow $R_i \leftarrow \dots$ indicates that only the named row $R_i$ is modified and replaced by the new linear combination, while all other rows remain completely unchanged.
Elementary row operations are algebraically reversible transformations: any change applied to a row can be undone by an inverse row operation without affecting the remaining rows.

## Detailed Step-by-Step Solution
Start with:

$$A=\begin{pmatrix}1&2&-1\\2&4&1\\-1&1&3\end{pmatrix}.$$

### Step 1: $R_2\leftarrow R_2-2R_1$
Here only row 2 is replaced, while $R_1$ and $R_3$ remain unchanged:

$$R_2 = (2,4,1) - 2(1,2,-1) = (2-2,\; 4-4,\; 1-(-2)) = (0,0,3).$$

The resulting matrix is:

$$A_1=\begin{pmatrix}1&2&-1\\0&0&3\\-1&1&3\end{pmatrix}.$$

### Step 2: $R_3\leftarrow R_3+R_1$
Here only row 3 is replaced, while $R_1$ and $R_2$ remain unchanged:

$$R_3 = (-1,1,3) + (1,2,-1) = (-1+1,\; 1+2,\; 3-1) = (0,3,2).$$

The resulting matrix is:

$$A_2=\begin{pmatrix}1&2&-1\\0&0&3\\0&3&2\end{pmatrix}.$$

### Step 3: Interchange $R_2$ and $R_3$
Swapping the second and third rows (while $R_1$ remains unchanged) gives:

$$A_3=\begin{pmatrix}1&2&-1\\0&3&2\\0&0&3\end{pmatrix}.$$

## Reverses of the Operations and Explanation
- **Reverse of Step 1 ($R_2 \leftarrow R_2 - 2R_1$):**
  Reversed by $R_2 \leftarrow R_2 + 2R_1$.
  *Explanation:* If $R_2' = R_2 - 2R_1$, then applying $R_2' + 2R_1 = (R_2 - 2R_1) + 2R_1 = R_2$ recovers the original row $R_2$. This works because $R_1$ was left unchanged during the forward operation.
- **Reverse of Step 2 ($R_3 \leftarrow R_3 + R_1$):**
  Reversed by $R_3 \leftarrow R_3 - R_1$.
  *Explanation:* Similarly, subtracting $R_1$ undoes adding $R_1$ since $(R_3 + R_1) - R_1 = R_3$, with $R_1$ remaining unchanged.
- **Reverse of Step 3 (Interchanging $R_2$ and $R_3$):**
  Reversed by interchanging $R_2$ and $R_3$ again.
  *Explanation:* Swapping the same two rows a second time restores each row to its original position.

## Verification and Consistency Checks
Each row operation modifies only the target row while keeping the reference rows intact. Applying the inverse operations in reverse order:
1. Interchange $R_2$ and $R_3$ on $A_3$ restores $A_2$.
2. $R_3 \leftarrow R_3 - R_1$ on $A_2$ restores $A_1$.
3. $R_2 \leftarrow R_2 + 2R_1$ on $A_1$ restores the initial matrix $A$.
This confirms that all row operations are completely reversible.
