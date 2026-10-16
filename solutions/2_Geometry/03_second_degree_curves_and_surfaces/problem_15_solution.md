# Problem 15: Recognition and Sketch Without a Given Name

## Problem Statement

Consider the two equations:

$$4x^2+9y^2-8x+36y+4=0,$$

$$4x^2+y^2=z^2.$$

For the first equation, reduce it to canonical form, recognize the curve, give its most important features, and make a sketch.

For the second equation, do not begin by using a ready-made name for the surface. First describe the cross-sections $z=c$ and the cross-sections by the planes $x=0$ and $y=0$, paying attention to the different scales along the axes. Only then identify the surface and make a sketch.

## Theoretical Background and Concepts

This final synthesis problem combines the two foundational methods of the entire exercise set:

1. **Reducing a General 2D Second-Degree Equation to Canonical Form via Completing the Square:**
   Given $Ax^2 + By^2 + Cx + Dy + E = 0$ with $A > 0, B > 0$, we group the $x$-terms and $y$-terms, factor out $A$ and $B$, and complete the square inside each group using $u^2 + bu = (u + b/2)^2 - (b/2)^2$. Normalizing the constant on the right-hand side to $1$ yields the canonical form of a shifted ellipse:
   $$\frac{(x - x_0)^2}{a^2} + \frac{(y - y_0)^2}{b^2} = 1,$$
   from which we read off the center $(x_0, y_0)$, horizontal semiaxis $a$, vertical semiaxis $b$, and vertices $(x_0 \pm a, y_0)$ and $(x_0, y_0 \pm b)$.

2. **Reconstructing a 3D Surface from Its Cross-Sections (Traces) with Anisotropic Scaling:**
   When a surface equation has different positive coefficients in front of $x^2$ and $y^2$ (such as $4x^2 + y^2 = z^2$), the surface is no longer rotationally symmetric around the $Oz$-axis, because $x$ and $y$ are scaled differently. By slicing the surface with horizontal planes $z = c$ and vertical coordinate planes $x = 0$ and $y = 0$, we determine how the horizontal cross-sections scale with $c$ and how the vertical cross-sections differ in slope along the $xz$- and $yz$-planes, enabling us to identify the 3D geometry from first principles.

## Detailed Step-by-Step Solution

---

### Part 1: First Equation — $4x^2 + 9y^2 - 8x + 36y + 4 = 0$

#### Step 1: Group Terms and Factor Out Leading Coefficients
Start with the given equation in $\mathbb{R}^2$:
$$4x^2 + 9y^2 - 8x + 36y + 4 = 0.$$
Group the $x$-terms and $y$-terms together, and move the constant $+4$ to the right-hand side:
$$(4x^2 - 8x) + (9y^2 + 36y) = -4.$$
Factor $4$ out of the $x$-group and $9$ out of the $y$-group:
$$4(x^2 - 2x) + 9(y^2 + 4y) = -4.$$

#### Step 2: Complete the Square for $x$ and $y$
1. **For $x^2 - 2x$:** Half of $-2$ is $-1$, and $(-1)^2 = 1$:
   $$x^2 - 2x = (x^2 - 2x + 1) - 1 = (x - 1)^2 - 1.$$
   Multiplying by $4$:
   $$4(x^2 - 2x) = 4\big((x - 1)^2 - 1\big) = 4(x - 1)^2 - 4.$$

2. **For $y^2 + 4y$:** Half of $+4$ is $+2$, and $2^2 = 4$:
   $$y^2 + 4y = (y^2 + 4y + 4) - 4 = (y + 2)^2 - 4.$$
   Multiplying by $9$:
   $$9(y^2 + 4y) = 9\big((y + 2)^2 - 4\big) = 9(y + 2)^2 - 36.$$

