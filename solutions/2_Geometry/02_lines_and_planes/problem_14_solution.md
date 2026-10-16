# Problem 14: Contrast: Intersection and Parallelism

## Problem Statement

From the point $P=(0,0,1)$, two lines are drawn with direction vectors
$$v_1=(2,1,-1),\qquad v_2=(2,1,0).$$
For each line, analyze its position relative to the plane $z=0$.

For the line that intersects the plane, find the intersection point. For the other line, explain how you can recognize parallelism without solving an equation.

## Theoretical Background and Concepts

Let $P = (x_0, y_0, z_0)$ be a starting point and let $L: \vec{x}(t) = P + t\vec{v}$ be a line with direction vector $\vec{v} = (v_x, v_y, v_z)$. We wish to analyze the position of $L$ relative to a plane $\Pi: \vec{n} \cdot \vec{x} = d$.

1. **The Coordinate Plane $z = 0$**:
   The equation $z = 0$ (or $0x + 0y + 1z = 0$) describes the horizontal **$xy$-plane** in $\mathbb{R}^3$. Its normal vector is the standard vertical unit vector:
   $$\vec{n} = \mathbf{k} = (0, 0, 1).$$
   For any vector $\vec{v} = (v_x, v_y, v_z)$, the dot product with $\vec{n} = (0, 0, 1)$ simply extracts the $z$-component of $\vec{v}$:
   $$\vec{n} \cdot \vec{v} = (0)(v_x) + (0)(v_y) + (1)(v_z) = v_z.$$

2. **Relative Position Criterion for the Plane $z = 0$**:
   - **Intersection at One Point ($v_z \neq 0$)**: If the vertical component $v_z$ of the direction vector is non-zero, moving along the line changes the height $z(t) = z_0 + t v_z$, so the line must cross the plane $z = 0$ at the unique parameter value $t = -z_0 / v_z$.
   - **Parallelism ($v_z = 0$)**: If the vertical component $v_z = 0$, moving along the line produces no vertical change ($z(t) = z_0$ for all $t \in \mathbb{R}$). Since $P = (0, 0, 1)$ starts at height $z_0 = 1 \neq 0$, the line stays at height $z = 1$ forever and is strictly parallel to the plane $z = 0$.

## Detailed Step-by-Step Solution

### Step 1: Write the Parametric Equations of Both Lines

Both lines pass through the point $P = (0, 0, 1)$:

1. **First Line $L_1$** with direction vector $\vec{v}_1 = (2, 1, -1)$:
   $$L_1: (x, y, z) = (0, 0, 1) + t(2, 1, -1) = (2t,\; t,\; 1 - t), \quad t \in \mathbb{R}.$$
2. **Second Line $L_2$** with direction vector $\vec{v}_2 = (2, 1, 0)$:
   $$L_2: (x, y, z) = (0, 0, 1) + s(2, 1, 0) = (2s,\; s,\; 1), \quad s \in \mathbb{R}.$$

The plane $\Pi: z = 0$ has normal vector $\vec{n} = (0, 0, 1)$ and right-hand side $d = 0$.

---

### Step 2: Analyze Line $L_1$ and Find Its Intersection Point with $z = 0$

#### Position Analysis for $L_1$:
We compute the dot product of the plane's normal vector $\vec{n} = (0, 0, 1)$ and $L_1$'s direction vector $\vec{v}_1 = (2, 1, -1)$:
$$\vec{n} \cdot \vec{v}_1 = (0)(2) + (0)(1) + (1)(-1) = -1 \neq 0.$$
Because $\vec{n} \cdot \vec{v}_1 \neq 0$ (the direction vector has a non-zero vertical component $v_{1,z} = -1$), **the line $L_1$ intersects the plane $z = 0$ at a single point**.

#### Finding the Intersection Point of $L_1$ with $z = 0$:
On $L_1$, the coordinates are $x = 2t$, $y = t$, and $z = 1 - t$. Substituting into the plane equation $z = 0$ gives:
$$1 - t = 0 \implies t = 1.$$
Substituting $t = 1$ back into the parametric equation of $L_1$:
$$\begin{aligned} x(1) &= 2(1) = 2, \\ y(1) &= 1, \\ z(1) &= 1 - 1 = 0. \end{aligned}$$
Therefore, **$L_1$ intersects the plane $z = 0$ at the point $I = (2, 1, 0)$**.

---

### Step 3: Analyze Line $L_2$ and Explain How to Recognize Parallelism Without Solving an Equation

#### Position Analysis for $L_2$:
Line $L_2$ passes through $P = (0, 0, 1)$ with direction vector $\vec{v}_2 = (2, 1, 0)$. **The line $L_2$ is strictly parallel to the plane $z = 0$ (and has no points in common with it).**

#### How to Recognize Parallelism Without Solving an Equation:
We can recognize immediately—purely by inspecting the given data—that $L_2$ is parallel to $z = 0$ in two closely related ways:

1. **Direct Inspection of the $z$-Component (Height Interpretation)**:
   - The plane $z = 0$ is the horizontal $xy$-plane (all points at vertical height $z = 0$).
   - The starting point $P = (0, 0, 1)$ is located at height $z = 1$ (one unit above the plane $z = 0$).
   - The direction vector $\vec{v}_2 = (2, 1, 0)$ has a **$z$-component equal to $0$** ($\Delta z = 0$). This means that moving along $\vec{v}_2$ changes only the horizontal coordinates $x$ and $y$, while the vertical height $z$ never changes at all.
   - Consequently, every point on $L_2$ remains at constant height $z = 1$ (inside the horizontal plane $z = 1$) and can never reach the plane $z = 0$.

2. **Orthogonality to the Normal Vector ($\vec{n} \cdot \vec{v}_2 = 0$)**:
   - The normal vector to the plane $z = 0$ is $\vec{n} = (0, 0, 1)$.
   - Taking the dot product mentally gives $\vec{n} \cdot \vec{v}_2 = (0, 0, 1) \cdot (2, 1, 0) = 0$.
   - Since $\vec{v}_2 \perp \vec{n}$ and $P = (0, 0, 1) \notin \{z = 0\}$, the line $L_2$ is strictly parallel to the plane $z = 0$.

## Verification and Consistency Checks

1. **Verification for $L_1$ and Intersection Point $I = (2, 1, 0)$**:
   - **Lies on $L_1$**: Setting $t = 1$ in $(0, 0, 1) + t(2, 1, -1)$ gives $(0 + 2, 0 + 1, 1 - 1) = (2, 1, 0) = I \quad \checkmark$
   - **Lies on $\Pi: z = 0$**: The $z$-coordinate of $I = (2, 1, 0)$ is $z = 0 \quad \checkmark$

2. **Verification for $L_2$**:
   - Every point on $L_2$ has the form $(x, y, z) = (2s, s, 1)$ for $s \in \mathbb{R}$.
   - The perpendicular distance from any point $(2s, s, 1)$ on $L_2$ to the plane $z = 0$ is $|z| = |1| = 1 > 0$, which is constant and independent of $s$. This confirms that $L_2$ stays at a constant distance of $1$ unit above the plane $z = 0$ for all $s \in \mathbb{R}$.
