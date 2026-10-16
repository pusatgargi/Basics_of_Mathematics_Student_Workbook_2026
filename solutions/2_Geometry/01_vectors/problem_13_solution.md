# Problem 13: Do Four Points Lie in One Plane?

## Problem Statement

Given
$$A=(0,0,0),\qquad B=(1,2,0),\qquad C=(0,1,1),\qquad D=(2,5,1).$$

1. Construct $\overrightarrow{AB}$ and $\overrightarrow{AC}$.
2. Find $n=\overrightarrow{AB}\times\overrightarrow{AC}$.
3. Construct $\overrightarrow{AD}$ and check whether $\overrightarrow{AD}\cdot n=0$.
4. Based on this, decide whether $D$ lies in the plane determined by $A,B,C$, and justify the criterion.

## Theoretical Background and Concepts

1. **Coplanarity of Four Points:** Four points $A, B, C, D$ in $\mathbb{R}^3$ are **coplanar** (lie in a single common plane) if and only if the three displacement vectors originating from a common point—namely $\overrightarrow{AB}$, $\overrightarrow{AC}$, and $\overrightarrow{AD}$—lie in the same plane through the origin (i.e., are linearly dependent).

2. **Normal Vector Description of a Plane:** If $A, B, C$ are not collinear, then $n = \overrightarrow{AB} \times \overrightarrow{AC} \neq \mathbf{0}$ is a **normal vector** perpendicular to the plane $\Pi$ through $A, B, C$. Any point $P \in \mathbb{R}^3$ lies in the plane $\Pi$ if and only if the displacement vector $\overrightarrow{AP} = P - A$ is perpendicular to the normal vector $n$:
   $$P \in \Pi \iff \overrightarrow{AP} \cdot n = 0.$$

3. **Connection to the Scalar Triple Product (Parallelepiped Volume):** The quantity $\overrightarrow{AD} \cdot (\overrightarrow{AB} \times \overrightarrow{AC})$ is the **scalar triple product** of $\overrightarrow{AB}, \overrightarrow{AC}, \overrightarrow{AD}$. Its absolute value $|\overrightarrow{AD} \cdot n|$ equals the volume of the three-dimensional parallelepiped spanned by $\overrightarrow{AB}, \overrightarrow{AC}, \overrightarrow{AD}$. This volume collapses to zero if and only if the three vectors are flat—that is, coplanar.

## Detailed Step-by-Step Solution

We are given the four points in $\mathbb{R}^3$:
$$A = (0, 0, 0), \qquad B = (1, 2, 0), \qquad C = (0, 1, 1), \qquad D = (2, 5, 1).$$

### Part 1: Construct $\overrightarrow{AB}$ and $\overrightarrow{AC}$

Using the displacement vector formula $\overrightarrow{PQ} = Q - P$ from the origin $A = (0, 0, 0)$:
$$\begin{aligned}
\overrightarrow{AB} &= B - A = (1 - 0,\; 2 - 0,\; 0 - 0) = (1, 2, 0), \\
\overrightarrow{AC} &= C - A = (0 - 0,\; 1 - 0,\; 1 - 0) = (0, 1, 1).
\end{aligned}$$

### Part 2: Find $n = \overrightarrow{AB} \times \overrightarrow{AC}$

Applying the cross product formula
$$u \times v = (u_2 v_3 - u_3 v_2,\; u_3 v_1 - u_1 v_3,\; u_1 v_2 - u_2 v_1)$$
to $u = \overrightarrow{AB} = (1, 2, 0)$ and $v = \overrightarrow{AC} = (0, 1, 1)$:
- **First ($x$) component:**
  $$n_1 = (2)(1) - (0)(1) = 2 - 0 = 2.$$
- **Second ($y$) component:**
  $$n_2 = (0)(0) - (1)(1) = 0 - 1 = -1.$$
- **Third ($z$) component:**
  $$n_3 = (1)(1) - (2)(0) = 1 - 0 = 1.$$

Thus, the normal vector to the plane through $A, B, C$ is:
$$n = \overrightarrow{AB} \times \overrightarrow{AC} = (2, -1, 1).$$
Note that $n \neq (0, 0, 0)$, which confirms that $A, B, C$ are non-collinear and uniquely determine a plane.

