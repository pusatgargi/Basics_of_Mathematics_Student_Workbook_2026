# Problem 2: A Line in Space

## Problem Statement

Given
$$L:(x,y,z)=(2,-1,3)+t(1,2,-2).$$
State a point on the line and its direction vector, check whether $P=(4,3,-1)$ lies on $L$, and find the point corresponding to $t=-1$.

## Theoretical Background and Concepts

In three-dimensional space $\mathbb{R}^3$, a line cannot be described by a single linear equation (because a single linear equation $ax + by + cz = d$ in $\mathbb{R}^3$ describes a plane, not a line). Instead, the most natural and geometric way to represent a line in space is the **vector parametric form**:
$$L: (x, y, z) = (x_0, y_0, z_0) + t(v_x, v_y, v_z), \quad t \in \mathbb{R}.$$

1. **Interpretation as "Point + Direction"**:
   - The fixed tuple $P_0 = (x_0, y_0, z_0)$ represents a **reference point** (or base point) on the line, obtained when the scalar parameter is $t = 0$.
   - The non-zero vector $\vec{v} = (v_x, v_y, v_z)$ is the **direction vector** of the line. It specifies the orientation of the line in space.
   - As the real parameter $t$ varies over $(-\infty, \infty)$, the vector $t\vec{v}$ scales the direction vector forward ($t > 0$) or backward ($t < 0$) from $P_0$, sweeping out every point $(x, y, z)$ on the line $L$.

2. **Component Parametric Equations**: Expanding the vector equation component by component gives a system of three equations in terms of $t$:
   $$\begin{cases} x(t) = x_0 + t v_x, \\ y(t) = y_0 + t v_y, \\ z(t) = z_0 + t v_z, \end{cases} \quad t \in \mathbb{R}.$$

3. **Condition for a Point to Lie on a Line**: A given point $P = (x_P, y_P, z_P)$ lies on the line $L$ if and only if there exists a **single, consistent** real parameter $t \in \mathbb{R}$ that simultaneously satisfies all three coordinate equations:
   $$x_P = x_0 + t v_x, \qquad y_P = y_0 + t v_y, \qquad z_P = z_0 + t v_z.$$
   If solving for $t$ in each coordinate produces the exact same value of $t$, the point lies on $L$; if different coordinates yield different values of $t$, the point does not lie on $L$.

## Detailed Step-by-Step Solution

### Step 1: State a Point on the Line and Its Direction Vector

We compare the given equation of the line
$$L: (x, y, z) = (2, -1, 3) + t(1, 2, -2)$$
directly with the general parametric template $(x, y, z) = P_0 + t\vec{v}$:

- **A point on the line** (corresponding to $t = 0$) is:
  $$P_0 = (2, -1, 3).$$
- **The direction vector** of the line (the vector multiplied by the parameter $t$) is:
  $$\vec{v} = (1, 2, -2).$$

Writing the line in component parametric form gives:
$$\begin{cases} x = 2 + t, \\ y = -1 + 2t, \\ z = 3 - 2t, \end{cases} \quad t \in \mathbb{R}.$$

### Step 2: Check Whether $P = (4, 3, -1)$ Lies on $L$

To determine whether $P = (4, 3, -1)$ lies on $L$, we substitute $(x, y, z) = (4, 3, -1)$ into the component parametric equations and test whether a single parameter $t$ satisfies all three equations simultaneously:
$$\begin{cases} 4 = 2 + t, & \text{(Equation 1: } x\text{-coordinate)} \\ 3 = -1 + 2t, & \text{(Equation 2: } y\text{-coordinate)} \\ -1 = 3 - 2t. & \text{(Equation 3: } z\text{-coordinate)} \end{cases}$$

We solve each equation for $t$:
1. From the $x$-coordinate equation:
   $$4 = 2 + t \implies t = 4 - 2 = 2.$$
2. From the $y$-coordinate equation:
   $$3 = -1 + 2t \implies 2t = 3 + 1 = 4 \implies t = \frac{4}{2} = 2.$$
3. From the $z$-coordinate equation:
   $$-1 = 3 - 2t \implies 2t = 3 - (-1) = 4 \implies t = \frac{4}{2} = 2.$$

Because all three coordinate equations are satisfied by the **same** parameter value $t = 2$, we conclude that **yes, the point $P = (4, 3, -1)$ lies on the line $L$**.

### Step 3: Find the Point Corresponding to $t = -1$

To find the point $Q$ on the line $L$ corresponding to $t = -1$, we substitute $t = -1$ into the vector equation $(x, y, z) = (2, -1, 3) + t(1, 2, -2)$:
$$Q = (2, -1, 3) + (-1)(1, 2, -2).$$
Computing each coordinate step by step:
$$\begin{aligned} x(-1) &= 2 + (-1)(1) = 2 - 1 = 1, \\ y(-1) &= -1 + (-1)(2) = -1 - 2 = -3, \\ z(-1) &= 3 + (-1)(-2) = 3 + 2 = 5. \end{aligned}$$
Therefore, the point on $L$ corresponding to $t = -1$ is:
$$Q = (1, -3, 5).$$

## Verification and Consistency Checks

1. **Collinearity Check for $P = (4, 3, -1)$**:
   If $P$ lies on $L$, the displacement vector $\overrightarrow{P_0 P}$ from the base point $P_0 = (2, -1, 3)$ to $P = (4, 3, -1)$ must be a scalar multiple of the direction vector $\vec{v} = (1, 2, -2)$:
   $$\overrightarrow{P_0 P} = P - P_0 = (4 - 2, 3 - (-1), -1 - 3) = (2, 4, -4).$$
   Factoring out $2$ gives:
   $$\overrightarrow{P_0 P} = 2(1, 2, -2) = 2\vec{v},$$
   confirming that $P$ lies on $L$ at parameter $t = 2$.

2. **Collinearity Check for $Q = (1, -3, 5)$**:
   The displacement vector from $P_0 = (2, -1, 3)$ to $Q = (1, -3, 5)$ is:
   $$\overrightarrow{P_0 Q} = Q - P_0 = (1 - 2, -3 - (-1), 5 - 3) = (-1, -2, 2) = (-1)(1, 2, -2) = -\vec{v},$$
   which confirms that $Q = (1, -3, 5)$ is indeed the point reached by moving $-1$ unit of $\vec{v}$ from $P_0$.
