# Problem 12: Intersection Line of Two Planes

## Problem Statement

Find a parametric equation of the line that is the intersection of
$$x+y+z=3,\qquad x-y+z=1.$$
Find its direction vector in two ways: from the system of equations and from the cross product of the normal vectors. Compare the results.

## Theoretical Background and Concepts

In $\mathbb{R}^3$, two non-parallel planes
$$\Pi_1: a_1 x + b_1 y + c_1 z = d_1 \qquad \text{and} \qquad \Pi_2: a_2 x + b_2 y + c_2 z = d_2$$
intersect along a straight line $L = \Pi_1 \cap \Pi_2$. We can construct the parametric equation of $L$ and determine its direction vector via two complementary viewpoints:

1. **Algebraic Approach (Solving the Underdetermined Linear System)**:
   A point $(x, y, z)$ lies on $L = \Pi_1 \cap \Pi_2$ if and only if it satisfies both plane equations simultaneously:
   $$\begin{cases} a_1 x + b_1 y + c_1 z = d_1, \\ a_2 x + b_2 y + c_2 z = d_2. \end{cases}$$
   Because this is a system of two independent linear equations in three unknowns $(x, y, z)$, its solution set has $3 - 2 = 1$ degree of freedom (one free parameter $t \in \mathbb{R}$). Expressing $(x, y, z)$ in terms of $t$ directly yields the parametric equation $(x, y, z) = P_0 + t\vec{v}_{\text{alg}}$.

2. **Geometric Approach (Cross Product of the Normal Vectors)**:
   Because the intersection line $L$ lies inside $\Pi_1$, its direction vector $\vec{v}$ must be orthogonal to $\Pi_1$'s normal vector $\vec{n}_1$ ($\vec{v} \perp \vec{n}_1$). Simultaneously, because $L$ lies inside $\Pi_2$, $\vec{v}$ must also be orthogonal to $\Pi_2$'s normal vector $\vec{n}_2$ ($\vec{v} \perp \vec{n}_2$).
   In $\mathbb{R}^3$, the cross product of two non-parallel vectors produces a vector perpendicular to both:
   $$\vec{v}_{\text{cross}} = \vec{n}_1 \times \vec{n}_2.$$
   Combining $\vec{v}_{\text{cross}}$ with any single particular point $P_0 \in \Pi_1 \cap \Pi_2$ gives the parametric equation of the line:
   $$L: \vec{x}(s) = P_0 + s(\vec{n}_1 \times \vec{n}_2), \quad s \in \mathbb{R}.$$

## Detailed Step-by-Step Solution

### Step 1: Method 1 — Finding the Line and Direction Vector from the System of Equations

We solve the system of two linear equations in three variables:
$$\begin{cases} x + y + z = 3 & \text{(Equation 1)} \\ x - y + z = 1 & \text{(Equation 2)} \end{cases}$$

1. **Eliminate $x$ and $z$ to find $y$**:
   Subtracting Equation (2) from Equation (1) gives:
   $$(x + y + z) - (x - y + z) = 3 - 1 \implies 2y = 2 \implies y = 1.$$
2. **Substitute $y = 1$ back into Equation (1)**:
   $$x + 1 + z = 3 \implies x + z = 2.$$
3. **Introduce a free parameter $t \in \mathbb{R}$**:
   Setting $z = t$ (where $t \in \mathbb{R}$), we solve for $x$:
   $$x = 2 - t.$$
   Writing all three coordinates in terms of $t$:
   $$\begin{cases} x = 2 - t, \\ y = 1 + 0t, \\ z = 0 + t, \end{cases} \quad t \in \mathbb{R}.$$

In vector parametric form, the intersection line is:
$$L: (x, y, z) = (2, 1, 0) + t(-1, 0, 1), \quad t \in \mathbb{R}.$$
From this parameterization, we obtain:
- **Reference point**: $P_0 = (2, 1, 0)$,
- **Direction vector (from the system)**: $\vec{v}_{\text{alg}} = (-1, 0, 1)$.

