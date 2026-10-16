# Problem 5: Distance from Velocity

## Problem Statement

The velocity of a car during the first five seconds is described by the function
$$
v(t)=4t+2\quad [\mathrm{m/s}].
$$

Compute the distance traveled and explain why the integral of velocity gives the change in position.

Then answer what would have to be changed in the reasoning if the velocity also took negative values.

## Theoretical Background and Concepts

In kinematics, position $s(t)$ and velocity $v(t)$ are linked by mutually inverse operations of differentiation and integration:

1. **Displacement (Net Change in Position) via the Fundamental Theorem of Calculus**:
   By definition, instantaneous velocity is the derivative of position: $v(t) = s'(t)$. Therefore, $s(t)$ is an antiderivative of $v(t)$. By the Fundamental Theorem of Calculus (Part 2), integrating the velocity over a time interval $[a, b]$ yields the net change in position (**displacement**):
   $$
   \int_a^b v(t)\,dt = \int_a^b s'(t)\,dt = s(b) - s(a) = \Delta s.
   $$
2. **Riemann Sum Interpretation**:
   Partitioning $[a, b]$ into $n$ small subintervals $[t_{i-1}, t_i]$ of duration $\Delta t_i = t_i - t_{i-1}$, the velocity $v(t)$ is approximately constant and equal to $v(t_i^*)$ on each brief subinterval. Thus, the small change in position over $[t_{i-1}, t_i]$ is approximately $\Delta s_i \approx v(t_i^*)\,\Delta t_i$. Summing these incremental displacements over the entire interval and taking the limit as the mesh size approaches zero ($\max \Delta t_i \to 0$) produces the definite integral:
   $$
   \Delta s = \sum_{i=1}^n \Delta s_i = \lim_{\max \Delta t_i \to 0} \sum_{i=1}^n v(t_i^*)\,\Delta t_i = \int_a^b v(t)\,dt.
   $$
3. **Displacement vs. Total Distance Traveled**:
   - **Displacement**: $\Delta s = \int_a^b v(t)\,dt$ is a signed quantity (motion in the negative direction cancels motion in the positive direction).
   - **Total Distance Traveled**: $S = \int_a^b |v(t)|\,dt$ is the integral of **speed** $|v(t)| \ge 0$, which accumulates the length of the path traveled regardless of direction.
   - When $v(t) \ge 0$ throughout $[a, b]$, we have $|v(t)| = v(t)$, so the total distance traveled coincides with the net displacement.

## Detailed Step-by-Step Solution

### Part 1: Computing the Distance Traveled Over the First Five Seconds

We are given the velocity function on the time interval $t \in [0, 5]$ (in seconds):
$$
v(t) = 4t + 2 \quad [\mathrm{m/s}].
$$

**Step 1a: Check the sign of $v(t)$ on $[0, 5]$.**
For all $t \in [0, 5]$, we have $4t \ge 0$, and therefore:
$$
v(t) = 4t + 2 \ge 2 > 0.
$$
Because the velocity is strictly positive throughout the entire interval $[0, 5]$, the car moves continuously in the positive direction without ever reversing direction. Consequently, $|v(t)| = v(t)$, and the total distance traveled $S$ equals the displacement $\Delta s$.

**Step 1b: Evaluate the definite integral.**
$$
\begin{aligned}
S = \int_0^5 v(t)\,dt &= \int_0^5 (4t + 2)\,dt \\
&= \left[4 \cdot \frac{t^2}{2} + 2t\right]_0^5 \\
&= \left[2t^2 + 2t\right]_0^5 \\
&= \left(2(5)^2 + 2(5)\right) - \left(2(0)^2 + 2(0)\right) \\
&= (50 + 10) - 0 \\
&= 60\ \mathrm{m}.
\end{aligned}
$$
During the first $5$ seconds, the car travels a total distance of **$60\ \mathrm{m}$**.

---

### Part 2: Why the Integral of Velocity Gives the Change in Position

There are two complementary ways to explain why $\int_a^b v(t)\,dt = s(b) - s(a)$:

1. **Analytical Explanation (Fundamental Theorem of Calculus)**:
   Velocity is defined as the instantaneous rate of change of position with respect to time:
   $$
   v(t) = \frac{ds}{dt} = s'(t).
   $$
   This means that the position function $s(t)$ is an antiderivative of the velocity function $v(t)$. By the Fundamental Theorem of Calculus, the definite integral of a rate of change $s'(t)$ from $t = a$ to $t = b$ equals the total net change in the antiderivative $s(t)$ between those endpoints:
   $$
   \int_a^b v(t)\,dt = \int_a^b s'(t)\,dt = s(b) - s(a).
   $$

2. **Physical Accumulation Explanation (Riemann Sums)**:
   For constant velocity $v$, change in position is simply $\Delta s = v \cdot \Delta t$. When $v(t)$ varies continuously with time, we divide $[a, b]$ into $n$ infinitesimal time intervals of length $\Delta t = \frac{b-a}{n}$. On the $i$-th subinterval $[t_{i-1}, t_i]$, velocity is nearly constant, so the car's position changes by $\Delta s_i \approx v(t_i)\Delta t$. Adding the position changes from all subintervals gives the telescoping sum:
   $$
   s(b) - s(a) = \sum_{i=1}^n \big(s(t_i) - s(t_{i-1})\big) \approx \sum_{i=1}^n v(t_i)\,\Delta t.
   $$
   In the limit as $\Delta t \to 0$ ($n \to \infty$), this Riemann sum converges to the definite integral $\int_a^b v(t)\,dt$.

---

### Part 3: What Changes If the Velocity Also Takes Negative Values

If $v(t)$ takes negative values on part of the interval $[a, b]$, the car moves backward (in the negative direction of the axis) during those times.
- The ordinary definite integral $\int_a^b v(t)\,dt = s(b) - s(a)$ still gives the **net displacement** (the signed difference between final and initial positions), where negative contributions from backward motion subtract from positive contributions of forward motion.
- To compute the actual **total distance traveled** (odometer reading), we must integrate the **speed** $|v(t)|$ instead of the signed velocity $v(t)$:
  $$
  S_{\text{total}} = \int_a^b |v(t)|\,dt.
  $$
- **Practical Computational Procedure**:
  1. Solve $v(t) = 0$ on $(a, b)$ to find all instants $t_1, t_2, \dots, t_k$ where the velocity changes sign (turning points).
  2. Split the integral at these points into subintervals on which $v(t)$ has a constant sign.
  3. Integrate $+v(t)$ on subintervals where $v(t) \ge 0$, and integrate $-v(t)$ on subintervals where $v(t) < 0$, then sum the resulting positive distances.

## Verification and Consistency Checks

1. **Unit Analysis**:
   $$
   [v(t)] \cdot [dt] = \left[\frac{\mathrm{m}}{\mathrm{s}}\right] \cdot [\mathrm{s}] = \mathrm{m},
   $$
   which matches the unit of distance/position.

2. **Kinematics Formula for Uniformly Accelerated Motion**:
   Since $v(t) = 4t + 2$ is linear, the car moves with constant acceleration $a = v'(t) = 4\ \mathrm{m/s^2}$ and initial velocity $v_0 = v(0) = 2\ \mathrm{m/s}$. Using the classical kinematic equation:
   $$
   S = v_0 t + \frac{1}{2}at^2 = (2)(5) + \frac{1}{2}(4)(5^2) = 10 + 50 = 60\ \mathrm{m}.
   $$

3. **Geometric Trapezoid Area Check**:
   The graph of $v(t) = 4t + 2$ over $[0, 5]$ forms a trapezoid above the $t$-axis with parallel vertical bases $v(0) = 2\ \mathrm{m/s}$ and $v(5) = 22\ \mathrm{m/s}$, and width $\Delta t = 5\ \mathrm{s}$. Its area is:
   $$
   \text{Area} = \frac{v(0) + v(5)}{2} \cdot \Delta t = \frac{2 + 22}{2} \cdot 5 = 12 \cdot 5 = 60\ \mathrm{m}.
   $$