#### Step 3: Normalize to Canonical Form
Substitute both completed squares back into the equation:
$$\big(4(x - 1)^2 - 4\big) + \big(9(y + 2)^2 - 36\big) = -4.$$
Combine the constants on the left-hand side ($-4 - 36 = -40$):
$$4(x - 1)^2 + 9(y + 2)^2 - 40 = -4.$$
Add $40$ to both sides:
$$4(x - 1)^2 + 9(y + 2)^2 = 36.$$
Divide both sides by $36$ so that the right-hand side equals $1$:
$$\frac{4(x - 1)^2}{36} + \frac{9(y + 2)^2}{36} = \frac{36}{36}$$
$$\frac{(x - 1)^2}{9} + \frac{(y + 2)^2}{4} = 1.$$
This is the **canonical form** of the curve.

#### Step 4: Recognize the Curve and Identify Its Most Important Features
Comparing $\frac{(x - 1)^2}{3^2} + \frac{(y - (-2))^2}{2^2} = 1$ with $\frac{(x - x_0)^2}{a^2} + \frac{(y - y_0)^2}{b^2} = 1$:
- **Type of Curve:** **Shifted Ellipse** (horizontally elongated since $a = 3 > b = 2$).
- **Center:** $S = (x_0, y_0) = (1, -2)$.
- **Semiaxis Lengths:**
  - Horizontal semiaxis (semi-major axis): $a = \sqrt{9} = 3$ (major axis length $2a = 6$, along the horizontal line $y = -2$).
  - Vertical semiaxis (semi-minor axis): $b = \sqrt{4} = 2$ (minor axis length $2b = 4$, along the vertical line $x = 1$).
- **Vertices (Endpoints of the Axes):**
  - Left and right major vertices $(x_0 \pm a, y_0)$:
    $$V_1 = (1 - 3, -2) = (-2, -2) \quad \text{and} \quad V_2 = (1 + 3, -2) = (4, -2).$$
  - Bottom and top minor vertices (co-vertices) $(x_0, y_0 \pm b)$:
    $$B_1 = (1, -2 - 2) = (1, -4) \quad \text{and} \quad B_2 = (1, -2 + 2) = (1, 0).$$
    *(Notice that $B_2(1, 0)$ lies directly on the $x$-axis, which means the top of the ellipse is **tangent to the $x$-axis** at $(1, 0)$!)*
- **$y$-Intercepts (set $x = 0$):**
  $$\frac{(0 - 1)^2}{9} + \frac{(y + 2)^2}{4} = 1 \implies \frac{(y + 2)^2}{4} = \frac{8}{9} \implies y = -2 \pm \frac{4\sqrt{2}}{3} \approx -0.114 \text{ and } -3.886.$$
- **Foci:** Since $c = \sqrt{a^2 - b^2} = \sqrt{9 - 4} = \sqrt{5}$, the foci are at $(1 - \sqrt{5}, -2)$ and $(1 + \sqrt{5}, -2)$.

#### Step 5: Coordinate Sketch of the Shifted Ellipse
```text
                    y
                    ^
                    |   B2(1,0)
  -----+------------+---*------------+-----> x
      -2            |0  :1           4
       :      . - ~ ~ ~ * ~ ~ - .    :
       :  . '       |   :        ' . :
  V1(-2,-2)         |   :          V2(4,-2)
       * - - - - - -+ - * - - - - - -*   y = -2
         ' .        | (1,-2)     . '
             ' - . _|_ _*_ . - '
                    |   B1(1,-4)
                   -4
```

---

### Part 2: Second Equation — $4x^2 + y^2 = z^2$

Following the instructions, we **do not** start with a ready-made name for the surface. Instead, we systematically examine its horizontal and vertical cross-sections first.

#### Step 1: Describe the Horizontal Cross-Sections $z = c$
Substitute $z = c$ (where $c \in \mathbb{R}$ is a constant) into $4x^2 + y^2 = z^2$:
$$4x^2 + y^2 = c^2.$$

