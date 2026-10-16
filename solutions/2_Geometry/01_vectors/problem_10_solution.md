# Problem 10: Triangle Area from Vectors

## Problem Statement

The points $A=(0,0,0)$, $B=(2,1,0)$, and $C=(1,3,2)$ form a triangle. Construct $\overrightarrow{AB}$ and $\overrightarrow{AC}$, compute the area of the parallelogram using the cross product, and then find the area of the triangle. Explain the factor $\frac12$.

## Theoretical Background and Concepts

1. **Edge Vectors of a Triangle:** Given three vertices $A, B, C$ in $\mathbb{R}^3$, two adjacent sides of $\triangle ABC$ meeting at vertex $A$ are represented by the displacement vectors
   $$\overrightarrow{AB} = B - A \qquad \text{and} \qquad \overrightarrow{AC} = C - A.$$

2. **Magnitude of the Cross Product as Parallelogram Area:** For any two vectors $u$ and $v$ in $\mathbb{R}^3$ forming an angle $\theta \in [0, \pi]$, the length of their cross product is
   $$\|u \times v\| = \|u\|\,\|v\|\sin\theta.$$
   In a parallelogram with adjacent sides $u$ and $v$, if we take $\|u\|$ as the base, then $h = \|v\|\sin\theta$ is the perpendicular altitude (height). Since the area of a parallelogram is $\text{base} \times \text{height}$, the length of the cross product equals the area of the parallelogram spanned by $u$ and $v$:
   $$\text{Area}_{\text{parallelogram}} = \|\overrightarrow{AB} \times \overrightarrow{AC}\|.$$

3. **Area of a Triangle in $\mathbb{R}^3$:** The area of the triangle $\triangle ABC$ with vertices $A, B, C$ is half the area of the parallelogram spanned by $\overrightarrow{AB}$ and $\overrightarrow{AC}$:
   $$\text{Area}_{\triangle ABC} = \frac{1}{2}\|\overrightarrow{AB} \times \overrightarrow{AC}\|.$$

## Detailed Step-by-Step Solution

We are given the three vertices:
$$A = (0, 0, 0), \qquad B = (2, 1, 0), \qquad C = (1, 3, 2).$$

### Step 1: Construct $\overrightarrow{AB}$ and $\overrightarrow{AC}$

Using the displacement vector formula $\overrightarrow{PQ} = Q - P$:
$$\begin{aligned}
\overrightarrow{AB} &= B - A = (2 - 0,\; 1 - 0,\; 0 - 0) = (2, 1, 0), \\
\overrightarrow{AC} &= C - A = (1 - 0,\; 3 - 0,\; 2 - 0) = (1, 3, 2).
\end{aligned}$$

### Step 2: Compute $\overrightarrow{AB} \times \overrightarrow{AC}$ and the Area of the Parallelogram

We first compute the cross product $u \times v$ for $u = \overrightarrow{AB} = (2, 1, 0)$ and $v = \overrightarrow{AC} = (1, 3, 2)$ using
$$u \times v = (u_2 v_3 - u_3 v_2,\; u_3 v_1 - u_1 v_3,\; u_1 v_2 - u_2 v_1):$$
- **First ($x$) component:**
  $$(1)(2) - (0)(3) = 2 - 0 = 2.$$
- **Second ($y$) component:**
  $$(0)(1) - (2)(2) = 0 - 4 = -4.$$
- **Third ($z$) component:**
  $$(2)(3) - (1)(1) = 6 - 1 = 5.$$

Thus:
$$\overrightarrow{AB} \times \overrightarrow{AC} = (2, -4, 5).$$

The area of the parallelogram spanned by $\overrightarrow{AB}$ and $\overrightarrow{AC}$ is the Euclidean norm of this cross product:
$$\begin{aligned}
\text{Area}_{\text{parallelogram}} = \|\overrightarrow{AB} \times \overrightarrow{AC}\| &= \sqrt{2^2 + (-4)^2 + 5^2} \\
&= \sqrt{4 + 16 + 25} \\
&= \sqrt{45} \\
&= \sqrt{9 \cdot 5} = 3\sqrt{5} \approx 6.7082.
\end{aligned}$$

### Step 3: Find the Area of the Triangle $\triangle ABC$

