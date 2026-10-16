# Problem 11: Two Similar Surfaces

## Problem Statement

Compare
$$x^2+y^2-z^2=1$$
and
$$x^2+y^2-z^2=-1.$$
For several values $z=c$, check whether the cross-section exists and what its radius is. Based on this, describe qualitatively the difference between the surfaces and make sketches.

## Theoretical Background and Concepts

When a second-degree surface in $\mathbb{R}^3$ has two squared terms of one sign and one squared term of the opposite sign, it belongs to the family of **hyperboloids**. Depending on the sign of the constant on the right-hand side, two distinct topological shapes arise:

1. **Hyperboloid of One Sheet:**
   $$\frac{x^2}{a^2} + \frac{y^2}{b^2} - \frac{z^2}{c_0^2} = 1.$$
   When $a = b = c_0 = 1$, this simplifies to $x^2 + y^2 - z^2 = 1$, or $x^2 + y^2 = 1 + z^2$.
   - Because $1 + z^2 \ge 1 > 0$ for **all** $z \in \mathbb{R}$, every horizontal plane $z = c$ intersects the surface in a circle (or ellipse) of non-zero radius.
   - Consequently, the surface is a single **connected** tubular ("hourglass" or cooling-tower) sheet with a narrowest "waist" ("throat circle") at $z = 0$.

2. **Hyperboloid of Two Sheets:**
   $$\frac{x^2}{a^2} + \frac{y^2}{b^2} - \frac{z^2}{c_0^2} = -1 \quad \Longleftrightarrow \quad \frac{z^2}{c_0^2} - \frac{x^2}{a^2} - \frac{y^2}{b^2} = 1.$$
   When $a = b = c_0 = 1$, this simplifies to $x^2 + y^2 - z^2 = -1$, or $x^2 + y^2 = z^2 - 1$.
   - Because $x^2 + y^2 \ge 0$, real points exist **only** when $z^2 - 1 \ge 0 \iff |z| \ge 1$.
   - For $-1 < z < 1$, no horizontal cross-section exists. The surface splits into **two disconnected bowl-like sheets**: an upper sheet for $z \ge 1$ and a lower sheet for $z \le -1$.

Both surfaces share the same **asymptotic cone** $x^2 + y^2 - z^2 = 0$ (i.e., $x^2 + y^2 = z^2$), which separates the one-sheeted hyperboloid outside the cone from the two-sheeted hyperboloid inside the upper and lower nappes of the cone.

## Detailed Step-by-Step Solution

---

### Part 1: Analysis of Horizontal Cross-Sections $z = c$ for Both Surfaces

#### Surface A: $x^2 + y^2 - z^2 = 1$
Substituting $z = c$ into $x^2 + y^2 - z^2 = 1$ gives the equation of the horizontal cross-section in the plane $z = c$:
$$x^2 + y^2 = 1 + c^2.$$
Since $c^2 \ge 0$ for every real number $c \in \mathbb{R}$, we always have $1 + c^2 \ge 1 > 0$. Therefore:
- **Existence:** The cross-section **exists for every $c \in \mathbb{R}$**.
- **Shape and Radius:** It is a **circle** centered at $(0, 0, c)$ on the $z$-axis with radius:
  $$R_1(c) = \sqrt{1 + c^2}.$$

Let us evaluate $R_1(c)$ for several concrete values of $z = c$:
- For $c = 0$: $x^2 + y^2 = 1 + 0^2 = 1 \implies$ Circle of radius $R_1(0) = 1$ (the smallest radius, called the **throat** or **waist** circle).
- For $c = \pm \frac{1}{2}$: $x^2 + y^2 = 1 + \frac{1}{4} = \frac{5}{4} \implies$ Circle of radius $R_1(\pm \frac{1}{2}) = \frac{\sqrt{5}}{2} \approx 1.118$.
- For $c = \pm 1$: $x^2 + y^2 = 1 + 1^2 = 2 \implies$ Circle of radius $R_1(\pm 1) = \sqrt{2} \approx 1.414$.
- For $c = \pm 2$: $x^2 + y^2 = 1 + 2^2 = 5 \implies$ Circle of radius $R_1(\pm 2) = \sqrt{5} \approx 2.236$.
- For $c = \pm 3$: $x^2 + y^2 = 1 + 3^2 = 10 \implies$ Circle of radius $R_1(\pm 3) = \sqrt{10} \approx 3.162$.

