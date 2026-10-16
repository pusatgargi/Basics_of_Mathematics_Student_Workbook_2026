# Problem 6: Angle Between Planes

## Problem Statement

Given
$$\Pi_1:x+y+z=1,\qquad \Pi_2:x-y=2.$$
First use the normal vectors to decide whether the planes are parallel. If not, compute the angle between them and explain why the normal vectors alone are enough for this calculation.

## Theoretical Background and Concepts

Let two planes in $\mathbb{R}^3$ be given in general form:
$$\Pi_1: a_1 x + b_1 y + c_1 z = d_1 \qquad \text{and} \qquad \Pi_2: a_2 x + b_2 y + c_2 z = d_2,$$
with respective normal vectors $\vec{n}_1 = (a_1, b_1, c_1)$ and $\vec{n}_2 = (a_2, b_2, c_2)$.

1. **Criterion for Parallelism of Two Planes**:
   Two planes $\Pi_1$ and $\Pi_2$ are parallel ($\Pi_1 \parallel \Pi_2$) if and only if they have the same spatial orientation, which occurs if and only if their normal vectors $\vec{n}_1$ and $\vec{n}_2$ are collinear (proportional):
   $$\Pi_1 \parallel \Pi_2 \iff \vec{n}_1 = k\vec{n}_2 \quad \text{for some non-zero scalar } k \in \mathbb{R} \iff \vec{n}_1 \times \vec{n}_2 = \vec{0}.$$
   If $\vec{n}_1$ and $\vec{n}_2$ are not proportional, the two planes must intersect along a straight line.

2. **Angle Between Two Planes**:
   By convention, the **angle $\theta$ between two intersecting planes** (the acute or right dihedral angle, $\theta \in [0, \frac{\pi}{2}]$) is defined as the angle between two lines, one in each plane, drawn perpendicular to their line of intersection at a common point.
   Using the normal vectors $\vec{n}_1$ and $\vec{n}_2$, this angle $\theta \in [0, \frac{\pi}{2}]$ is given by the dot product formula:
   $$\cos\theta = \frac{|\vec{n}_1 \cdot \vec{n}_2|}{\|\vec{n}_1\|\,\|\vec{n}_2\|},$$
   where:
   - $\vec{n}_1 \cdot \vec{n}_2 = a_1 a_2 + b_1 b_2 + c_1 c_2$ is the scalar (dot) product,
   - $\|\vec{n}_i\| = \sqrt{a_i^2 + b_i^2 + c_i^2}$ is the Euclidean length of $\vec{n}_i$,
   - The absolute value $|\vec{n}_1 \cdot \vec{n}_2|$ ensures that $\cos\theta \ge 0$, selecting the acute (or right) angle $\theta \in [0, \frac{\pi}{2}]$ regardless of whether $\vec{n}_1$ and $\vec{n}_2$ are chosen to point "inward" or "outward."
   In particular, two planes are **orthogonal (perpendicular)** ($\theta = \frac{\pi}{2} = 90^\circ$) if and only if $\vec{n}_1 \cdot \vec{n}_2 = 0$.

## Detailed Step-by-Step Solution

### Step 1: Identify the Normal Vectors of Both Planes

Reading the coefficients of $x$, $y$, and $z$ from each plane's equation:
- For $\Pi_1: 1x + 1y + 1z = 1$, a normal vector is:
  $$\vec{n}_1 = (1, 1, 1).$$
- For $\Pi_2: 1x - 1y + 0z = 2$, a normal vector is:
  $$\vec{n}_2 = (1, -1, 0).$$

### Step 2: Decide Whether the Planes Are Parallel

We test whether there exists a scalar $k \in \mathbb{R}$ such that $\vec{n}_1 = k\vec{n}_2$:
$$(1, 1, 1) = k(1, -1, 0) = (k, -k, 0).$$
Comparing components:
- From the first component, $k = 1$.
- From the second component, $1 = -k \implies k = -1$ (contradiction).
- From the third component, $1 = 0$ (impossible).

Since no such scalar $k$ exists, $\vec{n}_1$ and $\vec{n}_2$ are not parallel. Therefore, **the planes $\Pi_1$ and $\Pi_2$ are not parallel**; they intersect in a line.

### Step 3: Compute the Angle Between the Planes

To find the angle $\theta \in [0, \frac{\pi}{2}]$ between $\Pi_1$ and $\Pi_2$, we apply the formula:
$$\cos\theta = \frac{|\vec{n}_1 \cdot \vec{n}_2|}{\|\vec{n}_1\|\,\|\vec{n}_2\|}.$$

1. **Compute the dot product $\vec{n}_1 \cdot \vec{n}_2$**:
   $$\vec{n}_1 \cdot \vec{n}_2 = (1)(1) + (1)(-1) + (1)(0) = 1 - 1 + 0 = 0.$$

