# Problem 12: Complete Model and Computer Verification

## Problem Statement

A museum wants to create a rectangular exhibition room next to an existing straight wall. The side along the wall does not need to be built. The remaining three sides are to be constructed to two different standards: the two sides perpendicular to the wall cost $300\ \mathrm{PLN/m}$ each, while the side parallel to the wall costs $500\ \mathrm{PLN/m}$. The budget is $30\,000\ \mathrm{PLN}$.

Build a model that maximizes the area of the room and prepare a complete analysis containing:

- definition of variables and units,
- mathematical model,
- domain resulting from the problem statement,
- computation of the derivative,
- determination and verification of the optimum,
- interpretation of the result,
- graph of the objective function,
- numerical verification of several values near the optimum found.

Finally, indicate which part of the solution required modeling the problem and which part was only the execution of the calculation. Produce the graph and computer calculations only after completing the mathematical solution, and treat them as verification.

## Theoretical Background and Concepts

1. **Constrained Optimization with Weighted Linear Costs**:
   Unlike standard perimeter-constrained problems where all sides have equal unit weight, real-world engineering and architectural problems assign different unit costs ($c_\perp$ and $c_\parallel$) to different walls. To maximize the enclosed rectangular area $A = x y$ under a fixed budget $B$, the full budget is utilized at the optimum, giving a linear cost constraint:
   $$
   2 c_\perp x + c_\parallel y = B.
   $$
2. **Complete Applied Optimization Pipeline**:
   A rigorous applied mathematical analysis separates the workflow into three distinct phases:
   - **Phase I — Mathematical Modeling**: Translating the verbal, geometric, and economic description into variables, units, constraints, an objective function, and a feasible domain.
   - **Phase II — Analytical Calculation**: Differentiating the objective function, solving for critical points, and proving optimality using first and second derivative tests.
   - **Phase III — Interpretation and Independent Computational Verification**: Interpreting the solution in context and cross-checking the analytical result using graphical visualization and numerical tables around the critical point.

## Detailed Step-by-Step Solution

### 1. Definition of Variables and Units

Let us introduce the variables and parameters describing the rectangular exhibition room:
- $x\ [\mathrm{m}]$ — length of each of the two newly built sides **perpendicular** to the existing wall ($x > 0$).
- $y\ [\mathrm{m}]$ — length of the single newly built side **parallel** to the existing wall ($y > 0$).
- $c_\perp = 300\ [\mathrm{PLN/m}]$ — unit construction cost of each wall perpendicular to the existing wall.
- $c_\parallel = 500\ [\mathrm{PLN/m}]$ — unit construction cost of the wall parallel to the existing wall.
- $B = 30\,000\ [\mathrm{PLN}]$ — total available construction budget.
- $A\ [\mathrm{m^2}]$ — floor area of the rectangular exhibition room ($A = x \cdot y$).

---

### 2. Mathematical Model

- **Budget Constraint**:
  There are two perpendicular walls of length $x$ (each costing $300x\ \mathrm{PLN}$) and one parallel wall of length $y$ (costing $500y\ \mathrm{PLN}$). The fourth side lies along the existing museum wall and costs $0\ \mathrm{PLN}$. Since maximizing area requires using the entire available budget of $30\,000\ \mathrm{PLN}$, the cost equation is:
  $$
  2 \cdot 300x + 500y = 30\,000 \iff 600x + 500y = 30\,000.
  $$
  Dividing both sides by $100$ simplifies the constraint to:
  $$
  6x + 5y = 300 \implies y = \frac{300 - 6x}{5} = 60 - \frac{6}{5}x = 60 - 1.2x \quad [\mathrm{m}].
  $$

- **Objective Function**:
  The area of the rectangle is $A = x \cdot y$. Substituting $y = 60 - \frac{6}{5}x$ expresses the area as a single-variable quadratic function of $x$:
  $$
  A(x) = x\left(60 - \frac{6}{5}x\right) = 60x - \frac{6}{5}x^2 = 60x - 1.2x^2 \quad [\mathrm{m^2}].
  $$

---

### 3. Domain Resulting from the Problem Statement

For the exhibition room to be a physically valid non-degenerate rectangle, both side lengths $x$ and $y$ must be strictly positive:
$$
\begin{cases}
x > 0, \\
y = 60 - \frac{6}{5}x > 0 \iff \frac{6}{5}x < 60 \iff x < 50.
\end{cases}
$$
Therefore, the feasible domain resulting from the problem statement is the open interval:
$$
D = (0, 50) \quad (\text{in meters}).
$$
*(At the endpoints $x = 0\ \mathrm{m}$ and $x = 50\ \mathrm{m}$, the room degenerates to zero area, $A(0) = A(50) = 0\ \mathrm{m^2}$.)*

