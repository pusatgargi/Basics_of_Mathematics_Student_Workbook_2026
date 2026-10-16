# Problem 13: Supplementary Cross-Sectional Problem — Server Cooling Power: Extrema, Total Energy, and Average Demand

## Problem Statement

*(Note: The official problem set `05_applications_en.md` intentionally contains 12 problems. This file provides a supplementary cross-sectional application problem and complete worked solution combining differential and integral calculus in the style of the workbook.)*

During a $5$-hour high-load computation window ($0 \le t \le 5$, where $t$ is measured in hours), the instantaneous cooling power required by a data center server cluster is modeled by the function
$$
P(t) = -2t^3 + 15t^2 - 24t + 30 \quad [\mathrm{kW}], \qquad 0 \le t \le 5.
$$

1. Using differential calculus, find the intervals on which the cooling power is increasing or decreasing, and determine the absolute minimum and absolute maximum instantaneous power demand on $[0, 5]$.
2. Using integral calculus, compute the total electrical energy $E$ (in $\mathrm{kWh}$) consumed by the cooling system over the $5$-hour window.
3. Compute the average cooling power $P_{\text{avg}}$ on $[0, 5]$ and compare it with the minimum and maximum instantaneous power levels.

## Theoretical Background and Concepts

This cross-sectional problem integrates both branches of single-variable calculus to analyze a time-varying physical rate (electrical power $P(t)$):

