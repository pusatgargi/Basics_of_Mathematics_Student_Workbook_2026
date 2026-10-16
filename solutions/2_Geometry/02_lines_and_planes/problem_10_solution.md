# Problem 10: Projection of a Point onto a Plane

## Problem Statement

Find the orthogonal projection of $P=(2,1,3)$ onto the plane $x+y+z=3$, and then find the reflection of $P$ across this plane. Check that the midpoint of the segment joining the point and its reflection lies on the plane.

## Theoretical Background and Concepts

Let $\Pi: ax + by + cz = d$ be a plane in $\mathbb{R}^3$ with normal vector $\vec{n} = (a, b, c)$, and let $P = (x_0, y_0, z_0)$ be a point in space.

1. **Orthogonal Projection of a Point onto a Plane**:
   The **orthogonal projection** of $P$ onto $\Pi$, denoted $P'$, is the unique point on $\Pi$ such that the vector $\overrightarrow{PP'}$ is perpendicular to $\Pi$ (i.e., parallel to the normal vector $\vec{n}$). Geometrically, $P'$ is the "foot of the perpendicular" dropped from $P$ to the plane $\Pi$, and it is also the point on $\Pi$ closest to $P$.
   To construct $P'$:
   - Form the **normal line** $L_\perp$ passing through $P$ with direction vector $\vec{n}$:
     $$L_\perp: \vec{x}(t) = P + t\vec{n}, \quad t \in \mathbb{R}.$$
   - Find the parameter $t = t^*$ where $L_\perp$ intersects $\Pi$ by substituting $\vec{x}(t)$ into $\vec{n} \cdot \vec{x} = d$.
   - The orthogonal projection is $P' = P + t^*\vec{n}$.

2. **Reflection of a Point Across a Plane**:
   The **reflection** (or mirror image) of $P$ across the plane $\Pi$, denoted $P''$, is the point on the normal line $L_\perp$ on the opposite side of $\Pi$ at the exact same perpendicular distance from $\Pi$ as $P$.
   - Since moving from $P$ to the plane $\Pi$ requires the displacement vector $\overrightarrow{PP'} = t^*\vec{n}$, continuing an equal distance past the plane to the reflection $P''$ requires twice that displacement:
     $$P'' = P + 2\overrightarrow{PP'} = P + 2t^*\vec{n},$$
     or equivalently, using the fact that $P'$ is the midpoint of the segment $PP''$ ($P' = \frac{P + P''}{2}$):
     $$P'' = 2P' - P.$$

3. **Midpoint Formula in $\mathbb{R}^3$**:
   The midpoint $M$ of the line segment joining $A = (x_1, y_1, z_1)$ and $B = (x_2, y_2, z_2)$ is the average of their coordinates:
   $$M = \frac{A + B}{2} = \left(\frac{x_1 + x_2}{2},\; \frac{y_1 + y_2}{2},\; \frac{z_1 + z_2}{2}\right).$$

## Detailed Step-by-Step Solution

### Step 1: Set Up the Normal Line Through $P$

From the plane equation $\Pi: x + y + z = 3$, we read off the normal vector:
$$\vec{n} = (1, 1, 1).$$
The line $L_\perp$ passing through $P = (2, 1, 3)$ and perpendicular to the plane $\Pi$ has direction vector $\vec{n} = (1, 1, 1)$:
$$L_\perp: (x, y, z) = (2, 1, 3) + t(1, 1, 1), \quad t \in \mathbb{R}.$$
In component form:
$$\begin{cases} x = 2 + t, \\ y = 1 + t, \\ z = 3 + t, \end{cases} \quad t \in \mathbb{R}.$$

### Step 2: Find the Orthogonal Projection $P'$

The orthogonal projection $P'$ is the intersection point of the normal line $L_\perp$ with the plane $\Pi: x + y + z = 3$. Substituting $x = 2 + t$, $y = 1 + t$, and $z = 3 + t$ into the plane equation gives:
$$(2 + t) + (1 + t) + (3 + t) = 3.$$
Combining like terms and solving for $t$:
$$\begin{aligned} 6 + 3t &= 3 \\ 3t &= 3 - 6 \\ 3t &= -3 \\ t &= -1. \end{aligned}$$
Substituting $t^* = -1$ back into the normal line equation yields the orthogonal projection $P'$:
$$P' = (2 + (-1),\; 1 + (-1),\; 3 + (-1)) = (1, 0, 2).$$

### Step 3: Find the Reflection $P''$ of $P$ Across the Plane

To reach the orthogonal projection $P'$ on the plane from $P$, we traveled along the displacement vector:
$$\overrightarrow{PP'} = P' - P = (1 - 2,\; 0 - 1,\; 2 - 3) = (-1, -1, -1) \quad (\text{which corresponds to } t^* = -1).$$
To reach the reflection $P''$ across the plane, we travel twice this displacement from $P$ (corresponding to $t = 2t^* = -2$), or equivalently apply $P'' = 2P' - P$:
$$\begin{aligned} P'' &= 2P' - P \\ &= 2(1, 0, 2) - (2, 1, 3) \\ &= (2, 0, 4) - (2, 1, 3) \\ &= (2 - 2,\; 0 - 1,\; 4 - 3) \\ &= (0, -1, 1). \end{aligned}$$
Thus:
- **Orthogonal projection**: $P' = (1, 0, 2)$,
- **Reflection across the plane**: $P'' = (0, -1, 1)$.

## Verification and Consistency Checks

1. **Check That the Midpoint of $P$ and $P''$ Lies on the Plane**:
   Using the midpoint formula on $P = (2, 1, 3)$ and $P'' = (0, -1, 1)$:
   $$M = \frac{P + P''}{2} = \left(\frac{2 + 0}{2},\; \frac{1 + (-1)}{2},\; \frac{3 + 1}{2}\right) = \left(\frac{2}{2},\; \frac{0}{2},\; \frac{4}{2}\right) = (1, 0, 2).$$
   Notice first that $M = (1, 0, 2) = P'$, confirming that the orthogonal projection $P'$ is indeed the midpoint of $PP''$.
   Now we substitute the coordinates of $M = (1, 0, 2)$ into the plane equation $x + y + z = 3$:
   $$x_M + y_M + z_M = 1 + 0 + 2 = 3.$$
   Since $3 = 3$, the midpoint $M$ lies on the plane $\Pi$.

2. **Check Perpendicularity of the Segment $PP''$ to the Plane**:
   The vector joining $P = (2, 1, 3)$ and its reflection $P'' = (0, -1, 1)$ is:
   $$\overrightarrow{PP''} = P'' - P = (0 - 2,\; -1 - 1,\; 1 - 3) = (-2, -2, -2) = -2(1, 1, 1) = -2\vec{n}.$$
   Since $\overrightarrow{PP''}$ is a scalar multiple of the normal vector $\vec{n} = (1, 1, 1)$, the segment $PP''$ is strictly perpendicular to the plane $\Pi$.

3. **Check Equal Distances from $P$ and $P''$ to $P'$**:
   - $\|P - P'\| = \sqrt{(2-1)^2 + (1-0)^2 + (3-2)^2} = \sqrt{1 + 1 + 1} = \sqrt{3}$.
   - $\|P'' - P'\| = \sqrt{(0-1)^2 + (-1-0)^2 + (1-2)^2} = \sqrt{1 + 1 + 1} = \sqrt{3}$.
   Both $P$ and $P''$ are at the exact same distance $\sqrt{3}$ from the plane.