We analyze two cases depending on whether $c = 0$ or $c \neq 0$:
1. **For $c = 0$ (in the plane $z = 0$):**
   $$4x^2 + y^2 = 0.$$
   Since $4x^2 \ge 0$ and $y^2 \ge 0$ for all real $x, y$, their sum is zero if and only if $x = 0$ and $y = 0$.
   - Thus, the cross-section at $z = 0$ is a **single point**: the origin $(0, 0, 0)$.

2. **For $c \neq 0$ (in any plane $z = c$ above or below $z = 0$):**
   Since $c^2 > 0$, we can divide both sides of $4x^2 + y^2 = c^2$ by $c^2$ to obtain the canonical 2D form:
   $$\frac{4x^2}{c^2} + \frac{y^2}{c^2} = 1 \quad \Longleftrightarrow \quad \frac{x^2}{(c/2)^2} + \frac{y^2}{c^2} = 1.$$
   - **Shape of the Cross-Section:** In every horizontal plane $z = c \neq 0$, the cross-section is an **ellipse** centered at $(0, 0, c)$ on the $Oz$-axis.
   - **Different Scales Along the Axes:**
     - The semiaxis along the **$x$-axis** is:
       $$a(c) = \frac{|c|}{2}.$$
     - The semiaxis along the **$y$-axis** is:
       $$b(c) = |c|.$$
     Notice that $b(c) = 2a(c)$: at every non-zero height $z = c$, the ellipse is **twice as wide along the $y$-axis as it is along the $x$-axis** (it is compressed along the $x$-direction because of the factor $4$ multiplying $x^2$, and stretched along the $y$-direction).
   - **Dependence on $c$:** As $|c|$ increases linearly, both semiaxes $a(c) = |c|/2$ and $b(c) = |c|$ grow **linearly** with $|c|$, keeping their $1:2$ aspect ratio constant.

#### Step 2: Describe the Vertical Cross-Sections by the Planes $x = 0$ and $y = 0$
1. **Cross-Section by the Plane $x = 0$ (the $yz$-plane):**
   Substitute $x = 0$ into $4x^2 + y^2 = z^2$:
   $$4(0)^2 + y^2 = z^2 \implies y^2 = z^2 \iff z^2 - y^2 = 0 \iff (z - y)(z + y) = 0.$$
   Thus:
   $$z = y \quad \text{or} \quad z = -y \quad (x = 0).$$
   - **Description:** A **pair of intersecting straight lines** in the $yz$-plane passing through the origin $(0,0,0)$ with slopes $\pm 1$ (making a $45^\circ$ angle with both the $y$-axis and the $z$-axis). At height $z = c$, these lines are at distance $|y| = |c|$ from the $z$-axis.

2. **Cross-Section by the Plane $y = 0$ (the $xz$-plane):**
   Substitute $y = 0$ into $4x^2 + y^2 = z^2$:
   $$4x^2 + 0^2 = z^2 \implies 4x^2 = z^2 \iff z^2 - 4x^2 = 0 \iff (z - 2x)(z + 2x) = 0.$$
   Thus:
   $$z = 2x \quad \text{or} \quad z = -2x \quad \left(\text{equivalently } x = \pm \frac{z}{2}, \; y = 0\right).$$
   - **Description:** A **pair of intersecting straight lines** in the $xz$-plane passing through the origin $(0,0,0)$ with **steeper slopes** $\pm 2$ with respect to $x$. At height $z = c$, these lines are only at distance $|x| = |c|/2$ from the $z$-axis, so the V-shape in the $xz$-plane is **narrower (steeper)** than the V-shape in the $yz$-plane.

#### Step 3: Identify the Surface from Its Cross-Sections
Putting all cross-section information together:
- The surface passes through a single apex at $(0, 0, 0)$ when $z = 0$.
- Its vertical cross-sections through the $Oz$-axis ($x = 0$ and $y = 0$) are **straight lines intersecting at the origin**, which grow linearly apart as $|z|$ increases.
- Its horizontal cross-sections for $z = c \neq 0$ are **ellipses** (with semiaxes $a(c) = |c|/2$ along $Ox$ and $b(c) = |c|$ along $Oy$) whose size scales linearly with $|z|$.