Dividing the area of the parallelogram by $2$:
$$\begin{aligned}
\text{Area}_{\triangle ABC} &= \frac{1}{2}\|\overrightarrow{AB} \times \overrightarrow{AC}\| \\
                            &= \frac{\sqrt{45}}{2} = \frac{3\sqrt{5}}{2} \approx 3.3541.
\end{aligned}$$

### Step 4: Explain the Factor $\frac{1}{2}$

Geometrically, the two vectors $\overrightarrow{AB}$ and $\overrightarrow{AC}$ starting at $A$ define a full parallelogram $ABDC$ (where $D = A + \overrightarrow{AB} + \overrightarrow{AC} = (3, 4, 2)$). The third side $BC$ of our triangle $\triangle ABC$ is a **diagonal** of this parallelogram.

A diagonal of any parallelogram divides it into **two congruent triangles** ($\triangle ABC$ and $\triangle DCB$) by the Side-Side-Side (SSS) congruence criterion:
- $|AB| = |CD|$ (opposite sides of a parallelogram),
- $|AC| = |BD|$ (opposite sides of a parallelogram),
- $|BC| = |CB|$ (shared diagonal).

Because the two congruent triangles have identical areas and together tile the entire parallelogram without overlap, the area of $\triangle ABC$ is exactly **one-half** ($\frac{1}{2}$) the area of the parallelogram. Equivalently, in elementary geometry, a parallelogram has area $\text{base} \times \text{height} = \|\overrightarrow{AB}\| h$, whereas a triangle with the same base and height has area $\frac{1}{2} \times \text{base} \times \text{height} = \frac{1}{2}\|\overrightarrow{AB}\| h$.

```
               C = (1,3,2) ------------- D = A + AB + AC = (3,4,2)
                  /\                    /
                 /  \    Triangle      /
          AC    /    \     DCB        /
               /      \              /
              /  ABC   \  diagonal  /
             /          \   BC     /
            A ---------- B = (2,1,0)
                  AB
```

## Verification and Consistency Checks

1. **Orthogonality Check of $\overrightarrow{AB} \times \overrightarrow{AC} = (2, -4, 5)$:** Before trusting the norm of the cross product, we check that $(2, -4, 5)$ is orthogonal to both $\overrightarrow{AB} = (2, 1, 0)$ and $\overrightarrow{AC} = (1, 3, 2)$:
   $$(2, -4, 5) \cdot (2, 1, 0) = (2)(2) + (-4)(1) + (5)(0) = 4 - 4 + 0 = 0, \quad \checkmark$$
   $$(2, -4, 5) \cdot (1, 3, 2) = (2)(1) + (-4)(3) + (5)(2) = 2 - 12 + 10 = 0. \quad \checkmark$$

2. **Independent Area Calculation via Dot Product (Lagrange's Identity):** We can compute the triangle area without using the cross product components at all, via $\text{Area}_{\triangle ABC} = \frac{1}{2}\sqrt{\|\overrightarrow{AB}\|^2\|\overrightarrow{AC}\|^2 - (\overrightarrow{AB}\cdot\overrightarrow{AC})^2}$:
   - $\|\overrightarrow{AB}\|^2 = 2^2 + 1^2 + 0^2 = 5,$
   - $\|\overrightarrow{AC}\|^2 = 1^2 + 3^2 + 2^2 = 1 + 9 + 4 = 14,$
   - $\overrightarrow{AB} \cdot \overrightarrow{AC} = (2)(1) + (1)(3) + (0)(2) = 2 + 3 + 0 = 5.$
   Substituting these into the formula gives:
   $$\text{Area}_{\triangle ABC} = \frac{1}{2}\sqrt{(5)(14) - 5^2} = \frac{1}{2}\sqrt{70 - 25} = \frac{1}{2}\sqrt{45} = \frac{3\sqrt{5}}{2}. \quad \checkmark$$

3. **Vertex-Invariance Check (Expanding from Vertex $B$):** Using $\overrightarrow{BA} = (-2, -1, 0)$ and $\overrightarrow{BC} = C - B = (-1, 2, 2)$:
   $$\overrightarrow{BA} \times \overrightarrow{BC} = ((-1)(2) - (0)(2),\; (0)(-1) - (-2)(2),\; (-2)(2) - (-1)(-1)) = (-2, 4, -5),$$
   which gives the exact same triangle area $\frac{1}{2}\sqrt{(-2)^2 + 4^2 + (-5)^2} = \frac{\sqrt{45}}{2} = \frac{3\sqrt{5}}{2}$. $\checkmark$
