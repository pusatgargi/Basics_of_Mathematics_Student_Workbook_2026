# Problem 3: Vector Normalization

## Problem Statement

For $v=(3,4)$ find a unit vector $e$ with the same direction and orientation. Check that $\|e\|=1$, reconstruct $v$ in the form $v=\|v\|e$, and explain what changes during normalization and what remains unchanged.

## Theoretical Background and Concepts

1. **Euclidean Norm in $\mathbb{R}^2$:** The length (magnitude or norm) of a two-dimensional vector $v = (v_1, v_2)$ is given by the Pythagorean theorem:
   $$\|v\| = \sqrt{v_1^2 + v_2^2}.$$

2. **Unit Vector:** A vector $e$ is called a **unit vector** if its length is equal to $1$, i.e., $\|e\| = 1$. Unit vectors are used throughout mathematics and physics to specify pure direction without scaling.

3. **Vector Normalization:** Given any non-zero vector $v \neq \mathbf{0}$, **normalizing** $v$ means dividing $v$ by its own length $\|v\|$ (equivalently, multiplying $v$ by the positive scalar $\frac{1}{\|v\|}$):
   $$e = \frac{v}{\|v\|} = \frac{1}{\|v\|}(v_1, v_2) = \left(\frac{v_1}{\|v\|},\; \frac{v_2}{\|v\|}\right).$$
   Because $\frac{1}{\|v\|} > 0$, the resulting unit vector $e$ has the **exact same direction and orientation** as $v$, and its components are the direction cosines $(\cos\alpha, \sin\alpha)$ of $v$ relative to the positive $x$-axis.

4. **Magnitude-Direction Decomposition:** Every non-zero vector $v$ can be factored into the product of its scalar magnitude $\|v\|$ and its unit direction vector $e$:
   $$v = \|v\|e.$$

## Detailed Step-by-Step Solution

We are given the vector
$$v = (3, 4).$$

### Step 1: Compute the Length $\|v\|$

Using the norm formula $\|v\| = \sqrt{v_1^2 + v_2^2}$:
$$\begin{aligned}
\|v\| &= \sqrt{3^2 + 4^2} \\
      &= \sqrt{9 + 16} \\
      &= \sqrt{25} \\
      &= 5.
\end{aligned}$$

### Step 2: Find the Unit Vector $e$

To find the unit vector $e$ with the same direction and orientation as $v$, we multiply $v$ by the positive scalar $\frac{1}{\|v\|} = \frac{1}{5}$:
$$\begin{aligned}
e = \frac{1}{\|v\|}v &= \frac{1}{5}(3, 4) \\
                     &= \left(\frac{3}{5},\; \frac{4}{5}\right) \\
                     &= (0.6,\; 0.8).
\end{aligned}$$

### Step 3: Check that $\|e\| = 1$

We substitute the components of $e = \left(\frac{3}{5}, \frac{4}{5}\right)$ into the length formula $\|e\| = \sqrt{e_1^2 + e_2^2}$:
$$\begin{aligned}
\|e\| &= \sqrt{\left(\frac{3}{5}\right)^2 + \left(\frac{4}{5}\right)^2} \\
      &= \sqrt{\frac{9}{25} + \frac{16}{25}} \\
      &= \sqrt{\frac{9 + 16}{25}} \\
      &= \sqrt{\frac{25}{25}} \\
      &= \sqrt{1} = 1.
\end{aligned}$$
This confirms that $e$ is indeed a unit vector.

### Step 4: Reconstruct $v$ in the Form $v = \|v\|e$

Multiplying the unit vector $e = \left(\frac{3}{5}, \frac{4}{5}\right)$ by the scalar length $\|v\| = 5$:
$$\begin{aligned}
\|v\|e &= 5\left(\frac{3}{5},\; \frac{4}{5}\right) \\
       &= \left(5 \cdot \frac{3}{5},\; 5 \cdot \frac{4}{5}\right) \\
       &= (3, 4) = v.
\end{aligned}$$
This decomposition separates $v$ into its scalar length ($5$) and its pure directional carrier $e = \left(\frac{3}{5}, \frac{4}{5}\right)$.

### Step 5: Explain What Changes During Normalization and What Remains Unchanged

- **What changes:**
  - **The magnitude (length)** of the vector changes from $\|v\| = 5$ to $\|e\| = 1$ (it is scaled by the factor $\frac{1}{5}$).
  - **The individual numerical components** are scaled proportionally from $(3, 4)$ to $\left(\frac{3}{5}, \frac{4}{5}\right)$.

- **What remains unchanged:**
  - **The direction (line of action / slope):** Both vectors lie along the exact same line $y = \frac{4}{3}x$ through the origin, because the ratio of their components is preserved: $\frac{e_2}{e_1} = \frac{4/5}{3/5} = \frac{4}{3} = \frac{v_2}{v_1}$.
  - **The orientation (sense):** Because we multiplied $v$ by a strictly positive scalar $\frac{1}{\|v\|} = \frac{1}{5} > 0$, $e$ points in the **same sense** (into the first quadrant at angle $\theta = \arctan(4/3) \approx 53.13^\circ$ from the positive $x$-axis) rather than the opposite sense.

```
      y ^
      4 | . . . . . . * v = (3, 4), ||v|| = 5
        |           / .
      3 |         /   .
        |       /     .
      2 |     /       .
        |   /         .
      1 | * e = (3/5, 4/5), ||e|| = 1
        |/            .
      0 +----+----+---+----> x
        0    1    2   3
```

## Verification and Consistency Checks

1. **Zero-Angle Verification via Dot Product:** Two non-zero vectors have the exact same direction and orientation if and only if the cosine of the angle between them is $1$:
   $$\cos\theta = \frac{v \cdot e}{\|v\|\,\|e\|} = \frac{3\left(\frac{3}{5}\right) + 4\left(\frac{4}{5}\right)}{5 \cdot 1} = \frac{\frac{9}{5} + \frac{16}{5}}{5} = \frac{\frac{25}{5}}{5} = \frac{5}{5} = 1 \implies \theta = 0^\circ. \quad \checkmark$$

2. **Collinearity (2D Cross-Product / Determinant) Check:** Two vectors in $\mathbb{R}^2$ are parallel if and only if $v_1 e_2 - v_2 e_1 = 0$:
   $$v_1 e_2 - v_2 e_1 = 3\left(\frac{4}{5}\right) - 4\left(\frac{3}{5}\right) = \frac{12}{5} - \frac{12}{5} = 0. \quad \checkmark$$
