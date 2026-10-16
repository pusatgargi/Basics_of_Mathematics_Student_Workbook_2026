# Problem 15: Complete Classification of a Line Relative to a Plane

## Problem Statement

Let
$$L:p+tv,\qquad \Pi:n\cdot x=d.$$
State the conditions distinguishing the three cases: one intersection point, parallel with no common points, and the line contained in the plane. Then illustrate each case with your own simple numerical example.

## Theoretical Background and Concepts

In $\mathbb{R}^3$, let a line $L$ and a plane $\Pi$ be defined in general vector notation by:
$$L: \vec{x}(t) = \vec{p} + t\vec{v}, \quad t \in \mathbb{R} \quad (\vec{v} \neq \vec{0}),$$
$$\Pi: \vec{n} \cdot \vec{x} = d \quad (\vec{n} \neq \vec{0}),$$
where:
- $\vec{p} \in \mathbb{R}^3$ is a fixed reference point on the line $L$,
- $\vec{v} \in \mathbb{R}^3 \setminus \{\vec{0}\}$ is the direction vector of the line $L$,
- $\vec{n} \in \mathbb{R}^3 \setminus \{\vec{0}\}$ is a normal vector to the plane $\Pi$,
- $d \in \mathbb{R}$ is the scalar constant of the plane $\Pi$.

To determine the intersection $L \cap \Pi$, we substitute the general point $\vec{x}(t) = \vec{p} + t\vec{v}$ of the line into the equation of the plane $\vec{n} \cdot \vec{x} = d$. Using the linearity (distributivity) of the dot product:
$$\vec{n} \cdot (\vec{p} + t\vec{v}) = d \iff \vec{n} \cdot \vec{p} + t(\vec{n} \cdot \vec{v}) = d \iff (\vec{n} \cdot \vec{v})\,t = d - \vec{n} \cdot \vec{p}.$$
This reduces the geometric relationship between $L$ and $\Pi$ to a single scalar linear equation in the real unknown $t$:
$$A t = B, \qquad \text{where} \quad A = \vec{n} \cdot \vec{v} \quad \text{and} \quad B = d - \vec{n} \cdot \vec{p}.$$

## Detailed Step-by-Step Solution

### Part 1: Complete Algebraic and Geometric Classification of the Three Cases

Depending on the values of the two scalar quantities $\vec{n} \cdot \vec{v}$ and $\vec{n} \cdot \vec{p} - d$, there are exactly three mutually exclusive and exhaustive cases:

```
    Case 1: One Intersection Point       Case 2: Strictly Parallel        Case 3: Contained in Plane
           (n . v != 0)                 (n . v = 0, n . p != d)           (n . v = 0, n . p = d)

                \  L                            p *-------> v  L
        ^ n      \                              ^ n                              ^ n
        |         \                             |                                |
   -----+----------*--------- Pi           -----+---------------- Pi        -----*-------> v----- Pi
                    \                                                            p         L
                     v
```

#### Case 1: One Intersection Point ($L \cap \Pi = \{\vec{x}^*\}$)
- **Distinguishing Condition**:
  $$\vec{n} \cdot \vec{v} \neq 0.$$
  *(Note: No condition on $\vec{n} \cdot \vec{p}$ is required; whether $\vec{p}$ lies on $\Pi$ or not, the line intersects $\Pi$ at exactly one point.)*
- **Algebraic Justification**:
  Since the coefficient of $t$ is $A = \vec{n} \cdot \vec{v} \neq 0$, the linear equation $(\vec{n} \cdot \vec{v})t = d - \vec{n} \cdot \vec{p}$ has a **unique real solution**:
  $$t^* = \frac{d - \vec{n} \cdot \vec{p}}{\vec{n} \cdot \vec{v}},$$
  yielding the unique intersection point:
  $$\vec{x}^* = \vec{p} + \left(\frac{d - \vec{n} \cdot \vec{p}}{\vec{n} \cdot \vec{v}}\right)\vec{v}.$$
- **Geometric Meaning**:
  The direction vector $\vec{v}$ is not perpendicular to the normal vector $\vec{n}$, so the line is not parallel to the plane and pierces through the plane at a single point.

---