---

### 4. Computation of the Derivative

Differentiating the objective function $A(x) = 60x - \frac{6}{5}x^2$ with respect to $x$ on $(0, 50)$:
$$
A'(x) = \frac{d}{dx}\left(60x - \frac{6}{5}x^2\right) = 60 - \frac{12}{5}x = 60 - 2.4x \quad [\mathrm{m}].
$$
The second derivative is:
$$
A''(x) = \frac{d}{dx}\left(60 - \frac{12}{5}x\right) = -\frac{12}{5} = -2.4 \quad [\text{dimensionless}].
$$

---

### 5. Determination and Verification of the Optimum

- **Finding the Stationary Point**:
  Setting the first derivative equal to zero:
  $$
  A'(x) = 0 \iff 60 - \frac{12}{5}x = 0 \iff \frac{12}{5}x = 60 \iff x^* = \frac{60 \times 5}{12} = 25\ \mathrm{m}.
  $$
  The critical point $x^* = 25\ \mathrm{m}$ lies strictly inside the feasible domain $D = (0, 50)$.

- **Verification of Global Maximum**:
  1. **First Derivative Test**:
     Since $A'(x) = \frac{12}{5}(25 - x)$:
     - For $x \in (0, 25)$, $A'(x) > 0$, so $A(x)$ is **strictly increasing** on $(0, 25]$.
     - For $x \in (25, 50)$, $A'(x) < 0$, so $A(x)$ is **strictly decreasing** on $[25, 50)$.
     Thus, $x^* = 25\ \mathrm{m}$ is the unique global maximum of $A(x)$ on $(0, 50)$.
  2. **Second Derivative Test**:
     $A''(25) = -2.4 < 0$, confirming that the function is strictly concave and attains its maximum at $x^* = 25\ \mathrm{m}$.

- **Optimal Dimensions and Maximum Area**:
  - Perpendicular side length: $x^* = 25\ \mathrm{m}$.
  - Parallel side length: $y^* = 60 - \frac{6}{5}(25) = 60 - 30 = 30\ \mathrm{m}$.
  - Maximum exhibition area:
    $$
    A_{\max} = A(25) = 25\ \mathrm{m} \times 30\ \mathrm{m} = 750\ \mathrm{m^2}.
    $$

---

### 6. Interpretation of the Result

1. **Architectural Interpretation**:
   To obtain the largest possible exhibition room within the $30\,000\ \mathrm{PLN}$ budget, the museum should build the two walls perpendicular to the existing wall with length **$25\ \mathrm{m}$ each**, and the wall parallel to the existing wall with length **$30\ \mathrm{m}$**, yielding a floor area of **$750\ \mathrm{m^2}$**.
2. **Economic Interpretation (Equal Budget Allocation Principle)**:
   - Total cost of the two perpendicular walls: $2 \times 25\ \mathrm{m} \times 300\ \mathrm{PLN/m} = 15\,000\ \mathrm{PLN}$ ($50\%$ of budget).
   - Total cost of the parallel wall: $30\ \mathrm{m} \times 500\ \mathrm{PLN/m} = 15\,000\ \mathrm{PLN}$ ($50\%$ of budget).
   Even though the unit costs in the two directions are unequal ($600\ \mathrm{PLN/m}$ combined in the $x$-direction vs. $500\ \mathrm{PLN/m}$ in the $y$-direction), maximizing the product $x \cdot y$ subject to $c_x x + c_y y = B$ always splits the total expenditure equally ($B/2$ each) between the two orthogonal directions!

---

### 7. Graph of the Objective Function (Post-Solution Verification)

Having completed the analytical solution, we plot the parabola $A(x) = 60x - 1.2x^2$ over $[0, 50]$:

```text
  A(x) [m^2]
   750 +                         * (25, 750)  <-- Global Maximum
       |                     *   :   *
   720 +                  *      :      *
       |                *        :        *
   600 +              *          :          *
       |            *            :            *
   480 +          *              :              *
       |        *                :                *
   360 +       *                 :                 *
       |     *                   :                   *
   240 +    *                    :                    *
       |  *                      :                      *
   120 + *                       :                       *
       |*                        :                        *
     0 +----+----+----+----+----+----+----+----+----+----+---> x [m]
       0    5   10   15   20   25   30   35   40   45   50
```

---

### 8. Numerical Verification of Values Near the Optimum

To verify our analytical solution computationally, we evaluate $y(x) = 60 - 1.2x$, the total cost $600x + 500y$, the area $A(x) = 60x - 1.2x^2$, and the derivative $A'(x) = 60 - 2.4x$ at points across the domain and in a tight neighborhood of $x^* = 25\ \mathrm{m}$:

| $x\ [\mathrm{m}]$ | $y = 60 - 1.2x\ [\mathrm{m}]$ | Budget Check $600x+500y\ [\mathrm{PLN}]$ | Area $A(x) = x \cdot y\ [\mathrm{m^2}]$ | Derivative $A'(x)\ [\mathrm{m}]$ | Difference $A(x) - A_{\max}\ [\mathrm{m^2}]$ |
| :---: | :---: | :---: | :---: | :---: | :---: |
| $10.0$ | $48.00$ | $30\,000$ | $480.000$ | $+36.00$ | $-270.000$ |
| $20.0$ | $36.00$ | $30\,000$ | $720.000$ | $+12.00$ | $-30.000$ |
| $24.0$ | $31.20$ | $30\,000$ | $748.800$ | $+2.40$ | $-1.200$ |
| $24.5$ | $30.60$ | $30\,000$ | $749.700$ | $+1.20$ | $-0.300$ |
| $24.9$ | $30.12$ | $30\,000$ | $749.988$ | $+0.24$ | $-0.012$ |
| **$25.0$** | **$30.00$** | **$30\,000$** | **$750.000$** | **$0.00$** | **$0.000$ (Max)** |
| $25.1$ | $29.88$ | $30\,000$ | $749.988$ | $-0.24$ | $-0.012$ |
| $25.5$ | $29.40$ | $30\,000$ | $749.700$ | $-1.20$ | $-0.300$ |
| $26.0$ | $28.80$ | $30\,000$ | $748.800$ | $-2.40$ | $-1.200$ |
| $30.0$ | $24.00$ | $30\,000$ | $720.000$ | $-12.00$ | $-30.000$ |
| $40.0$ | $12.00$ | $30\,000$ | $480.000$ | $-36.00$ | $-270.000$ |

---

### 9. Distinction Between Modeling and Calculation Execution

| Stage of Solution | Classification | Explanation |
| :--- | :--- | :--- |
| Choosing variables $x, y$ and assigning physical units ($\mathrm{m}, \mathrm{PLN}$) | **Modeling the Problem** | Requires translating the geometric layout (existing wall vs. three new walls) into mathematical quantities. |
| Formulating the budget constraint $600x + 500y = 30\,000$ and area $A = xy$ | **Modeling the Problem** | Requires recognizing that two perpendicular walls cost $300\ \mathrm{PLN/m}$ each ($600x$ total), one parallel wall costs $500y$, and full budget utilization maximizes area. |
| Determining the domain $D = (0, 50)$ from $x > 0$ and $y > 0$ | **Modeling the Problem** | Imposes physical positivity constraints from geometry onto the algebraic variables. |
| Eliminating $y$, expanding $A(x) = 60x - 1.2x^2$, computing $A'(x) = 60 - 2.4x$, and solving $A'(x) = 0 \implies x^* = 25$ | **Execution of Calculation** | Purely algorithmic algebraic and calculus manipulations that follow standard differentiation and equation-solving rules. |
| Interpreting $x^*=25\ \mathrm{m}, y^*=30\ \mathrm{m}$ and checking the graph/table | **Interpretation & Verification** | Connects the abstract number $x^* = 25$ back to museum construction specifications and confirms accuracy. |

## Verification and Consistency Checks

1. **Vertex / Completing the Square Identity**:
   $$
   A(x) = 60x - 1.2x^2 = -1.2\left(x^2 - 50x + 625\right) + 1.2(625) = 750 - 1.2(x - 25)^2.
   $$
   This matches every entry in the numerical table: for a perturbation $\Delta x = x - 25$, the area drop is exactly $1.2(\Delta x)^2$ (e.g., for $\Delta x = \pm 0.1\ \mathrm{m}$, $\Delta A = -1.2(0.01) = -0.012\ \mathrm{m^2}$; for $\Delta x = \pm 1\ \mathrm{m}$, $\Delta A = -1.2\ \mathrm{m^2}$).

2. **Dimensional Consistency**:
   - $[600x] = [\mathrm{PLN/m}] \cdot [\mathrm{m}] = [\mathrm{PLN}]$, $[500y] = [\mathrm{PLN/m}] \cdot [\mathrm{m}] = [\mathrm{PLN}]$.
   - In $A(x) = 60x - 1.2x^2$, the coefficient $60 = \frac{30\,000\ \mathrm{PLN}}{500\ \mathrm{PLN/m}}$ has units of $\mathrm{m}$, and $1.2 = \frac{600\ \mathrm{PLN/m}}{500\ \mathrm{PLN/m}}$ is a dimensionless cost ratio, so both $60x$ and $1.2x^2$ have units of $\mathrm{m^2}$.