2. **Compute the norms $\|\vec{n}_1\|$ and $\|\vec{n}_2\|$**:
   $$\|\vec{n}_1\| = \sqrt{1^2 + 1^2 + 1^2} = \sqrt{1 + 1 + 1} = \sqrt{3},$$
   $$\|\vec{n}_2\| = \sqrt{1^2 + (-1)^2 + 0^2} = \sqrt{1 + 1 + 0} = \sqrt{2}.$$

3. **Substitute into the cosine formula**:
   $$\cos\theta = \frac{|0|}{\sqrt{3}\,\sqrt{2}} = \frac{0}{\sqrt{6}} = 0.$$

4. **Determine the angle $\theta$**:
   Since $\cos\theta = 0$ and $\theta \in [0, \frac{\pi}{2}]$, we obtain:
   $$\theta = \arccos(0) = \frac{\pi}{2}\text{ radians} = 90^\circ.$$

Thus, the angle between the planes $\Pi_1$ and $\Pi_2$ is **$90^\circ$ ($\frac{\pi}{2}$ radians)**, meaning the two planes are **mutually perpendicular (orthogonal)**.

### Step 4: Explain Why the Normal Vectors Alone Are Enough

Why can we determine the angle between two planes solely from their normal vectors $\vec{n}_1$ and $\vec{n}_2$, without ever finding a point on either plane or constructing their line of intersection?

1. **Translation Invariance of Angles**:
   The constant terms on the right-hand sides ($d_1 = 1$ and $d_2 = 2$) only translate the planes $\Pi_1$ and $\Pi_2$ parallel to themselves. Translating a plane without rotating it does not change the angle it makes with another plane. The orientation (tilt) of each plane in $\mathbb{R}^3$ is completely encoded in its normal vector $\vec{n}_i$.
2. **Cross-Sectional Geometry (Rotation by $90^\circ$)**:
   Imagine slicing space with a two-dimensional cross-sectional plane perpendicular to the line of intersection of $\Pi_1$ and $\Pi_2$. In this 2D cross-section:
   - The planes $\Pi_1$ and $\Pi_2$ appear as two intersecting straight lines, forming the dihedral angle $\theta$.
   - Because $\vec{n}_1 \perp \Pi_1$ and $\vec{n}_2 \perp \Pi_2$, both normal vectors lie in this exact same 2D cross-sectional plane, and each normal vector is rotated by exactly $90^\circ$ relative to its corresponding plane.
   - In planar geometry, if two rays are both rotated by $90^\circ$ (or if one is reflected), the angle between the perpendiculars is either equal to $\theta$ or supplementary ($\pi - \theta$). Taking $|\vec{n}_1 \cdot \vec{n}_2|$ automatically chooses the acute/right angle $\theta \in [0, \frac{\pi}{2}]$.

## Verification and Consistency Checks

Let us verify the $90^\circ$ angle directly by constructing the line of intersection and finding two vectors—one in $\Pi_1$ and one in $\Pi_2$—that are both perpendicular to the line of intersection:

1. **Direction of the Intersection Line $L = \Pi_1 \cap \Pi_2$**:
   The line of intersection must be perpendicular to both $\vec{n}_1$ and $\vec{n}_2$, so its direction vector is:
   $$\vec{v} = \vec{n}_1 \times \vec{n}_2 = \begin{vmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ 1 & 1 & 1 \\ 1 & -1 & 0 \end{vmatrix} = \big((1)(0)-(1)(-1),\; (1)(1)-(1)(0),\; (1)(-1)-(1)(1)\big) = (1, 1, -2).$$

2. **Vectors in Each Plane Perpendicular to $L$**:
   - In $\Pi_1$, a vector lying in $\Pi_1$ (orthogonal to $\vec{n}_1$) and perpendicular to $\vec{v}$ is:
     $$\vec{u}_1 = \vec{n}_1 \times \vec{v} = (1, 1, 1) \times (1, 1, -2) = (-3, 3, 0).$$
   - In $\Pi_2$, a vector lying in $\Pi_2$ (orthogonal to $\vec{n}_2$) and perpendicular to $\vec{v}$ is:
     $$\vec{u}_2 = \vec{n}_2 \times \vec{v} = (1, -1, 0) \times (1, 1, -2) = (2, 2, 2).$$

3. **Angle Between $\vec{u}_1$ and $\vec{u}_2$**:
   $$\vec{u}_1 \cdot \vec{u}_2 = (-3)(2) + (3)(2) + (0)(2) = -6 + 6 + 0 = 0.$$
   Since $\vec{u}_1 \cdot \vec{u}_2 = 0$, the two planes indeed meet at a right angle ($\theta = 90^\circ$).
