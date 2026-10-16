# Problem 2: Distance as the Length of a Vector

## Problem Statement

The points are $A=(1,2,3)$ and $B=(4,-2,6)$.

1. Construct $\overrightarrow{AB}$.
2. Compute its length.
3. Compute the distance between the points using the coordinate formula.
4. Explain why both calculations give the same result.

## Theoretical Background and Concepts

1. **Points vs. Displacement Vectors:** A point $A = (x_A, y_A, z_A)$ in $\mathbb{R}^3$ specifies a fixed location in space (which can also be identified with its position vector $\overrightarrow{OA}$ from the origin $O = (0,0,0)$). Given two points $A = (x_A, y_A, z_A)$ and $B = (x_B, y_B, z_B)$, the **directed displacement vector** $\overrightarrow{AB}$ from the initial point $A$ to the terminal point $B$ is obtained by subtracting the coordinates of the initial point $A$ from the coordinates of the terminal point $B$:
   $$\overrightarrow{AB} = B - A = (x_B - x_A,\; y_B - y_A,\; z_B - z_A).$$

2. **Length (Euclidean Norm) of a Vector:** By applying the Pythagorean theorem twice in three-dimensional space, the length (or magnitude/norm) of a vector $v = (v_1, v_2, v_3)$ is the square root of the sum of the squares of its components:
   $$\|v\| = \sqrt{v_1^2 + v_2^2 + v_3^2}.$$

3. **Euclidean Distance Between Two Points:** The straight-line distance $d(A, B)$ between two points $A = (x_A, y_A, z_A)$ and $B = (x_B, y_B, z_B)$ in $\mathbb{R}^3$ is given by the coordinate distance formula:
   $$d(A, B) = \sqrt{(x_B - x_A)^2 + (y_B - y_A)^2 + (z_B - z_A)^2}.$$

## Detailed Step-by-Step Solution

We are given the points
$$A = (1, 2, 3) \qquad \text{and} \qquad B = (4, -2, 6).$$

### Part 1: Construct $\overrightarrow{AB}$

To find the displacement vector $\overrightarrow{AB}$ starting at $A$ and ending at $B$, we subtract the coordinates of $A$ from the corresponding coordinates of $B$:
$$\overrightarrow{AB} = (x_B - x_A,\; y_B - y_A,\; z_B - z_A).$$
Substituting $A = (1, 2, 3)$ and $B = (4, -2, 6)$ gives:
$$\begin{aligned}
\overrightarrow{AB} &= (4 - 1,\; -2 - 2,\; 6 - 3) \\
                    &= (3, -4, 3).
\end{aligned}$$
This means that to move from point $A$ to point $B$, one moves $+3$ units along the $x$-axis, $-4$ units along the $y$-axis, and $+3$ units along the $z$-axis.

### Part 2: Compute the Length of $\overrightarrow{AB}$

The length (Euclidean norm) of a vector $v = (v_1, v_2, v_3)$ is given by
$$\|v\| = \sqrt{v_1^2 + v_2^2 + v_3^2}.$$
Substituting the components of $\overrightarrow{AB} = (3, -4, 3)$:
$$\begin{aligned}
\|\overrightarrow{AB}\| &= \sqrt{3^2 + (-4)^2 + 3^2} \\
                        &= \sqrt{9 + 16 + 9} \\
                        &= \sqrt{34} \approx 5.8310.
\end{aligned}$$

### Part 3: Compute the Distance Between the Points Using the Coordinate Formula

The coordinate distance formula between $A = (x_A, y_A, z_A)$ and $B = (x_B, y_B, z_B)$ is:
$$d(A, B) = \sqrt{(x_B - x_A)^2 + (y_B - y_A)^2 + (z_B - z_A)^2}.$$
Substituting the coordinates of $A = (1, 2, 3)$ and $B = (4, -2, 6)$ directly:
$$\begin{aligned}
d(A, B) &= \sqrt{(4 - 1)^2 + (-2 - 2)^2 + (6 - 3)^2} \\
        &= \sqrt{3^2 + (-4)^2 + 3^2} \\
        &= \sqrt{9 + 16 + 9} \\
        &= \sqrt{34} \approx 5.8310.
\end{aligned}$$

### Part 4: Explain Why Both Calculations Give the Same Result

Both calculations produce the exact same value $\sqrt{34}$ for both algebraic and geometric reasons:

- **Algebraic Explanation:** The coordinate differences $(x_B - x_A)$, $(y_B - y_A)$, and $(z_B - z_A)$ that appear inside the square root of the point-distance formula are **by definition** the three components $(v_1, v_2, v_3)$ of the displacement vector $\overrightarrow{AB} = B - A$. In Parts 1 and 2, we first computed those differences to form $\overrightarrow{AB} = (3, -4, 3)$ and then took the square root of the sum of their squares; in Part 3, we performed the exact same subtractions and squaring inside a single formula:
  $$d(A, B) = \sqrt{(x_B - x_A)^2 + (y_B - y_A)^2 + (z_B - z_A)^2} = \|\overrightarrow{AB}\|.$$

- **Geometric Explanation:** The vector $\overrightarrow{AB}$ is the directed line segment (arrow) whose tail sits at point $A$ and whose tip sits at point $B$. The **length** of the arrow connecting $A$ to $B$ is literally the straight-line **distance** between its endpoints $A$ and $B$ (the space diagonal of a rectangular box of dimensions $|\Delta x| = 3$, $|\Delta y| = 4$, and $|\Delta z| = 3$).

```
              B = (4, -2, 6)
              ^
             / |
  ||AB|| =  /  |  dz = +3
  sqrt(34) /   |
          /    +-------
         A = (1, 2, 3)  \  dy = -4
          \              \
           +--------------+
               dx = +3
```

## Verification and Consistency Checks

1. **Endpoint Reconstruction Check ($A + \overrightarrow{AB} = B$):** Starting at point $A$ and adding the displacement vector $\overrightarrow{AB}$ must land exactly at point $B$:
   $$A + \overrightarrow{AB} = (1 + 3,\; 2 + (-4),\; 3 + 3) = (4, -2, 6) = B. \quad \checkmark$$

2. **Symmetry of Distance ($\|\overrightarrow{BA}\| = \|\overrightarrow{AB}\|$):** The distance from $B$ to $A$ must equal the distance from $A$ to $B$. Constructing the opposite vector $\overrightarrow{BA} = A - B$:
   $$\overrightarrow{BA} = (1 - 4,\; 2 - (-2),\; 3 - 6) = (-3, 4, -3).$$
   Computing its length gives:
   $$\|\overrightarrow{BA}\| = \sqrt{(-3)^2 + 4^2 + (-3)^2} = \sqrt{9 + 16 + 9} = \sqrt{34} = \|\overrightarrow{AB}\|. \quad \checkmark$$
   Squaring eliminates the signs of the components, ensuring $d(A, B) = d(B, A)$.