---

#### Surface B: $x^2 + y^2 - z^2 = -1$
Substituting $z = c$ into $x^2 + y^2 - z^2 = -1$ gives the equation of the horizontal cross-section in the plane $z = c$:
$$x^2 + y^2 = c^2 - 1.$$
Because the left-hand side $x^2 + y^2$ is a sum of squares of real numbers, it is always non-negative ($x^2 + y^2 \ge 0$). Thus, a real cross-section exists if and only if $c^2 - 1 \ge 0 \iff c^2 \ge 1 \iff |c| \ge 1$:
- **For $|c| < 1$ (i.e., $-1 < c < 1$):** $c^2 - 1 < 0$, so **no real cross-section exists** (empty set $\varnothing$).
- **For $c = \pm 1$:** $x^2 + y^2 = (\pm 1)^2 - 1 = 0 \implies x = 0, y = 0$. The cross-section degenerates to a **single point** (radius $R_2(\pm 1) = 0$) at the two vertices $(0, 0, 1)$ and $(0, 0, -1)$.
- **For $|c| > 1$ (i.e., $c > 1$ or $c < -1$):** $c^2 - 1 > 0$, so the cross-section is a **circle** centered at $(0, 0, c)$ with radius:
  $$R_2(c) = \sqrt{c^2 - 1}.$$

Let us evaluate $R_2(c)$ for the same test values of $z = c$:
- For $c = 0$: $x^2 + y^2 = -1 < 0 \implies$ **Does not exist** ($\varnothing$).
- For $c = \pm \frac{1}{2}$: $x^2 + y^2 = -\frac{3}{4} < 0 \implies$ **Does not exist** ($\varnothing$).
- For $c = \pm 1$: $x^2 + y^2 = 0 \implies$ **Single point** $(0, 0, \pm 1)$ of radius $R_2(\pm 1) = 0$.
- For $c = \pm 2$: $x^2 + y^2 = 2^2 - 1 = 3 \implies$ Circle of radius $R_2(\pm 2) = \sqrt{3} \approx 1.732$.
- For $c = \pm 3$: $x^2 + y^2 = 3^2 - 1 = 8 \implies$ Circle of radius $R_2(\pm 3) = \sqrt{8} = 2\sqrt{2} \approx 2.828$.

---

### Summary Table of Cross-Sections for $z = c$

| Plane Height $z = c$ | Surface 1: $x^2 + y^2 - z^2 = 1$ ($x^2+y^2 = 1+c^2$) | Radius $R_1(c) = \sqrt{1+c^2}$ | Surface 2: $x^2 + y^2 - z^2 = -1$ ($x^2+y^2 = c^2-1$) | Radius $R_2(c) = \sqrt{c^2-1}$ |
| :--- | :--- | :--- | :--- | :--- |
| $c = 0$ | Circle $x^2 + y^2 = 1$ | $1$ | Empty set $\varnothing$ ($x^2+y^2 = -1$) | — (does not exist) |
| $c = \pm \frac{1}{2}$ | Circle $x^2 + y^2 = \frac{5}{4}$ | $\frac{\sqrt{5}}{2} \approx 1.118$ | Empty set $\varnothing$ ($x^2+y^2 = -\frac{3}{4}$) | — (does not exist) |
| $c = \pm 1$ | Circle $x^2 + y^2 = 2$ | $\sqrt{2} \approx 1.414$ | Single point $(0, 0, \pm 1)$ | $0$ (degenerate circle) |
| $c = \pm 2$ | Circle $x^2 + y^2 = 5$ | $\sqrt{5} \approx 2.236$ | Circle $x^2 + y^2 = 3$ | $\sqrt{3} \approx 1.732$ |
| $c = \pm 3$ | Circle $x^2 + y^2 = 10$ | $\sqrt{10} \approx 3.162$ | Circle $x^2 + y^2 = 8$ | $2\sqrt{2} \approx 2.828$ |

---

### Part 2: Qualitative Comparison of the Two Surfaces