### Part 3: Construct $\overrightarrow{AD}$ and Check Whether $\overrightarrow{AD} \cdot n = 0$

First, we construct the displacement vector $\overrightarrow{AD} = D - A$:
$$\overrightarrow{AD} = (2 - 0,\; 5 - 0,\; 1 - 0) = (2, 5, 1).$$

Next, we compute the dot product of $\overrightarrow{AD} = (2, 5, 1)$ and $n = (2, -1, 1)$:
$$\begin{aligned}
\overrightarrow{AD} \cdot n &= (2)(2) + (5)(-1) + (1)(1) \\
                            &= 4 - 5 + 1 \\
                            &= 0.
\end{aligned}$$
Thus, $\overrightarrow{AD} \cdot n = 0$ holds identically.

### Part 4: Decision and Justification of the Criterion

- **Decision:** **Yes**, the point $D = (2, 5, 1)$ **lies in the plane** determined by $A, B, C$ (the four points $A, B, C, D$ are coplanar).

- **Justification of the Criterion:**
  1. The points $A, B, C$ determine a unique plane $\Pi$ passing through $A$, spanned by the two non-collinear vectors $\overrightarrow{AB}$ and $\overrightarrow{AC}$.
  2. By construction of the cross product, $n = \overrightarrow{AB} \times \overrightarrow{AC} \neq \mathbf{0}$ is perpendicular (normal) to both $\overrightarrow{AB}$ and $\overrightarrow{AC}$, and therefore perpendicular to **every** vector lying in the plane $\Pi$.
  3. Conversely, in three-dimensional space $\mathbb{R}^3$, the set of all vectors starting at $A$ that are perpendicular to the normal vector $n$ forms the exact 2-dimensional plane $\Pi$.
  4. Therefore, a fourth point $D$ lies in the plane $\Pi$ if and only if the displacement vector $\overrightarrow{AD}$ lies in $\Pi$, which occurs if and only if $\overrightarrow{AD}$ is perpendicular to the plane's normal vector $n$—that is, $\overrightarrow{AD} \cdot n = 0$.

```
                n = AB x AC = (2, -1, 1)
                ^
                |  90 deg
                |                 * D = (2, 5, 1)
        +-------+-----------------/-------+
       /        |         AD    /        /
      /     C = (0,1,1)       /         /
     /        ^             /          /
    /        / AC         /           /
   /        A --------> B = (1, 2, 0)/
  +------------ AB -----------------+
        Plane Pi through A, B, C
```

## Verification and Consistency Checks

1. **Orthogonality Check of $n = (2, -1, 1)$ with $\overrightarrow{AB}$ and $\overrightarrow{AC}$:**
   $$n \cdot \overrightarrow{AB} = (2)(1) + (-1)(2) + (1)(0) = 2 - 2 + 0 = 0, \quad \checkmark$$
   $$n \cdot \overrightarrow{AC} = (2)(0) + (-1)(1) + (1)(1) = 0 - 1 + 1 = 0. \quad \checkmark$$

2. **Explicit Linear Combination Check ($\overrightarrow{AD} = \alpha\overrightarrow{AB} + \beta\overrightarrow{AC}$):** If $D$ truly lies in the plane through $A, B, C$, then $\overrightarrow{AD} = (2, 5, 1)$ must be an explicit linear combination of $\overrightarrow{AB} = (1, 2, 0)$ and $\overrightarrow{AC} = (0, 1, 1)$:
   $$\alpha(1, 2, 0) + \beta(0, 1, 1) = (\alpha,\; 2\alpha + \beta,\; \beta) = (2, 5, 1).$$
   - From the $x$-component: $\alpha = 2$.
   - From the $z$-component: $\beta = 1$.
   - Checking the $y$-component: $2\alpha + \beta = 2(2) + 1 = 4 + 1 = 5$, which matches the middle coordinate of $\overrightarrow{AD} = (2, 5, 1)$!
   Indeed:
   $$2\overrightarrow{AB} + 1\overrightarrow{AC} = 2(1, 2, 0) + (0, 1, 1) = (2, 4, 0) + (0, 1, 1) = (2, 5, 1) = \overrightarrow{AD}. \quad \checkmark$$
   This directly proves that $D$ lies in the plane determined by $A, B, C$.