#### Case 2: Parallel with No Common Points ($L \cap \Pi = \emptyset$)
- **Distinguishing Condition**:
  $$\vec{n} \cdot \vec{v} = 0 \qquad \text{and} \qquad \vec{n} \cdot \vec{p} \neq d.$$
- **Algebraic Justification**:
  When $\vec{n} \cdot \vec{v} = 0$ and $d - \vec{n} \cdot \vec{p} \neq 0$, the equation $(\vec{n} \cdot \vec{v})t = d - \vec{n} \cdot \vec{p}$ becomes:
  $$0 \cdot t = d - \vec{n} \cdot \vec{p} \neq 0,$$
  which is a contradiction for every $t \in \mathbb{R}$. The solution set is empty.
- **Geometric Meaning**:
  The condition $\vec{n} \cdot \vec{v} = 0$ means $\vec{v} \perp \vec{n}$, so the line's direction is parallel to the plane. The condition $\vec{n} \cdot \vec{p} \neq d$ means the reference point $\vec{p}$ does not lie in the plane. Thus, the line starts outside the plane and travels parallel to it, never meeting the plane.

---

#### Case 3: Line Contained in the Plane ($L \subset \Pi$, i.e., $L \cap \Pi = L$)
- **Distinguishing Condition**:
  $$\vec{n} \cdot \vec{v} = 0 \qquad \text{and} \qquad \vec{n} \cdot \vec{p} = d.$$
- **Algebraic Justification**:
  When $\vec{n} \cdot \vec{v} = 0$ and $d - \vec{n} \cdot \vec{p} = 0$, the equation $(\vec{n} \cdot \vec{v})t = d - \vec{n} \cdot \vec{p}$ becomes:
  $$0 \cdot t = 0,$$
  which is an identity satisfied by **every $t \in \mathbb{R}$**. Every point on the line satisfies the plane equation.
- **Geometric Meaning**:
  The reference point $\vec{p}$ lies inside the plane ($\vec{n} \cdot \vec{p} = d$), and the line's direction $\vec{v}$ is parallel to the plane ($\vec{n} \cdot \vec{v} = 0$). Therefore, moving from $\vec{p}$ in the direction $\vec{v}$ never leaves the plane, and the entire line lies within $\Pi$.

---

### Summary Table

| Case | Relative Position | Condition on $\vec{n} \cdot \vec{v}$ | Condition on $\vec{n} \cdot \vec{p}$ | Solutions for $t$ | Intersection $L \cap \Pi$ |
| :--- | :--- | :---: | :---: | :---: | :---: |
| **1** | Intersects at one point | $\vec{n} \cdot \vec{v} \neq 0$ | Any ($\vec{n} \cdot \vec{p} \in \mathbb{R}$) | Unique $t^* = \frac{d - \vec{n}\cdot\vec{p}}{\vec{n}\cdot\vec{v}}$ | Single point $\{\vec{p} + t^*\vec{v}\}$ |
| **2** | Strictly parallel (disjoint) | $\vec{n} \cdot \vec{v} = 0$ | $\vec{n} \cdot \vec{p} \neq d$ | None ($\emptyset$) | Empty set $\emptyset$ |
| **3** | Line lies in the plane | $\vec{n} \cdot \vec{v} = 0$ | $\vec{n} \cdot \vec{p} = d$ | All $t \in \mathbb{R}$ | Entire line $L$ |

---

### Part 2: Simple Numerical Examples Illustrating Each Case

For clarity, let us fix the plane $\Pi: x + y + z = 1$, which has normal vector $\vec{n} = (1, 1, 1)$ and constant $d = 1$.

#### Example for Case 1 (One Intersection Point):
- Choose $\vec{p} = (0, 0, 0)$ and $\vec{v} = (1, 1, 1)$, so:
  $$L_1: (x, y, z) = (0, 0, 0) + t(1, 1, 1) = (t, t, t), \qquad \Pi: x + y + z = 1.$$
- Check the criterion:
  $$\vec{n} \cdot \vec{v} = (1)(1) + (1)(1) + (1)(1) = 3 \neq 0.$$
