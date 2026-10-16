# Problem 13: Closest Point on a Plane

## Problem Statement

Find the point on the plane $x+2y+2z=4$ closest to $P=(3,0,0)$. Give the distance and check that the segment joining the two points is perpendicular to the plane.

## Theoretical Background and Concepts

Let $\Pi: ax + by + cz = d$ be a plane in $\mathbb{R}^3$ with normal vector $\vec{n} = (a, b, c)$, and let $P = (x_0, y_0, z_0)$ be a given point in space.

1. **Characterization of the Closest Point via Orthogonal Projection**:
   For any point $X \in \Pi$, let $Q \in \Pi$ be the **orthogonal projection** of $P$ onto $\Pi$ (so that $\overrightarrow{PQ}$ is perpendicular to $\Pi$, while $\overrightarrow{QX}$ lies inside $\Pi$). Because $\overrightarrow{PQ} \perp \overrightarrow{QX}$, the triangle $\triangle PQX$ is a right triangle with hypotenuse $PX$. By the Pythagorean theorem:
   $$\|P - X\|^2 = \|P - Q\|^2 + \|Q - X\|^2 \ge \|P - Q\|^2,$$
   with equality if and only if $X = Q$. Therefore, the point $Q$ on $\Pi$ closest to $P$ is uniquely the **orthogonal projection** of $P$ onto $\Pi$, obtained by intersecting $\Pi$ with the normal line $L_\perp$ through $P$:
   $$L_\perp: \vec{x}(t) = P + t\vec{n}, \quad t \in \mathbb{R}.$$

2. **Distance Between $P$ and $\Pi$**:
   The shortest distance from $P$ to $\Pi$ equals the Euclidean distance $\|Q - P\|$ between $P$ and its closest point $Q$, which can also be computed directly via the point-to-plane distance formula:
   $$d(P, \Pi) = \|Q - P\| = \frac{|ax_0 + by_0 + cz_0 - d|}{\sqrt{a^2 + b^2 + c^2}}.$$

## Detailed Step-by-Step Solution

### Step 1: Construct the Normal Line Through $P = (3, 0, 0)$

From the equation of the plane $\Pi: x + 2y + 2z = 4$, we read off the normal vector:
$$\vec{n} = (1, 2, 2).$$
The line $L_\perp$ passing through $P = (3, 0, 0)$ in the direction of the normal vector $\vec{n} = (1, 2, 2)$ has the parametric equation:
$$L_\perp: (x, y, z) = (3, 0, 0) + t(1, 2, 2), \quad t \in \mathbb{R},$$
or in coordinate form:
$$\begin{cases} x = 3 + t, \\ y = 2t, \\ z = 2t, \end{cases} \quad t \in \mathbb{R}.$$

### Step 2: Find the Closest Point $Q$ on the Plane

The closest point $Q$ is the intersection of $L_\perp$ with the plane $x + 2y + 2z = 4$. Substituting $x = 3 + t$, $y = 2t$, and $z = 2t$ into the plane equation:
$$(3 + t) + 2(2t) + 2(2t) = 4.$$
Simplifying and solving for $t$:
$$\begin{aligned} 3 + t + 4t + 4t &= 4 \\ 3 + 9t &= 4 \\ 9t &= 4 - 3 \\ 9t &= 1 \\ t &= \frac{1}{9}. \end{aligned}$$
Substituting $t = \frac{1}{9}$ back into the parametric equations of $L_\perp$ gives the coordinates of the closest point $Q$:
$$\begin{aligned} x_Q &= 3 + \frac{1}{9} = \frac{27}{9} + \frac{1}{9} = \frac{28}{9}, \\ y_Q &= 2\left(\frac{1}{9}\right) = \frac{2}{9}, \\ z_Q &= 2\left(\frac{1}{9}\right) = \frac{2}{9}. \end{aligned}$$
Thus, the point on the plane closest to $P = (3, 0, 0)$ is:
$$Q = \left(\frac{28}{9},\; \frac{2}{9},\; \frac{2}{9}\right).$$

