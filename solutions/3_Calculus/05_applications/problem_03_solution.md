# Problem 3: A Box Made from Cardboard

## Problem Statement

From a $30\text{ cm}\times40\text{ cm}$ sheet, squares of side length $x$ are cut from the corners and the edges are folded up to form an open box.

Write the volume as a function of $x$, determine the physically meaningful domain, and find the value of $x$ for which the volume is greatest.

## Theoretical Background and Concepts

When constructing a three-dimensional geometric solid from a flat sheet, the optimization model is built directly from spatial relationships:

1. **Geometric Parameterization**:
   Removing a square of side $x$ from each of the four corners of a rectangular sheet of dimensions $W \times L$ shortens both the width and the length of the base by $2x$ (since a segment of length $x$ is removed from each end of every edge). Folding the four side flaps upward by $90^\circ$ creates an open rectangular prism (box) of:
   - height: $h(x) = x$,
   - base width: $w(x) = W - 2x$,
   - base length: $l(x) = L - 2x$.
   The volume of the rectangular prism is the product of its three orthogonal dimensions:
   $$
   V(x) = h(x) \cdot w(x) \cdot l(x) = x(W - 2x)(L - 2x).
   $$

2. **Physical Domain Constraints**:
   Every physical dimension of the folded box must be strictly positive:
   $$
   x > 0, \qquad W - 2x > 0, \qquad L - 2x > 0.
   $$
   Hence $0 < x < \frac{1}{2}\min(W, L)$.

3. **Optimization on an Open Interval**:
   For a smooth polynomial $V(x)$ on $(0, a)$ satisfying $\lim_{x \to 0^+} V(x) = 0$, $\lim_{x \to a^-} V(x) = 0$, and $V(x) > 0$ on $(0, a)$, the Extreme Value Theorem on $[0, a]$ guarantees that the global maximum occurs at an interior stationary point where $V'(x) = 0$.

## Detailed Step-by-Step Solution

### Step 1: Volume as a Function of $x$

Let $x$ (in $\text{cm}$) be the side length of each square cut from the four corners of the $30\text{ cm} \times 40\text{ cm}$ cardboard sheet.
After cutting the corners and folding up the flaps:
- Height of the box: $h = x\text{ cm}$.
- Width of the rectangular base: $w = (30 - 2x)\text{ cm}$.
- Length of the rectangular base: $l = (40 - 2x)\text{ cm}$.

The volume $V(x)$ of the open box (in $\text{cm}^3$) is the product of base area and height:
$$
V(x) = x(30 - 2x)(40 - 2x).
$$
Expanding the product into standard polynomial form:
$$
\begin{aligned}
V(x) &= x\left(1200 - 60x - 80x + 4x^2\right) \\
&= x\left(4x^2 - 140x + 1200\right) \\
&= 4x^3 - 140x^2 + 1200x \quad [\text{cm}^3].
\end{aligned}
$$

---

### Step 2: Physically Meaningful Domain

For the folded box to have positive height, positive base width, and positive base length, $x$ must satisfy the system of strict inequalities:
$$
\begin{cases}
x > 0 & \text{(positive cut and box height)}, \\
30 - 2x > 0 \iff x < 15 & \text{(positive base width)}, \\
40 - 2x > 0 \iff x < 20 & \text{(positive base length)}.
\end{cases}
$$
Taking the intersection of all three conditions yields the physically meaningful domain:
$$
D = (0, 15) \quad \text{(in cm)}.
$$
*(At the boundary points $x = 0$ and $x = 15$, the box degenerates and $V(0) = V(15) = 0$.)*

---

### Step 3: Finding the Optimal Cut Size $x$

We differentiate $V(x) = 4x^3 - 140x^2 + 1200x$ with respect to $x$:
$$
\begin{aligned}
V'(x) &= \frac{d}{dx}\left(4x^3 - 140x^2 + 1200x\right) \\
&= 12x^2 - 280x + 1200 \\
&= 4\left(3x^2 - 70x + 300\right).
\end{aligned}
$$
To find the stationary points, we solve $V'(x) = 0$:
$$
3x^2 - 70x + 300 = 0.
$$
Computing the discriminant $\Delta = b^2 - 4ac$:
$$
\Delta = (-70)^2 - 4(3)(300) = 4900 - 3600 = 1300 = 100 \times 13 \implies \sqrt{\Delta} = 10\sqrt{13}.
$$
The roots of the quadratic equation are:
$$
x = \frac{70 \pm 10\sqrt{13}}{2 \cdot 3} = \frac{35 \pm 5\sqrt{13}}{3}.
$$
Let us check which root belongs to the physical domain $D = (0, 15)$. Since $3.60555 < \sqrt{13} < 3.60556$:
1. First root:
   $$
   x_1 = \frac{35 - 5\sqrt{13}}{3} \approx \frac{35 - 18.02776}{3} \approx 5.6574\text{ cm} \in (0, 15).
   $$