Therefore, the surface is an **elliptic cone** (specifically, a double cone with elliptical horizontal cross-sections, vertex at the origin $(0,0,0)$, axis along the $Oz$-axis, narrower along the $x$-axis and wider along the $y$-axis).

#### Step 4: Sketch of the Elliptic Cone $4x^2 + y^2 = z^2$
```text
                         z
                         ^
        \      . - ~ ~ ~ | ~ ~ ~ - .      /
         \  . '    ^ a=|c|/2 (x)    ' .  /   <-- Elliptical cross-section at z = c
          \(   <---+---|---+--->       )/        (narrower in x, wider in y: b = |c|)
           \' . _  v   |       _ . '  /
            \     ~ ~ ~|~ ~ ~        /
             \  z=-2x  |  z=y       /        <-- Steeper lines z = +-2x in xz-plane,
              \   \    |    /      /             wider lines z = +-y in yz-plane
               \   \   |   /      /
                \   \  |  /      /
                 \   \ | /      /
  ----------------\---*-------/----------------> y (wider axis, b = |c|)
                 /   /|\     /
                /  /  | \   /   Apex at (0,0,0)
               / /    |  \ /
              /       |   \
             / . - ~ ~|~ ~ \ - .
            /(        |     \   )
           /  ' - . _ | _ . -\ '
          /           |       \
                      v
                      x (narrower axis, a = |c|/2)
```

## Verification and Consistency Checks

1. **Verification for Equation 1 ($4x^2 + 9y^2 - 8x + 36y + 4 = 0$):**
   - **Expand the canonical form $\frac{(x - 1)^2}{9} + \frac{(y + 2)^2}{4} = 1$:**
     Multiply by $36$:
     $$4(x^2 - 2x + 1) + 9(y^2 + 4y + 4) = 36 \implies 4x^2 - 8x + 4 + 9y^2 + 36y + 36 - 36 = 0 \implies 4x^2 + 9y^2 - 8x + 36y + 4 = 0. \quad \checkmark$$
   - **Substitute the four vertices into the original equation:**
     - $V_2(4, -2)$: $4(4)^2 + 9(-2)^2 - 8(4) + 36(-2) + 4 = 64 + 36 - 32 - 72 + 4 = 104 - 104 = 0$. $\checkmark$
     - $V_1(-2, -2)$: $4(-2)^2 + 9(-2)^2 - 8(-2) + 36(-2) + 4 = 16 + 36 + 16 - 72 + 4 = 72 - 72 = 0$. $\checkmark$
     - $B_2(1, 0)$: $4(1)^2 + 9(0)^2 - 8(1) + 36(0) + 4 = 4 + 0 - 8 + 0 + 4 = 0$. $\checkmark$
     - $B_1(1, -4)$: $4(1)^2 + 9(-4)^2 - 8(1) + 36(-4) + 4 = 4 + 144 - 8 - 144 + 4 = 0$. $\checkmark$

2. **Verification for Equation 2 ($4x^2 + y^2 = z^2$):**
   - **Test cross-section at height $z = 2$:**
     Our formula gives the ellipse $\frac{x^2}{1^2} + \frac{y^2}{2^2} = 1$ with $x$-vertices $(\pm 1, 0, 2)$ and $y$-vertices $(0, \pm 2, 2)$:
     - At $(\pm 1, 0, 2)$: $\text{LHS} = 4(\pm 1)^2 + 0^2 = 4$, $\text{RHS} = 2^2 = 4$. $\checkmark$
     - At $(0, \pm 2, 2)$: $\text{LHS} = 4(0)^2 + (\pm 2)^2 = 4$, $\text{RHS} = 2^2 = 4$. $\checkmark$
     Notice that $(\pm 1, 0, 2)$ also lies on the $y = 0$ trace lines $z = \pm 2x$, and $(0, \pm 2, 2)$ also lies on the $x = 0$ trace lines $z = \pm y$, confirming that the horizontal and vertical cross-sections intersect consistently.