### Step 3: Compute the Distance from $P$ to the Plane

We compute the distance $d(P, \Pi)$ using the Euclidean length of the segment $PQ$:
$$\overrightarrow{PQ} = Q - P = \left(\frac{28}{9} - 3,\; \frac{2}{9} - 0,\; \frac{2}{9} - 0\right) = \left(\frac{1}{9},\; \frac{2}{9},\; \frac{2}{9}\right) = \frac{1}{9}(1, 2, 2).$$
Taking the Euclidean norm of $\overrightarrow{PQ}$:
$$d(P, \Pi) = \|\overrightarrow{PQ}\| = \sqrt{\left(\frac{1}{9}\right)^2 + \left(\frac{2}{9}\right)^2 + \left(\frac{2}{9}\right)^2} = \frac{1}{9}\sqrt{1^2 + 2^2 + 2^2} = \frac{1}{9}\sqrt{1 + 4 + 4} = \frac{\sqrt{9}}{9} = \frac{3}{9} = \frac{1}{3}.$$
Therefore, the distance from $P$ to the plane is:
$$d(P, \Pi) = \frac{1}{3}.$$

## Verification and Consistency Checks

1. **Check That $Q = \left(\frac{28}{9}, \frac{2}{9}, \frac{2}{9}\right)$ Lies on the Plane $x + 2y + 2z = 4$**:
   $$x_Q + 2y_Q + 2z_Q = \frac{28}{9} + 2\left(\frac{2}{9}\right) + 2\left(\frac{2}{9}\right) = \frac{28 + 4 + 4}{9} = \frac{36}{9} = 4 \quad \checkmark$$

2. **Check That the Segment $PQ$ Is Perpendicular to the Plane**:
   - **Proportionality to the Normal Vector**:
     $$\overrightarrow{PQ} = \left(\frac{1}{9},\; \frac{2}{9},\; \frac{2}{9}\right) = \frac{1}{9}(1, 2, 2) = \frac{1}{9}\vec{n}.$$
     Because $\overrightarrow{PQ}$ is a non-zero scalar multiple of the plane's normal vector $\vec{n} = (1, 2, 2)$, the segment $PQ$ is perpendicular to the plane.
   - **Direct Orthogonality Check with Vectors in the Plane**:
     Consider any two additional points on the plane $x + 2y + 2z = 4$, such as $A = (4, 0, 0)$ and $B = (0, 2, 0)$. The displacement vectors from $Q$ to $A$ and $B$ lie in the plane:
     $$\overrightarrow{QA} = A - Q = \left(\frac{8}{9},\; -\frac{2}{9},\; -\frac{2}{9}\right), \qquad \overrightarrow{QB} = B - Q = \left(-\frac{28}{9},\; \frac{16}{9},\; -\frac{2}{9}\right).$$
     Taking their dot products with $\overrightarrow{PQ} = \left(\frac{1}{9}, \frac{2}{9}, \frac{2}{9}\right)$:
     $$\overrightarrow{PQ} \cdot \overrightarrow{QA} = \frac{8 - 4 - 4}{81} = 0, \qquad \overrightarrow{PQ} \cdot \overrightarrow{QB} = \frac{-28 + 32 - 4}{81} = 0 \quad \checkmark$$

3. **Independent Distance Check Using the Point-to-Plane Formula**:
   Applying $d(P, \Pi) = \frac{|ax_0 + by_0 + cz_0 - d|}{\sqrt{a^2 + b^2 + c^2}}$ to $P = (3, 0, 0)$ and $x + 2y + 2z - 4 = 0$:
   $$d(P, \Pi) = \frac{|1(3) + 2(0) + 2(0) - 4|}{\sqrt{1^2 + 2^2 + 2^2}} = \frac{|3 - 4|}{\sqrt{9}} = \frac{|-1|}{3} = \frac{1}{3} \quad \checkmark$$
