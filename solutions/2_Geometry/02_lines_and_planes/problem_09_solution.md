# Problem 9: Distances

## Problem Statement

Compute:
1. the distance from $P=(2,3)$ to the line $3x+4y-10=0$,
2. the distance from $Q=(2,-1,3)$ to the plane $2x-2y+z-4=0$.

Compare the two formulas and explain their common connection with the normal direction.

## Theoretical Background and Concepts

The **Euclidean distance** from a point to a geometric set (such as a line in $\mathbb{R}^2$ or a plane in $\mathbb{R}^3$) is defined as the shortest distance from the point to any point on the set. By the Pythagorean theorem, the shortest segment connecting a point to a line or a plane is always the **perpendicular** segment—that is, the segment parallel to the **normal vector** $\vec{n}$.

1. **Distance from a Point to a Line in $\mathbb{R}^2$**:
   Given a point $P = (x_0, y_0)$ and a line $L$ in general form:
   $$L: ax + by + c = 0$$
   with normal vector $\vec{n} = (a, b)$ and length $\|\vec{n}\| = \sqrt{a^2 + b^2}$, the perpendicular distance from $P$ to $L$ is:
   $$d(P, L) = \frac{|ax_0 + by_0 + c|}{\sqrt{a^2 + b^2}}.$$

2. **Distance from a Point to a Plane in $\mathbb{R}^3$**:
   Given a point $Q = (x_0, y_0, z_0)$ and a plane $\Pi$ in general form:
   $$\Pi: ax + by + cz + d = 0$$
   with normal vector $\vec{n} = (a, b, c)$ and length $\|\vec{n}\| = \sqrt{a^2 + b^2 + c^2}$, the perpendicular distance from $Q$ to $\Pi$ is:
   $$d(Q, \Pi) = \frac{|ax_0 + by_0 + cz_0 + d|}{\sqrt{a^2 + b^2 + c^2}}.$$

3. **Unified Vector Derivation via Orthogonal Projection**:
   In any dimension $\mathbb{R}^k$, an affine hyperplane $H$ is defined by $\vec{n} \cdot \vec{x} + c = 0$. If $X_0$ is any point on $H$, then $\vec{n} \cdot X_0 + c = 0$, so $c = -\vec{n} \cdot X_0$. For any external point $P$, the displacement vector $\overrightarrow{X_0 P} = P - X_0$ has a perpendicular component along the unit normal vector $\hat{n} = \frac{\vec{n}}{\|\vec{n}\|}$ whose magnitude is:
   $$d(P, H) = \left|\overrightarrow{X_0 P} \cdot \hat{n}\right| = \frac{|(P - X_0) \cdot \vec{n}|}{\|\vec{n}\|} = \frac{|\vec{n} \cdot P - \vec{n} \cdot X_0|}{\|\vec{n}\|} = \frac{|\vec{n} \cdot P + c|}{\|\vec{n}\|}.$$

## Detailed Step-by-Step Solution

### Part 1: Distance from $P = (2, 3)$ to the Line $3x + 4y - 10 = 0$

#### Step 1.1: Identify the Parameters
From the line equation $3x + 4y - 10 = 0$ and the point $P = (2, 3)$:
- Coefficients of the normal vector $\vec{n} = (a, b)$: $a = 3$, $b = 4$,
- Constant term: $c = -10$,
- Coordinates of the point $P$: $x_0 = 2$, $y_0 = 3$.

#### Step 1.2: State and Apply the Distance Formula
The point-to-line distance formula in $\mathbb{R}^2$ is:
$$d(P, L) = \frac{|ax_0 + by_0 + c|}{\sqrt{a^2 + b^2}}.$$

1. **Evaluate the numerator $|ax_0 + by_0 + c|$**:
   $$|3(2) + 4(3) - 10| = |6 + 12 - 10| = |8| = 8.$$
2. **Evaluate the denominator $\|\vec{n}\| = \sqrt{a^2 + b^2}$**:
   $$\sqrt{3^2 + 4^2} = \sqrt{9 + 16} = \sqrt{25} = 5.$$
3. **Divide numerator by denominator**:
   $$d(P, L) = \frac{8}{5} = 1.6.$$

---

### Part 2: Distance from $Q = (2, -1, 3)$ to the Plane $2x - 2y + z - 4 = 0$

#### Step 2.1: Identify the Parameters
From the plane equation $2x - 2y + z - 4 = 0$ and the point $Q = (2, -1, 3)$:
- Coefficients of the normal vector $\vec{n} = (a, b, c)$: $a = 2$, $b = -2$, $c = 1$,
- Constant term: $d = -4$,
- Coordinates of the point $Q$: $x_0 = 2$, $y_0 = -1$, $z_0 = 3$.

#### Step 2.2: State and Apply the Distance Formula
The point-to-plane distance formula in $\mathbb{R}^3$ is:
$$d(Q, \Pi) = \frac{|ax_0 + by_0 + cz_0 + d|}{\sqrt{a^2 + b^2 + c^2}}.$$

