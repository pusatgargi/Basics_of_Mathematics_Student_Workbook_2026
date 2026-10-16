# Problem 12: A Normal Vector to a Plane

## Problem Statement

Given $A=(1,0,2)$, $B=(2,1,0)$, and $C=(0,3,1)$. Construct two vectors lying in the plane, find a vector perpendicular to both, and check the perpendicularity using dot products.

## Theoretical Background and Concepts

1. **Plane Determined by Three Non-Collinear Points:** Three points $A, B, C$ in $\mathbb{R}^3$ that do not lie on a single line determine a unique plane $\Pi$. Any displacement vector between two points in the plane—such as $\overrightarrow{AB} = B - A$ and $\overrightarrow{AC} = C - A$—lies completely **inside** (parallel to) the plane $\Pi$.

2. **Normal Vector to a Plane:** A non-zero vector $n$ is called a **normal vector** to the plane $\Pi$ if it is perpendicular to every vector lying in $\Pi$. Because every vector in $\Pi$ is a linear combination of the two spanning vectors $\overrightarrow{AB}$ and $\overrightarrow{AC}$, a vector $n$ is perpendicular to the entire plane if and only if it is perpendicular to both $\overrightarrow{AB}$ and $\overrightarrow{AC}$:
   $$n \cdot \overrightarrow{AB} = 0 \qquad \text{and} \qquad n \cdot \overrightarrow{AC} = 0.$$

3. **Constructing the Normal via the Cross Product:** The cross product of two non-collinear vectors in the plane automatically produces a non-zero normal vector to the plane:
   $$n = \overrightarrow{AB} \times \overrightarrow{AC} = \left(u_2 v_3 - u_3 v_2,\; u_3 v_1 - u_1 v_3,\; u_1 v_2 - u_2 v_1\right),$$
   where $u = \overrightarrow{AB}$ and $v = \overrightarrow{AC}$. (Any non-zero scalar multiple $c n$ with $c \neq 0$ is also a valid normal vector to the same plane.)

## Detailed Step-by-Step Solution

We are given the three points in $\mathbb{R}^3$:
$$A = (1, 0, 2), \qquad B = (2, 1, 0), \qquad C = (0, 3, 1).$$

### Step 1: Construct Two Vectors Lying in the Plane

Taking $A = (1, 0, 2)$ as our common reference point, we construct the displacement vectors $\overrightarrow{AB} = B - A$ and $\overrightarrow{AC} = C - A$ using component-wise subtraction:

1. **Vector $\overrightarrow{AB}$:**
   $$\begin{aligned}
   \overrightarrow{AB} = B - A &= (2 - 1,\; 1 - 0,\; 0 - 2) \\
                               &= (1, 1, -2).
   \end{aligned}$$

2. **Vector $\overrightarrow{AC}$:**
   $$\begin{aligned}
   \overrightarrow{AC} = C - A &= (0 - 1,\; 3 - 0,\; 1 - 2) \\
                               &= (-1, 3, -1).
   \end{aligned}$$

Both $u = \overrightarrow{AB} = (1, 1, -2)$ and $v = \overrightarrow{AC} = (-1, 3, -1)$ lie in the plane determined by $A, B, C$.

### Step 2: Find a Vector Perpendicular to Both Using the Cross Product

To find a normal vector $n$ perpendicular to both $u = (1, 1, -2)$ and $v = (-1, 3, -1)$, we compute their cross product
$$n = \overrightarrow{AB} \times \overrightarrow{AC} = (u_2 v_3 - u_3 v_2,\; u_3 v_1 - u_1 v_3,\; u_1 v_2 - u_2 v_1):$$
- **First ($x$) component:**
  $$n_1 = u_2 v_3 - u_3 v_2 = (1)(-1) - (-2)(3) = -1 - (-6) = -1 + 6 = 5.$$
- **Second ($y$) component:**
  $$n_2 = u_3 v_1 - u_1 v_3 = (-2)(-1) - (1)(-1) = 2 - (-1) = 2 + 1 = 3.$$
- **Third ($z$) component:**
  $$n_3 = u_1 v_2 - u_2 v_1 = (1)(3) - (1)(-1) = 3 - (-1) = 3 + 1 = 4.$$

Therefore, a normal vector perpendicular to both $\overrightarrow{AB}$ and $\overrightarrow{AC}$ is:
$$n = (5, 3, 4).$$

### Step 3: Check Perpendicularity Using Dot Products

We verify that $n = (5, 3, 4)$ is orthogonal to both $\overrightarrow{AB} = (1, 1, -2)$ and $\overrightarrow{AC} = (-1, 3, -1)$ by computing their dot products:

1. **Dot product $n \cdot \overrightarrow{AB}$:**
   $$\begin{aligned}
   n \cdot \overrightarrow{AB} &= (5)(1) + (3)(1) + (4)(-2) \\
                               &= 5 + 3 - 8 \\
                               &= 0.
   \end{aligned}$$
   Since $n \cdot \overrightarrow{AB} = 0$, we have $n \perp \overrightarrow{AB}$.

2. **Dot product $n \cdot \overrightarrow{AC}$:**
   $$\begin{aligned}
   n \cdot \overrightarrow{AC} &= (5)(-1) + (3)(3) + (4)(-1) \\
                               &= -5 + 9 - 4 \\
                               &= 0.
   \end{aligned}$$
   Since $n \cdot \overrightarrow{AC} = 0$, we have $n \perp \overrightarrow{AC}$.

## Verification and Consistency Checks

1. **Perpendicularity to the Third Edge $\overrightarrow{BC}$:** Because the third edge of $\triangle ABC$ is $\overrightarrow{BC} = C - B = \overrightarrow{AC} - \overrightarrow{AB}$, it also lies in the plane and must be perpendicular to $n = (5, 3, 4)$. Let us compute $\overrightarrow{BC}$ directly from the coordinates of $B = (2, 1, 0)$ and $C = (0, 3, 1)$:
   $$\overrightarrow{BC} = (0 - 2,\; 3 - 1,\; 1 - 0) = (-2, 2, 1).$$
   Taking the dot product with $n = (5, 3, 4)$:
   $$n \cdot \overrightarrow{BC} = (5)(-2) + (3)(2) + (4)(1) = -10 + 6 + 4 = 0. \quad \checkmark$$

2. **Cartesian Plane Equation Check at All Three Vertices:** With normal vector $n = (5, 3, 4)$ and point $A = (1, 0, 2)$, the equation of the plane $n \cdot ((x, y, z) - A) = 0$ is
   $$5(x - 1) + 3(y - 0) + 4(z - 2) = 0 \iff 5x + 3y + 4z = 13.$$
   Checking that all three given points satisfy $5x + 3y + 4z = 13$:
   - At $A = (1, 0, 2)$: $5(1) + 3(0) + 4(2) = 5 + 0 + 8 = 13.$ $\checkmark$
   - At $B = (2, 1, 0)$: $5(2) + 3(1) + 4(0) = 10 + 3 + 0 = 13.$ $\checkmark$
   - At $C = (0, 3, 1)$: $5(0) + 3(3) + 4(1) = 0 + 9 + 4 = 13.$ $\checkmark$