- Substituting $(t, t, t)$ into $x + y + z = 1$ gives $3t = 1 \implies t = \frac{1}{3}$, yielding the unique intersection point $\left(\frac{1}{3}, \frac{1}{3}, \frac{1}{3}\right)$.

#### Example for Case 2 (Parallel with No Common Points):
- Choose $\vec{p} = (0, 0, 0)$ and $\vec{v} = (1, -1, 0)$, so:
  $$L_2: (x, y, z) = (0, 0, 0) + t(1, -1, 0) = (t, -t, 0), \qquad \Pi: x + y + z = 1.$$
- Check the criteria:
  $$\vec{n} \cdot \vec{v} = (1)(1) + (1)(-1) + (1)(0) = 1 - 1 + 0 = 0,$$
  $$\vec{n} \cdot \vec{p} = (1)(0) + (1)(0) + (1)(0) = 0 \neq 1 = d.$$
- Substituting $(t, -t, 0)$ into $x + y + z = 1$ gives $t + (-t) + 0 = 1 \implies 0 = 1$, which has no solution. Thus $L_2 \cap \Pi = \emptyset$.

#### Example for Case 3 (Line Contained in the Plane):
- Choose $\vec{p} = (1, 0, 0)$ and $\vec{v} = (1, -1, 0)$, so:
  $$L_3: (x, y, z) = (1, 0, 0) + t(1, -1, 0) = (1 + t, -t, 0), \qquad \Pi: x + y + z = 1.$$
- Check the criteria:
  $$\vec{n} \cdot \vec{v} = (1)(1) + (1)(-1) + (1)(0) = 0,$$
  $$\vec{n} \cdot \vec{p} = (1)(1) + (1)(0) + (1)(0) = 1 = d.$$
- Substituting $(1 + t, -t, 0)$ into $x + y + z = 1$ gives $(1 + t) + (-t) + 0 = 1 \implies 1 = 1$ for all $t \in \mathbb{R}$. Thus $L_3 \subset \Pi$.

## Verification and Consistency Checks

Let us verify each of our three numerical examples by direct substitution into the general formula $(\vec{n} \cdot \vec{v})t = d - \vec{n} \cdot \vec{p}$ with $\vec{n} = (1, 1, 1)$ and $d = 1$:

1. **Case 1 Verification ($L_1: (t, t, t)$)**:
   - Formula: $t^* = \frac{d - \vec{n} \cdot \vec{p}}{\vec{n} \cdot \vec{v}} = \frac{1 - 0}{3} = \frac{1}{3}$.
   - Point: $\vec{x}\left(\frac{1}{3}\right) = \left(\frac{1}{3}, \frac{1}{3}, \frac{1}{3}\right)$.
   - Plane check: $\frac{1}{3} + \frac{1}{3} + \frac{1}{3} = 1 = d \quad \checkmark$

2. **Case 2 Verification ($L_2: (t, -t, 0)$)**:
   - Formula: $(\vec{n} \cdot \vec{v})t = d - \vec{n} \cdot \vec{p} \implies 0 \cdot t = 1 - 0 = 1$ (impossible).
   - Distance from any point $(t, -t, 0)$ on $L_2$ to $\Pi: x + y + z - 1 = 0$:
     $$d((t, -t, 0), \Pi) = \frac{|t + (-t) + 0 - 1|}{\sqrt{1^2 + 1^2 + 1^2}} = \frac{|-1|}{\sqrt{3}} = \frac{1}{\sqrt{3}} > 0 \quad \text{for all } t \in \mathbb{R} \quad \checkmark$$

3. **Case 3 Verification ($L_3: (1 + t, -t, 0)$)**:
   - Formula: $(\vec{n} \cdot \vec{v})t = d - \vec{n} \cdot \vec{p} \implies 0 \cdot t = 1 - 1 = 0$ (holds for all $t \in \mathbb{R}$).
   - Distance from any point $(1 + t, -t, 0)$ on $L_3$ to $\Pi: x + y + z - 1 = 0$:
     $$d((1 + t, -t, 0), \Pi) = \frac{|(1 + t) + (-t) + 0 - 1|}{\sqrt{1^2 + 1^2 + 1^2}} = \frac{|0|}{\sqrt{3}} = 0 \quad \text{for all } t \in \mathbb{R} \quad \checkmark$$