2. Second root:
   $$
   x_2 = \frac{35 + 5\sqrt{13}}{3} \approx \frac{35 + 18.02776}{3} \approx 17.6759\text{ cm} \notin (0, 15).
   $$
   *(For $x_2 > 15$, the factor $30 - 2x$ would be negative, which is physically impossible.)*

Thus, the unique critical point inside the domain $D = (0, 15)$ is:
$$
x^* = \frac{35 - 5\sqrt{13}}{3}\text{ cm} \approx 5.66\text{ cm}.
$$

---

### Step 4: Justification of Maximum and Maximum Volume Calculation

**First Derivative Test**:
Since $V'(x) = 12(x - x_1)(x - x_2)$ is an upward-opening parabola with roots $x_1 \approx 5.66$ and $x_2 \approx 17.68$:
- For $x \in (0, x_1)$, both $(x - x_1) < 0$ and $(x - x_2) < 0$, so $V'(x) > 0$ ($V$ is strictly increasing).
- For $x \in (x_1, 15)$, $(x - x_1) > 0$ and $(x - x_2) < 0$, so $V'(x) < 0$ ($V$ is strictly decreasing).
Hence, $x^* = x_1 = \frac{35 - 5\sqrt{13}}{3}$ is the unique global maximum of $V(x)$ on $(0, 15)$.

**Second Derivative Test**:
$$
V''(x) = 24x - 280.
$$
Evaluating at $x^* = \frac{35 - 5\sqrt{13}}{3}$:
$$
V''\left(\frac{35 - 5\sqrt{13}}{3}\right) = 8\left(35 - 5\sqrt{13}\right) - 280 = 280 - 40\sqrt{13} - 280 = -40\sqrt{13} \approx -144.22 < 0,
$$
which confirms a strict local (and global) maximum.

**Corresponding Dimensions and Maximum Volume**:
- Optimal cut / height: $x^* = \frac{35 - 5\sqrt{13}}{3} \approx 5.6574\text{ cm}$.
- Base width: $30 - 2x^* = \frac{20 + 10\sqrt{13}}{3} \approx 18.6852\text{ cm}$.
- Base length: $40 - 2x^* = \frac{50 + 10\sqrt{13}}{3} \approx 28.6852\text{ cm}$.
- Maximum volume:
  $$
  V_{\max} = V\left(\frac{35 - 5\sqrt{13}}{3}\right) = \frac{1000\left(35 + 13\sqrt{13}\right)}{27}\text{ cm}^3 \approx 3032.30\text{ cm}^3.
  $$

## Verification and Consistency Checks

1. **Dimensional Consistency**:
   Each factor $x$, $(30-2x)$, and $(40-2x)$ has units of $\text{cm}$, so $V(x)$ has units of $\text{cm}^3$, and $V'(x)$ has units of $\text{cm}^2$.

2. **Boundary Checks**:
   - As $x \to 0^+$, $V(0) = 0(30)(40) = 0\text{ cm}^3$ (a flat sheet with zero height).
   - As $x \to 15^-$, $V(15) = 15(0)(10) = 0\text{ cm}^3$ (the narrower $30\text{ cm}$ side is folded completely in half with zero base width).

3. **Numerical Comparison Near $x^* \approx 5.6574\text{ cm}$**:
   - $x = 5.0\text{ cm}$: $V(5) = 5(20)(30) = 3000.00\text{ cm}^3 < V_{\max}$.
   - $x = 5.5\text{ cm}$: $V(5.5) = 5.5(19)(29) = 3030.50\text{ cm}^3 < V_{\max}$.
   - $x = x^* \approx 5.6574\text{ cm}$: $V(x^*) \approx 3032.30\text{ cm}^3$.
   - $x = 6.0\text{ cm}$: $V(6) = 6(18)(28) = 3024.00\text{ cm}^3 < V_{\max}$.
   These evaluations confirm the peak at $x^* = \frac{35 - 5\sqrt{13}}{3}\text{ cm}$.