1. **Connectedness (One Sheet vs. Two Sheets):**
   - **Surface 1 ($x^2 + y^2 - z^2 = 1$, Hyperboloid of One Sheet):** Because circular cross-sections exist for every $z \in (-\infty, \infty)$ with a minimum positive radius $R_1(0) = 1$, the surface forms **one continuous, connected piece** shaped like an hourglass or power-plant cooling tower. It narrows to a waist of radius $1$ in the plane $z = 0$ and flares outward as $|z| \to \infty$.
   - **Surface 2 ($x^2 + y^2 - z^2 = -1$, Hyperboloid of Two Sheets):** Because no points exist in the horizontal slab $-1 < z < 1$, the surface is broken into **two separate, disconnected bowls (sheets)**: an upper bowl for $z \ge 1$ with vertex at $(0, 0, 1)$ opening upward, and a lower bowl for $z \le -1$ with vertex at $(0, 0, -1)$ opening downward.

2. **Vertical Cross-Sections ($x = 0$ or $y = 0$):**
   - Setting $y = 0$ in Surface 1 gives $x^2 - z^2 = 1$, a hyperbola opening left and right along the $x$-axis with vertices $(\pm 1, 0, 0)$. Rotating this hyperbola around the $z$-axis sweeps out the single hourglass tube.
   - Setting $y = 0$ in Surface 2 gives $z^2 - x^2 = 1$, a conjugate hyperbola opening up and down along the $z$-axis with vertices $(0, 0, \pm 1)$. Rotating these upper and lower branches around the $z$-axis sweeps out the two separate bowls.

3. **Behavior for Large $|c|$:**
   For both surfaces, as $|c| \to \infty$, both $R_1(c) = \sqrt{c^2 + 1} \approx |c|$ and $R_2(c) = \sqrt{c^2 - 1} \approx |c|$ approach the radius $|c|$ of the **asymptotic cone** $x^2 + y^2 = z^2$, with $R_2(c) < |c| < R_1(c)$.

---

### Part 3: Sketches of Both Surfaces

```text
   Surface 1: x^2 + y^2 - z^2 = 1              Surface 2: x^2 + y^2 - z^2 = -1
     (Hyperboloid of One Sheet)                  (Hyperboloid of Two Sheets)

                 z                                           z
                 ^                                           ^
         . - ~ ~ | ~ ~ - .                           . - ~ ~ | ~ ~ - .
       (         |         )                       (         |         )
        \  ' - . | . - '  /                         \  ' - . | . - '  /
          \      |      /                             \      |      /
           \     |     /                               ' . _ * _ . '   z = +1 (vertex)
            ) . -|- . (                                      |
  ---------(-1---+---1-)---------> x,y         --------------+--------------> x,y
            ) ' -|- ' (                          (Empty gap for -1 < z < 1)
           /     |     \                               . - ~ * ~ - .   z = -1 (vertex)
          /      |      \                             /      |      \
        /  . - ~ | ~ - .  \                         /  . - ~ | ~ - .  \
       (         |         )                       (         |         )
         ' - . _ | _ . - '                           ' - . _ | _ . - '
```

## Verification and Consistency Checks

1. **Direct Point Verification on Surface 1 ($x^2 + y^2 - z^2 = 1$):**
   - Waist point $(1, 0, 0)$ at $z = 0$: $1^2 + 0^2 - 0^2 = 1$. $\checkmark$
   - Point $(\sqrt{5}, 0, 2)$ at $z = 2$: $(\sqrt{5})^2 + 0^2 - 2^2 = 5 - 4 = 1$. $\checkmark$
   - Point $(1, 2, 2)$ at $z = 2$ (since $1^2 + 2^2 = 5 = R_1(2)^2$): $1^2 + 2^2 - 2^2 = 1 + 4 - 4 = 1$. $\checkmark$

2. **Direct Point Verification on Surface 2 ($x^2 + y^2 - z^2 = -1$):**
   - Upper and lower vertices $(0, 0, \pm 1)$: $0^2 + 0^2 - (\pm 1)^2 = -1$. $\checkmark$
   - Point $(\sqrt{3}, 0, 2)$ at $z = 2$: $(\sqrt{3})^2 + 0^2 - 2^2 = 3 - 4 = -1$. $\checkmark$
   - Check the difference of squared radii at any height $|c| \ge 1$:
     $$R_1(c)^2 - R_2(c)^2 = (1 + c^2) - (c^2 - 1) = 2,$$
     which is constant for all $|c| \ge 1$ ($5 - 3 = 2$ at $c=2$; $10 - 8 = 2$ at $c=3$).
