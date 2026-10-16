# Problem 4: Plane Through Three Points

## Problem Statement

Find the equation of the plane through
$$A=(1,0,0),\quad B=(0,1,0),\quad C=(0,0,1).$$
First construct two vectors lying in the plane, and then use the cross product. Check the resulting equation on all three points.

## Theoretical Background and Concepts

Three non-collinear points $A$, $B$, and $C$ in $\mathbb{R}^3$ uniquely determine a plane. To find the scalar equation of this plane, we need a point on the plane (any of $A$, $B$, or $C$) and a **normal vector** $\vec{n}$ perpendicular to the plane.

1. **Constructing Spanning Vectors in the Plane**:
   Using one point (say $A$) as an anchor, the displacement vectors to the other two points,
   $$\vec{u} = \overrightarrow{AB} = B - A \quad \text{and} \quad \vec{w} = \overrightarrow{AC} = C - A,$$
   both lie entirely within the plane. If $A$, $B$, and $C$ are not collinear, $\vec{u}$ and $\vec{w}$ are linearly independent (non-parallel) and span the plane's two-dimensional direction space.

2. **Finding the Normal Vector via the Cross Product**:
   For any two vectors $\vec{u} = (u_1, u_2, u_3)$ and $\vec{w} = (w_1, w_2, w_3)$ in $\mathbb{R}^3$, their **cross product** $\vec{n} = \vec{u} \times \vec{w}$ is defined by:
   $$\vec{u} \times \vec{w} = \begin{vmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ u_1 & u_2 & u_3 \\ w_1 & w_2 & w_3 \end{vmatrix} = \big(u_2 w_3 - u_3 w_2,\; u_3 w_1 - u_1 w_3,\; u_1 w_2 - u_2 w_1\big).$$
   By fundamental properties of the cross product:
   - $\vec{u} \times \vec{w}$ is orthogonal to both $\vec{u}$ and $\vec{w}$ (and therefore orthogonal to every vector in the plane spanned by $\vec{u}$ and $\vec{w}$).
   - $\vec{u} \times \vec{w} \neq \vec{0}$ if and only if $\vec{u}$ and $\vec{w}$ are not parallel (i.e., $A, B, C$ are non-collinear).
   Thus, $\vec{n} = \overrightarrow{AB} \times \overrightarrow{AC}$ serves directly as a normal vector to the plane.

3. **Equation of the Plane**:
   Once $\vec{n} = (a, b, c)$ is known, the equation of the plane using point $A = (x_A, y_A, z_A)$ is:
   $$a(x - x_A) + b(y - y_A) + c(z - z_A) = 0.$$

## Detailed Step-by-Step Solution

### Step 1: Construct Two Vectors Lying in the Plane

Using $A = (1, 0, 0)$ as the starting point, we construct the displacement vectors $\overrightarrow{AB}$ and $\overrightarrow{AC}$ to $B = (0, 1, 0)$ and $C = (0, 0, 1)$:
$$\vec{u} = \overrightarrow{AB} = B - A = (0 - 1,\; 1 - 0,\; 0 - 0) = (-1, 1, 0),$$
$$\vec{w} = \overrightarrow{AC} = C - A = (0 - 1,\; 0 - 0,\; 1 - 0) = (-1, 0, 1).$$
Both $\vec{u} = (-1, 1, 0)$ and $\vec{w} = (-1, 0, 1)$ lie in the desired plane.

### Step 2: Compute the Normal Vector Using the Cross Product

To obtain a normal vector $\vec{n}$ perpendicular to both $\vec{u}$ and $\vec{w}$, we calculate the cross product $\vec{n} = \vec{u} \times \vec{w}$:
$$\vec{n} = \overrightarrow{AB} \times \overrightarrow{AC} = \begin{vmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ -1 & 1 & 0 \\ -1 & 0 & 1 \end{vmatrix}.$$
Using the cofactor (or $2 \times 2$ minor) formula $\big(u_2 w_3 - u_3 w_2,\; u_3 w_1 - u_1 w_3,\; u_1 w_2 - u_2 w_1\big)$:
$$\begin{aligned} n_x &= (1)(1) - (0)(0) = 1 - 0 = 1, \\ n_y &= (0)(-1) - (-1)(1) = 0 - (-1) = 1, \\ n_z &= (-1)(0) - (1)(-1) = 0 - (-1) = 1. \end{aligned}$$
Thus, a normal vector to the plane is:
$$\vec{n} = (1, 1, 1).$$

### Step 3: Write the Equation of the Plane

Using the point-normal form $a(x - x_A) + b(y - y_A) + c(z - z_A) = 0$ with normal vector $\vec{n} = (1, 1, 1)$ and point $A = (1, 0, 0)$:
$$1(x - 1) + 1(y - 0) + 1(z - 0) = 0.$$
Simplifying this expression gives the general equation of the plane:
$$x + y + z - 1 = 0,$$
or equivalently:
$$x + y + z = 1.$$

*(Geometrically, this is the intercept form of the plane cutting the $x$-, $y$-, and $z$-axes at $1$ unit each.)*

## Verification and Consistency Checks

1. **Checking the Plane Equation $x + y + z = 1$ on All Three Points**:
   - **Point $A = (1, 0, 0)$**:
     $$x + y + z = 1 + 0 + 0 = 1 \quad \checkmark$$
   - **Point $B = (0, 1, 0)$**:
     $$x + y + z = 0 + 1 + 0 = 1 \quad \checkmark$$
   - **Point $C = (0, 0, 1)$**:
     $$x + y + z = 0 + 0 + 1 = 1 \quad \checkmark$$
   All three points satisfy the equation $x + y + z = 1$.

2. **Checking Orthogonality of $\vec{n}$ with the Plane Vectors**:
   - $\vec{n} \cdot \overrightarrow{AB} = (1, 1, 1) \cdot (-1, 1, 0) = (1)(-1) + (1)(1) + (1)(0) = -1 + 1 + 0 = 0 \quad \checkmark$
   - $\vec{n} \cdot \overrightarrow{AC} = (1, 1, 1) \cdot (-1, 0, 1) = (1)(-1) + (1)(0) + (1)(1) = -1 + 0 + 1 = 0 \quad \checkmark$
   This confirms that $\vec{n} = (1, 1, 1)$ is perpendicular to both spanning vectors in the plane.