*(Note: If we instead chose $x = t$ as the free parameter, then $z = 2 - t$, yielding $(x, y, z) = (0, 1, 2) + t(1, 0, -1)$ with direction vector $\vec{v}_{\text{alg}}' = (1, 0, -1) = -\vec{v}_{\text{alg}}$.)*

---

### Step 2: Method 2 — Finding the Direction Vector from the Cross Product of Normal Vectors

From the two plane equations:
- $\Pi_1: x + y + z = 3$ has normal vector $\vec{n}_1 = (1, 1, 1)$.
- $\Pi_2: x - y + z = 1$ has normal vector $\vec{n}_2 = (1, -1, 1)$.

Since the intersection line lies in both planes, its direction vector is perpendicular to both $\vec{n}_1$ and $\vec{n}_2$, given by their cross product:
$$\vec{v}_{\text{cross}} = \vec{n}_1 \times \vec{n}_2 = \begin{vmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ 1 & 1 & 1 \\ 1 & -1 & 1 \end{vmatrix}.$$
Computing each component via $2 \times 2$ minors:
$$\begin{aligned} (\vec{v}_{\text{cross}})_x &= (1)(1) - (1)(-1) = 1 - (-1) = 2, \\ (\vec{v}_{\text{cross}})_y &= (1)(1) - (1)(1) = 1 - 1 = 0, \\ (\vec{v}_{\text{cross}})_z &= (1)(-1) - (1)(1) = -1 - 1 = -2. \end{aligned}$$
Thus, the cross product yields the direction vector:
$$\vec{v}_{\text{cross}} = (2, 0, -2).$$
Using the point $P_0 = (2, 1, 0)$ (found by setting $z = 0$ in $x + z = 2, y = 1$), the parametric equation using $\vec{v}_{\text{cross}}$ is:
$$L: (x, y, z) = (2, 1, 0) + s(2, 0, -2), \quad s \in \mathbb{R}.$$

---

### Step 3: Compare the Two Results

Comparing the direction vector from the system of equations, $\vec{v}_{\text{alg}} = (-1, 0, 1)$ (or $\vec{v}_{\text{alg}}' = (1, 0, -1)$), with the direction vector from the cross product, $\vec{v}_{\text{cross}} = (2, 0, -2)$:
$$\vec{v}_{\text{cross}} = (2, 0, -2) = -2(-1, 0, 1) = -2\vec{v}_{\text{alg}} = 2\vec{v}_{\text{alg}}'.$$

**Comparison and Geometric Explanation**:
- The two direction vectors $\vec{v}_{\text{alg}} = (-1, 0, 1)$ and $\vec{v}_{\text{cross}} = (2, 0, -2)$ are **collinear (non-zero scalar multiples of each other)**, differing only by the scalar factor $-2$.
- A line's direction vector is only unique up to multiplication by a non-zero scalar $k \neq 0$: replacing $\vec{v}$ by $k\vec{v}$ (equivalent to the parameter substitution $t = -2s$) sweeps out the **exact same geometric line** in $\mathbb{R}^3$.
- Both vectors have a second component of $0$ ($v_y = 0$), reflecting the geometric fact that the line of intersection lies entirely in the horizontal plane $y = 1$, while $x$ and $z$ change at equal and opposite rates ($\Delta x = -\Delta z$).

## Verification and Consistency Checks

1. **Verify That the Parametric Line Lies in Both Planes for All $t \in \mathbb{R}$**:
   Substitute $(x, y, z) = (2 - t,\; 1,\; t)$ into both plane equations:
   - **Plane $\Pi_1$ ($x + y + z = 3$)**:
     $$(2 - t) + 1 + t = 3 + (-1 + 1)t = 3 \quad \checkmark$$
   - **Plane $\Pi_2$ ($x - y + z = 1$)**:
     $$(2 - t) - 1 + t = 1 + (-1 + 1)t = 1 \quad \checkmark$$
   Both equations are satisfied identically for all $t \in \mathbb{R}$.

2. **Verify Orthogonality of $\vec{v}_{\text{cross}} = (2, 0, -2)$ and $\vec{v}_{\text{alg}} = (-1, 0, 1)$ to $\vec{n}_1$ and $\vec{n}_2$**:
   - $\vec{n}_1 \cdot \vec{v}_{\text{alg}} = (1)(-1) + (1)(0) + (1)(1) = -1 + 0 + 1 = 0 \quad \checkmark$
   - $\vec{n}_2 \cdot \vec{v}_{\text{alg}} = (1)(-1) + (-1)(0) + (1)(1) = -1 + 0 + 1 = 0 \quad \checkmark$
   - $\vec{n}_1 \cdot \vec{v}_{\text{cross}} = (1)(2) + (1)(0) + (1)(-2) = 2 + 0 - 2 = 0 \quad \checkmark$
   - $\vec{n}_2 \cdot \vec{v}_{\text{cross}} = (1)(2) + (-1)(0) + (1)(-2) = 2 + 0 - 2 = 0 \quad \checkmark$