1. **Evaluate the numerator $|ax_0 + by_0 + cz_0 + d|$**:
   $$|2(2) + (-2)(-1) + 1(3) - 4| = |4 + 2 + 3 - 4| = |5| = 5.$$
2. **Evaluate the denominator $\|\vec{n}\| = \sqrt{a^2 + b^2 + c^2}$**:
   $$\sqrt{2^2 + (-2)^2 + 1^2} = \sqrt{4 + 4 + 1} = \sqrt{9} = 3.$$
3. **Divide numerator by denominator**:
   $$d(Q, \Pi) = \frac{5}{3}.$$

---

### Part 3: Comparison of the Two Formulas and Their Connection with the Normal Direction

Comparing the two formulas side by side:
$$d_{\text{2D}}(P, L) = \frac{|ax_0 + by_0 + c|}{\sqrt{a^2 + b^2}} \qquad \text{vs.} \qquad d_{\text{3D}}(Q, \Pi) = \frac{|ax_0 + by_0 + cz_0 + d|}{\sqrt{a^2 + b^2 + c^2}},$$
we observe that both are instances of the single geometric identity:
$$\text{Distance} = \frac{|\vec{n} \cdot \vec{p} + \text{const}|}{\|\vec{n}\|}.$$

1. **Role of the Numerator ($|\vec{n} \cdot \vec{p} + \text{const}|$)**:
   When a point lies directly *on* the line or plane, substituting its coordinates into the general equation gives $0$. When the point lies *off* the line or plane, the expression $\vec{n} \cdot \vec{p} + \text{const} = \vec{n} \cdot (\vec{p} - \vec{p}_{\text{ref}})$ measures how far the point fails to satisfy the equation, scaled by the length of $\vec{n}$.
2. **Role of the Denominator ($\|\vec{n}\|$)**:
   Because multiplying the equation of a line or plane by a non-zero constant $k$ scales the normal vector $\vec{n}$ by $k$ without changing the geometric line or plane itself, dividing by the length $\|\vec{n}\|$ normalizes $\vec{n}$ into a **unit normal vector** $\hat{n} = \frac{\vec{n}}{\|\vec{n}\|}$.
3. **Connection to the Normal Direction**:
   In both $\mathbb{R}^2$ (for a line) and $\mathbb{R}^3$ (for a plane), there is a **single perpendicular direction** (codimension $1$) given by $\vec{n}$. Any displacement vector from a point on the line/plane to the external point $P$ or $Q$ can be decomposed into a component parallel to the line/plane and a component along the normal $\vec{n}$. Only the component along the normal $\vec{n}$ contributes to the shortest distance, which is why both formulas project the displacement vector onto $\vec{n}$.

## Verification and Consistency Checks

We can independently verify both distances by finding the actual closest point (orthogonal projection) on the line/plane and computing the Euclidean distance between the two points:

1. **Verification for Part 1 ($P = (2, 3)$ and $L: 3x + 4y - 10 = 0$)**:
   - The line through $P = (2, 3)$ along $\vec{n} = (3, 4)$ is $(x, y) = (2 + 3t, 3 + 4t)$.
   - Substituting into $3x + 4y - 10 = 0$:
     $$3(2 + 3t) + 4(3 + 4t) - 10 = 0 \implies 6 + 9t + 12 + 16t - 10 = 0 \implies 25t + 8 = 0 \implies t = -\frac{8}{25}.$$
   - The displacement vector from $P$ to the foot of the perpendicular $P'$ is $t\vec{n} = -\frac{8}{25}(3, 4)$, whose Euclidean length is:
     $$\|P' - P\| = |t|\,\|\vec{n}\| = \frac{8}{25}\sqrt{3^2 + 4^2} = \frac{8}{25} \cdot 5 = \frac{8}{5} \quad \checkmark$$

2. **Verification for Part 2 ($Q = (2, -1, 3)$ and $\Pi: 2x - 2y + z - 4 = 0$)**:
   - The line through $Q = (2, -1, 3)$ along $\vec{n} = (2, -2, 1)$ is $(x, y, z) = (2 + 2t, -1 - 2t, 3 + t)$.
   - Substituting into $2x - 2y + z - 4 = 0$:
     $$2(2 + 2t) - 2(-1 - 2t) + (3 + t) - 4 = 0 \implies 4 + 4t + 2 + 4t + 3 + t - 4 = 0 \implies 9t + 5 = 0 \implies t = -\frac{5}{9}.$$
   - The displacement vector from $Q$ to the foot of the perpendicular $Q'$ is $t\vec{n} = -\frac{5}{9}(2, -2, 1)$, whose Euclidean length is:
     $$\|Q' - Q\| = |t|\,\|\vec{n}\| = \frac{5}{9}\sqrt{2^2 + (-2)^2 + 1^2} = \frac{5}{9} \cdot 3 = \frac{5}{3} \quad \checkmark$$
