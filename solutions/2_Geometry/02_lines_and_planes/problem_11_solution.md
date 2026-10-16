# Problem 11: Plane Containing a Line and a Point

## Problem Statement

Find the equation of the plane containing
$$(x,y,z)=(1,0,2)+t(1,1,-1)$$
and the point $P=(0,2,1)$. Check that both the entire line and the point lie in the plane you obtain.

## Theoretical Background and Concepts

A unique plane $\Pi$ in $\mathbb{R}^3$ is determined by a line $L: \vec{x}(t) = A + t\vec{v}$ and an external point $P \notin L$. To construct the scalar equation of $\Pi$, we need a point on the plane and a **normal vector** $\vec{n}$ perpendicular to the plane.

1. **Constructing Two Linearly Independent Directions in the Plane**:
   - First, because the entire line $L$ lies inside the plane $\Pi$, the line's direction vector $\vec{v}$ automatically lies in $\Pi$.
   - Second, because both the base point $A$ of the line (at $t = 0$) and the given point $P$ lie in the plane $\Pi$, the displacement vector connecting them,
     $$\vec{u} = \overrightarrow{AP} = P - A,$$
     also lies entirely in $\Pi$.
   - Since $P \notin L$, the vectors $\vec{v}$ and $\vec{u} = \overrightarrow{AP}$ are non-parallel (linearly independent) and together span the two-dimensional direction space of the plane $\Pi$.

2. **Finding the Normal Vector via the Cross Product**:
   A normal vector $\vec{n}$ to $\Pi$ must be orthogonal to every vector in $\Pi$, and in particular to both $\vec{v}$ and $\vec{u} = \overrightarrow{AP}$. Therefore, we compute their cross product:
   $$\vec{n} = \vec{v} \times \overrightarrow{AP}.$$

3. **Writing the Plane Equation**:
   With $\vec{n} = (a, b, c)$ and either $A$ or $P$ as reference point, the point-normal equation is:
   $$a(x - x_A) + b(y - y_A) + c(z - z_A) = 0.$$

## Detailed Step-by-Step Solution

### Step 1: Identify Two Independent Vectors in the Plane

From the parametric equation of the line
$$L: (x, y, z) = (1, 0, 2) + t(1, 1, -1),$$
we obtain:
- A point on the line (and therefore on the plane) at $t = 0$:
  $$A = (1, 0, 2).$$
- A first direction vector lying in the plane:
  $$\vec{v} = (1, 1, -1).$$

Next, using the point $A = (1, 0, 2)$ and the given external point $P = (0, 2, 1)$, we construct a second vector $\vec{u} = \overrightarrow{AP}$ lying in the plane:
$$\vec{u} = \overrightarrow{AP} = P - A = (0 - 1,\; 2 - 0,\; 1 - 2) = (-1, 2, -1).$$

### Step 2: Compute the Normal Vector Using the Cross Product

We take the cross product of $\vec{v} = (1, 1, -1)$ and $\vec{u} = (-1, 2, -1)$ to find a normal vector $\vec{n}$ to the plane:
$$\vec{n} = \vec{v} \times \vec{u} = \begin{vmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ 1 & 1 & -1 \\ -1 & 2 & -1 \end{vmatrix}.$$
Expanding the $2 \times 2$ minors component by component:
$$\begin{aligned} n_x &= (1)(-1) - (-1)(2) = -1 - (-2) = -1 + 2 = 1, \\ n_y &= (-1)(-1) - (1)(-1) = 1 - (-1) = 1 + 1 = 2, \\ n_z &= (1)(2) - (1)(-1) = 2 - (-1) = 2 + 1 = 3. \end{aligned}$$
Thus, a normal vector to the plane is:
$$\vec{n} = (1, 2, 3).$$
*(Since $\vec{n} = (1, 2, 3) \neq (0, 0, 0)$, this also confirms that $P$ does not lie on $L$ and that the plane is uniquely determined.)*

### Step 3: Write the Equation of the Plane

Using the point-normal formula $a(x - x_0) + b(y - y_0) + c(z - z_0) = 0$ with normal vector $\vec{n} = (1, 2, 3)$ and the point $A = (1, 0, 2)$:
$$1(x - 1) + 2(y - 0) + 3(z - 2) = 0.$$
Expanding and combining the constant terms:
$$\begin{aligned} x - 1 + 2y + 3z - 6 &= 0 \\ x + 2y + 3z - 7 &= 0, \end{aligned}$$
or equivalently:
$$x + 2y + 3z = 7.$$

## Verification and Consistency Checks

1. **Check That the Point $P = (0, 2, 1)$ Lies in the Plane**:
   Substituting $x = 0$, $y = 2$, and $z = 1$ into the left-hand side of $x + 2y + 3z = 7$:
   $$\text{LHS} = 0 + 2(2) + 3(1) = 0 + 4 + 3 = 7 = \text{RHS}.$$
   Thus, the point $P = (0, 2, 1)$ lies in the plane.

2. **Check That the Entire Line Lies in the Plane**:
   An arbitrary point on the line $L: (x, y, z) = (1, 0, 2) + t(1, 1, -1)$ has coordinates:
   $$x(t) = 1 + t, \qquad y(t) = t, \qquad z(t) = 2 - t, \quad t \in \mathbb{R}.$$
   Substituting these parametric coordinates into the left-hand side of $x + 2y + 3z = 7$ gives:
   $$\begin{aligned} x(t) + 2y(t) + 3z(t) &= (1 + t) + 2(t) + 3(2 - t) \\ &= 1 + t + 2t + 6 - 3t \\ &= (1 + 6) + (1 + 2 - 3)t \\ &= 7 + 0t \\ &= 7. \end{aligned}$$
   Because the parameter $t$ cancels out completely ($0t = 0$) and the equality $7 = 7$ holds for **every** $t \in \mathbb{R}$, the **entire line $L$** lies in the plane $x + 2y + 3z = 7$.

3. **Check Orthogonality of $\vec{n}$ with $\vec{v}$ and $\overrightarrow{AP}$**:
   - $\vec{n} \cdot \vec{v} = (1)(1) + (2)(1) + (3)(-1) = 1 + 2 - 3 = 0 \quad \checkmark$
   - $\vec{n} \cdot \overrightarrow{AP} = (1)(-1) + (2)(2) + (3)(-1) = -1 + 4 - 3 = 0 \quad \checkmark$