1. **Differential Calculus for Instantaneous Rate Analysis and Global Extrema**:
   - The derivative $P'(t) = \frac{dP}{dt}$ (in $\mathrm{kW/h}$) measures how rapidly the power demand is ramping up ($P'(t) > 0$) or ramping down ($P'(t) < 0$).
   - By the **Extreme Value Theorem**, a continuous function $P(t)$ on a closed bounded interval $[a, b]$ attains its global minimum and global maximum either at interior stationary points where $P'(t) = 0$ or at the boundary endpoints $t = a$ and $t = b$.

2. **Integral Calculus for Energy Accumulation and Average Power**:
   - Instantaneous power is the rate of energy transfer with respect to time: $P(t) = E'(t)$. By the **Fundamental Theorem of Calculus**, the total energy consumed over $[a, b]$ is the definite integral of power:
     $$
     E = \int_a^b P(t)\,dt \quad [\mathrm{kWh}].
     $$
   - The **average power** over $[a, b]$ is the constant power level that would consume the exact same total energy $E$ over the duration $b - a$:
     $$
     P_{\text{avg}} = \frac{1}{b - a}\int_a^b P(t)\,dt = \frac{E}{b - a} \quad [\mathrm{kW}].
     $$

## Detailed Step-by-Step Solution

### Part 1: Monotonicity and Absolute Extrema of Cooling Power on $[0, 5]$

**Step 1a: Differentiate $P(t)$ and find critical points.**
Differentiating $P(t) = -2t^3 + 15t^2 - 24t + 30$ with respect to $t$:
$$
\begin{aligned}
P'(t) &= \frac{d}{dt}\left(-2t^3 + 15t^2 - 24t + 30\right) \\
&= -6t^2 + 30t - 24 \\
&= -6\left(t^2 - 5t + 4\right) \\
&= -6(t - 1)(t - 4) \quad [\mathrm{kW/h}].
\end{aligned}
$$
Setting $P'(t) = 0$ yields the stationary points:
$$
-6(t - 1)(t - 4) = 0 \implies t_1 = 1\ \mathrm{h} \quad \text{and} \quad t_2 = 4\ \mathrm{h}.
$$
Both critical points $t_1 = 1$ and $t_2 = 4$ lie in the interior of the domain $[0, 5]$.

**Step 1b: Determine intervals of monotonicity and local extrema.**
Analyzing the sign of $P'(t) = -6(t - 1)(t - 4)$ on $[0, 5]$:
- On $[0, 1)$: $(t - 1) < 0$ and $(t - 4) < 0 \implies P'(t) < 0$, so $P(t)$ is **strictly decreasing**.
- On $(1, 4)$: $(t - 1) > 0$ and $(t - 4) < 0 \implies P'(t) > 0$, so $P(t)$ is **strictly increasing**.
- On $(4, 5]$: $(t - 1) > 0$ and $(t - 4) > 0 \implies P'(t) < 0$, so $P(t)$ is **strictly decreasing**.

By the First Derivative Test (and confirmed by $P''(t) = -12t + 30$, where $P''(1) = 18 > 0$ and $P''(4) = -18 < 0$):
- $t = 1\ \mathrm{h}$ is a strict **local minimum**,
- $t = 4\ \mathrm{h}$ is a strict **local maximum**.

**Step 1c: Evaluate $P(t)$ at critical points and endpoints.**
- At $t = 0\ \mathrm{h}$: $P(0) = 30\ \mathrm{kW}$.
- At $t = 1\ \mathrm{h}$: $P(1) = -2(1)^3 + 15(1)^2 - 24(1) + 30 = -2 + 15 - 24 + 30 = 19\ \mathrm{kW}$.
- At $t = 4\ \mathrm{h}$: $P(4) = -2(4)^3 + 15(4)^2 - 24(4) + 30 = -128 + 240 - 96 + 30 = 46\ \mathrm{kW}$.
- At $t = 5\ \mathrm{h}$: $P(5) = -2(5)^3 + 15(5)^2 - 24(5) + 30 = -250 + 375 - 120 + 30 = 35\ \mathrm{kW}$.

Comparing all four candidate values:
- **Absolute minimum power demand**: $P_{\min} = P(1) = 19\ \mathrm{kW}$ (at $t = 1\ \mathrm{h}$).
- **Absolute maximum power demand**: $P_{\max} = P(4) = 46\ \mathrm{kW}$ (at $t = 4\ \mathrm{h}$).

---

### Part 2: Total Electrical Energy Consumed Over $[0, 5]$

Integrating $P(t)$ from $t = 0$ to $t = 5$:
$$
\begin{aligned}
E &= \int_0^5 P(t)\,dt = \int_0^5 \left(-2t^3 + 15t^2 - 24t + 30\right) dt \\
&= \left[-2 \cdot \frac{t^4}{4} + 15 \cdot \frac{t^3}{3} - 24 \cdot \frac{t^2}{2} + 30t\right]_0^5 \\
&= \left[-\frac{1}{2}t^4 + 5t^3 - 12t^2 + 30t\right]_0^5 \\
&= \left(-\frac{625}{2} + 5(125) - 12(25) + 30(5)\right) - 0 \\
&= -312.5 + 625 - 300 + 150 \\
&= 162.5\ \mathrm{kWh}.
\end{aligned}
$$
The cooling system consumes a total of **$162.5\ \mathrm{kWh}$** of electrical energy during the $5$-hour period.

---

### Part 3: Average Cooling Power and Comparison

Computing the average value of $P(t)$ on $[0, 5]$:
$$
P_{\text{avg}} = \frac{1}{5 - 0}\int_0^5 P(t)\,dt = \frac{162.5\ \mathrm{kWh}}{5\ \mathrm{h}} = 32.5\ \mathrm{kW}.
$$
**Comparison**:
$$
P_{\min} = 19\ \mathrm{kW} < P_{\text{avg}} = 32.5\ \mathrm{kW} < P_{\max} = 46\ \mathrm{kW}.
$$
In engineering terms, while the average load is $32.5\ \mathrm{kW}$ (which determines total electricity billing), the cooling infrastructure and power supply must be rated for at least the peak demand $P_{\max} = 46\ \mathrm{kW}$ (which is $41.5\%$ higher than the average load).

## Verification and Consistency Checks

1. **Inflection Point Symmetry Check**:
   Notice that $P''(t) = -12t + 30 = 0 \implies t_{\text{infl}} = 2.5\ \mathrm{h}$, which is the exact midpoint of $[0, 5]$! Because a cubic polynomial is point-symmetric about its inflection point $(2.5, P(2.5))$, the average value of $P(t)$ on any interval symmetric about $t = 2.5$ must equal $P(2.5)$ and also equal $\frac{P(0) + P(5)}{2}$ and $\frac{P(1) + P(4)}{2}$. Let us check:
   $$
   \begin{aligned}
   P(2.5) &= -2(15.625) + 15(6.25) - 24(2.5) + 30 = -31.25 + 93.75 - 60 + 30 = 32.5\ \mathrm{kW}, \\
   \frac{P(0) + P(5)}{2} &= \frac{30 + 35}{2} = 32.5\ \mathrm{kW}, \qquad \frac{P_{\min} + P_{\max}}{2} = \frac{19 + 46}{2} = 32.5\ \mathrm{kW}.
   \end{aligned}
   $$
   All three independent checks yield $32.5\ \mathrm{kW}$, confirming that $E = 5 \times 32.5 = 162.5\ \mathrm{kWh}$ is exact!
