# Problem 9: Cross Product as a Perpendicular Direction

## Problem Statement

For $u=(1,2,0)$ and $v=(0,1,3)$ compute $u\times v$. Use dot products to check perpendicularity to both vectors, compute $v\times u$, and compare the results.

## Theoretical Background and Concepts

1. **Algebraic Definition of the Cross Product (Vector Product):** For two vectors $u = (u_1, u_2, u_3)$ and $v = (v_1, v_2, v_3)$ in $\mathbb{R}^3$, their **cross product** $u \times v$ is a vector in $\mathbb{R}^3$ defined by the symbolic $3 \times 3$ determinant:
   $$u \times v = \begin{vmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ u_1 & u_2 & u_3 \\ v_1 & v_2 & v_3 \end{vmatrix} = \left(u_2 v_3 - u_3 v_2,\; u_3 v_1 - u_1 v_3,\; u_1 v_2 - u_2 v_1\right).$$

2. **Geometric Properties of the Cross Product:**
   - **Orthogonality:** The vector $u \times v$ is simultaneously perpendicular (orthogonal) to both $u$ and $v$, and therefore normal to the plane spanned by $u$ and $v$:
     $$(u \times v) \cdot u = 0 \qquad \text{and} \qquad (u \times v) \cdot v = 0.$$
   - **Orientation (Right-Hand Rule):** If the fingers of the right hand curl from $u$ toward $v$ through the smaller angle $\theta \in [0, \pi]$, the thumb points in the direction of $u \times v$.
   - **Anti-Commutativity:** Reversing the order of the two vectors reverses the orientation of the cross product while preserving its length and line of action:
     $$v \times u = -(u \times v).$$

## Detailed Step-by-Step Solution

We are given the vectors in $\mathbb{R}^3$:
$$u = (1, 2, 0) \qquad \text{and} \qquad v = (0, 1, 3).$$

### Step 1: Compute $u \times v$

Using the component formula for the cross product,
$$u \times v = (u_2 v_3 - u_3 v_2,\; u_3 v_1 - u_1 v_3,\; u_1 v_2 - u_2 v_1),$$
we substitute $u = (u_1, u_2, u_3) = (1, 2, 0)$ and $v = (v_1, v_2, v_3) = (0, 1, 3)$:
- **First ($x$) component:**
  $$u_2 v_3 - u_3 v_2 = (2)(3) - (0)(1) = 6 - 0 = 6.$$
- **Second ($y$) component:**
  $$u_3 v_1 - u_1 v_3 = (0)(0) - (1)(3) = 0 - 3 = -3.$$
- **Third ($z$) component:**
  $$u_1 v_2 - u_2 v_1 = (1)(1) - (2)(0) = 1 - 0 = 1.$$

Combining the three components gives:
$$u \times v = (6, -3, 1).$$

### Step 2: Use Dot Products to Check Perpendicularity to Both Vectors

To verify that $u \times v = (6, -3, 1)$ is perpendicular to both $u$ and $v$, we compute the dot product of $u \times v$ with each vector.

1. **Dot product with $u = (1, 2, 0)$:**
   $$\begin{aligned}
   (u \times v) \cdot u &= (6)(1) + (-3)(2) + (1)(0) \\
                        &= 6 - 6 + 0 \\
                        &= 0.
   \end{aligned}$$
   Since $(u \times v) \cdot u = 0$, we have $(u \times v) \perp u$.

2. **Dot product with $v = (0, 1, 3)$:**
   $$\begin{aligned}
   (u \times v) \cdot v &= (6)(0) + (-3)(1) + (1)(3) \\
                        &= 0 - 3 + 3 \\
                        &= 0.
   \end{aligned}$$
   Since $(u \times v) \cdot v = 0$, we have $(u \times v) \perp v$.

Thus, $u \times v = (6, -3, 1)$ is confirmed to be perpendicular to both $u$ and $v$.

### Step 3: Compute $v \times u$

Applying the cross product formula with the roles of $v = (0, 1, 3)$ and $u = (1, 2, 0)$ swapped:
$$v \times u = (v_2 u_3 - v_3 u_2,\; v_3 u_1 - v_1 u_3,\; v_1 u_2 - v_2 u_1).$$
Computing each component explicitly:
- **First ($x$) component:**
  $$v_2 u_3 - v_3 u_2 = (1)(0) - (3)(2) = 0 - 6 = -6.$$
- **Second ($y$) component:**
  $$v_3 u_1 - v_1 u_3 = (3)(1) - (0)(0) = 3 - 0 = 3.$$
- **Third ($z$) component:**
  $$v_1 u_2 - v_2 u_1 = (0)(2) - (1)(1) = 0 - 1 = -1.$$

Therefore:
$$v \times u = (-6, 3, -1).$$

### Step 4: Compare $u \times v$ and $v \times u$

Comparing the two results component by component:
$$u \times v = (6, -3, 1) \qquad \text{and} \qquad v \times u = (-6, 3, -1) = -(6, -3, 1) = -(u \times v).$$
- **What is the same:** Both vectors have the **exact same length** ($\|u \times v\| = \|v \times u\| = \sqrt{36 + 9 + 1} = \sqrt{46}$) and lie along the **exact same line** perpendicular to the plane spanned by $u$ and $v$.
- **What is different:** Every component has the **opposite sign**, meaning $v \times u$ points in the **exact opposite orientation (sense)** to $u \times v$. This illustrates that the cross product is **anti-commutative** ($v \times u = -u \times v$), which geometrically reflects the right-hand rule: curling the fingers from $v$ to $u$ points the thumb in the opposite direction of curling from $u$ to $v$.

## Verification and Consistency Checks

1. **Lagrange's Identity Check ($\|u \times v\|^2 = \|u\|^2\|v\|^2 - (u \cdot v)^2$):** Every cross product must satisfy Lagrange's identity. Let us compute both sides independently:
   - **Left-hand side:**
     $$\|u \times v\|^2 = 6^2 + (-3)^2 + 1^2 = 36 + 9 + 1 = 46.$$
   - **Right-hand side:**
     $$\|u\|^2 = 1^2 + 2^2 + 0^2 = 1 + 4 + 0 = 5,$$
     $$\|v\|^2 = 0^2 + 1^2 + 3^2 = 0 + 1 + 9 = 10,$$
     $$u \cdot v = (1)(0) + (2)(1) + (0)(3) = 0 + 2 + 0 = 2.$$
     Therefore:
     $$\|u\|^2\|v\|^2 - (u \cdot v)^2 = (5)(10) - 2^2 = 50 - 4 = 46.$$
   Both sides equal $46$, confirming the magnitude and components of $u \times v$. $\checkmark$

2. **Orthogonality Check for $v \times u$:**
   $$(v \times u) \cdot u = (-6)(1) + (3)(2) + (-1)(0) = -6 + 6 + 0 = 0, \quad \checkmark$$
   $$(v \times u) \cdot v = (-6)(0) + (3)(1) + (-1)(3) = 0 + 3 - 3 = 0. \quad \checkmark$$
