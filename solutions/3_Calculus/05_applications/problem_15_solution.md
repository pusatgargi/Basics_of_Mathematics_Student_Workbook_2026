# Problem 15: Supplementary Cross-Sectional Problem — From Marginal Cost to Total Cost and Minimum Average Cost

## Problem Statement

*(Note: The official problem set `05_applications_en.md` intentionally contains 12 problems. This file provides a supplementary cross-sectional application problem and complete worked solution combining integration of rates and optimization in mathematical economics in the style of the workbook.)*

A technology manufacturer produces precision sensor modules. The fixed daily overhead cost of running the production line is $C_0 = 1600\ \mathrm{PLN}$, and the **marginal cost** (the instantaneous rate of change of total cost with respect to production volume $u$) is modeled by
$$
M(u) = 2u + 20 \quad [\mathrm{PLN/unit}], \qquad u \ge 0.
$$

1. Using integral calculus, reconstruct the total daily cost function $C(x)$ for producing $x$ units ($x > 0$).
2. Write the average cost per unit $A(x) = \frac{C(x)}{x}$, specify its domain, and find the production level $x^*$ that minimizes the average cost per unit.
3. Verify that at the optimal production level $x^*$, the average cost equals the marginal cost: $A(x^*) = M(x^*)$, and explain why this relationship holds for any smooth cost function.

## Theoretical Background and Concepts

In mathematical economics and operations research, differential and integral calculus connect three fundamental cost concepts:

1. **Marginal Cost ($M(x) = C'(x)$) and Total Cost ($C(x)$)**:
   The marginal cost $M(x) = C'(x)$ represents the approximate cost of producing one additional unit at production level $x$. Given the fixed cost $C(0) = C_0$ (incurred even when $x = 0$) and the marginal cost function $M(u)$, the Fundamental Theorem of Calculus reconstructs the total cost function:
   $$
   C(x) = C(0) + \int_0^x M(u)\,du = C_0 + \int_0^x C'(u)\,du.
   $$

2. **Average (Unit) Cost Function ($A(x)$)**:
   For any positive production level $x > 0$, the average cost per unit is the ratio of total cost to the number of units produced:
   $$
   A(x) = \frac{C(x)}{x} \quad [\mathrm{PLN/unit}].
   $$

3. **Marginal-Average Cost Intersection Theorem**:
   By the quotient rule of differentiation:
   $$
   A'(x) = \frac{d}{dx}\left(\frac{C(x)}{x}\right) = \frac{x C'(x) - C(x)}{x^2} = \frac{1}{x}\left(C'(x) - \frac{C(x)}{x}\right) = \frac{M(x) - A(x)}{x}.
   $$
   Consequently, $A'(x^*) = 0 \iff M(x^*) = A(x^*)$: the average cost is stationary precisely where the marginal cost curve intersects the average cost curve.

## Detailed Step-by-Step Solution

### Part 1: Reconstructing the Total Cost Function $C(x)$

Using the initial condition $C(0) = C_0 = 1600\ \mathrm{PLN}$ and integrating the marginal cost $M(u) = 2u + 20$ from $u = 0$ to $u = x$:
$$
\begin{aligned}
C(x) &= C_0 + \int_0^x M(u)\,du \\
&= 1600 + \int_0^x (2u + 20)\,du \\
&= 1600 + \left[2 \cdot \frac{u^2}{2} + 20u\right]_0^x \\
&= 1600 + \left(x^2 + 20x\right) - 0 \\
&= x^2 + 20x + 1600 \quad [\mathrm{PLN}].
\end{aligned}
$$

---

### Part 2: Minimizing the Average Cost Per Unit $A(x)$

**Step 2a: Formulate $A(x)$ and its domain.**
Dividing the total cost $C(x)$ by the number of units $x$ gives the average cost per unit:
$$
A(x) = \frac{C(x)}{x} = \frac{x^2 + 20x + 1600}{x} = x + 20 + \frac{1600}{x} \quad [\mathrm{PLN/unit}].
$$
Since division by $x$ requires a non-zero production quantity and production volume is positive, the continuous domain is:
$$
D = (0, \infty).
$$

**Step 2b: Differentiate $A(x)$ and find the stationary point.**
Differentiating $A(x) = x + 20 + 1600x^{-1}$ with respect to $x$ on $(0, \infty)$:
$$
A'(x) = 1 + 0 - \frac{1600}{x^2} = \frac{x^2 - 1600}{x^2} = \frac{(x - 40)(x + 40)}{x^2}.
$$
Setting $A'(x) = 0$:
$$
x^2 - 1600 = 0 \implies x = 40 \quad \text{or} \quad x = -40.
$$
Since $x \in (0, \infty)$, the unique critical point in the domain is:
$$
x^* = 40\text{ units}.
$$

**Step 2c: Justify that $x^* = 40$ is the global minimum.**
- **First Derivative Test**:
  - For $x \in (0, 40)$, $x - 40 < 0 \implies A'(x) < 0$, so $A(x)$ is **strictly decreasing** (spreading the fixed cost $1600\ \mathrm{PLN}$ over more units dominates).
  - For $x \in (40, \infty)$, $x - 40 > 0 \implies A'(x) > 0$, so $A(x)$ is **strictly increasing** (rising marginal production cost dominates).
- **Second Derivative Test**:
  $$
  A''(x) = \frac{3200}{x^3} > 0 \quad \text{for all } x > 0 \quad \left(A''(40) = \frac{3200}{64\,000} = 0.05 > 0\right).
  $$
Therefore, producing **$x^* = 40\text{ units}$** per day achieves the global minimum average cost:
$$
A_{\min} = A(40) = 40 + 20 + \frac{1600}{40} = 40 + 20 + 40 = 100\ \mathrm{PLN/unit}.
$$
*(The total daily cost at $x^* = 40$ is $C(40) = 40 \times 100 = 4000\ \mathrm{PLN}$.)*

---

### Part 3: Verification and Explanation of $A(x^*) = M(x^*)$

- **Direct Evaluation at $x^* = 40$**:
  - Minimum average cost: $A(40) = 100\ \mathrm{PLN/unit}$.
  - Marginal cost at $x^* = 40$: $M(40) = 2(40) + 20 = 80 + 20 = 100\ \mathrm{PLN/unit}$.
  Thus, $A(40) = M(40) = 100\ \mathrm{PLN/unit}$ holds identically.

- **General Mathematical and Economic Explanation**:
  1. **Calculus Proof**: For any differentiable cost function $C(x)$, the quotient rule gives $A'(x) = \frac{x C'(x) - C(x)}{x^2} = \frac{M(x) - A(x)}{x}$. At an interior minimum $x^* > 0$, $A'(x^*) = 0$ forces the numerator to vanish, which means $M(x^*) = A(x^*)$.
  2. **Intuitive Marginal-Average Principle**: As long as producing one more unit costs **less** than the current average ($M(x) < A(x)$), adding that unit pulls the average down ($A'(x) < 0$). Once producing one more unit costs **more** than the current average ($M(x) > A(x)$), adding that unit pulls the average up ($A'(x) > 0$). Therefore, the average reaches its lowest point at the exact crossover where $M(x^*) = A(x^*)$.

## Verification and Consistency Checks

1. **AM-GM Inequality Check**:
   For all $x > 0$:
   $$
   A(x) = 20 + \left(x + \frac{1600}{x}\right) \ge 20 + 2\sqrt{x \cdot \frac{1600}{x}} = 20 + 2(40) = 100\ \mathrm{PLN/unit},
   $$
   with equality if and only if $x = \frac{1600}{x} \iff x = 40$.

2. **Numerical Evaluation Near $x^* = 40$**:
   - $x = 32$: $A(32) = 32 + 20 + 50 = 102.00\ \mathrm{PLN/unit}$, $M(32) = 84 < A(32)$.
   - $x = 40$: $A(40) = 40 + 20 + 40 = 100.00\ \mathrm{PLN/unit}$, $M(40) = 100 = A(40)$.
   - $x = 50$: $A(50) = 50 + 20 + 32 = 102.00\ \mathrm{PLN/unit}$, $M(50) = 120 > A(50)$.
