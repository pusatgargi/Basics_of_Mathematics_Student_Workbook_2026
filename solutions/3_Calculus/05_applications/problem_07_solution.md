# Problem 7: Exponential Growth

## Problem Statement

Assume the model
$$
N(t)=N_0e^{kt},\qquad k>0.
$$

1. Verify by differentiation that the model satisfies the relation $N'(t)=kN(t)$.
2. Find the population doubling time.
3. Explain why the doubling time does not depend on $N_0$.

## Theoretical Background and Concepts

1. **Malthusian (Exponential) Growth Model**:
   In biology, demography, nuclear physics, and finance, many processes evolve such that the instantaneous rate of change of a quantity $N(t)$ is directly proportional to the current amount present:
   $$
   \frac{dN}{dt} = k N(t),
   $$
   where $k > 0$ is the **relative (specific or per-capita) growth rate** (with dimension $[\text{time}]^{-1}$) and $N_0 = N(0) > 0$ is the initial value at $t = 0$.

2. **Chain Rule for Exponential Functions**:
   The natural exponential function $e^u$ is its own derivative: $\frac{d}{du}(e^u) = e^u$. For a composite function $e^{kt}$, the chain rule yields:
   $$
   \frac{d}{dt}\left(e^{kt}\right) = e^{kt} \cdot \frac{d}{dt}(kt) = k e^{kt}.
   $$

3. **Doubling Time ($T_d$)**:
   The doubling time is the time interval $\Delta t = T_d$ required for the quantity $N(t)$ to grow to twice its value:
   $$
   N(t + T_d) = 2 N(t) \quad \text{(or specifically } N(T_d) = 2 N_0 \text{ starting from } t = 0\text{)}.
   $$

## Detailed Step-by-Step Solution

### Part 1: Verification that $N'(t) = kN(t)$

We are given the exponential growth model:
$$
N(t) = N_0 e^{kt}, \qquad k > 0, \quad N_0 > 0.
$$
Differentiating $N(t)$ with respect to $t$, using the constant multiple rule and the chain rule for $e^{kt}$:
$$
\begin{aligned}
N'(t) &= \frac{d}{dt}\left(N_0 e^{kt}\right) \\
&= N_0 \cdot \frac{d}{dt}\left(e^{kt}\right) \\
&= N_0 \cdot \left(e^{kt} \cdot \frac{d}{dt}(kt)\right) \\
&= N_0 \cdot k e^{kt} \\
&= k\left(N_0 e^{kt}\right).
\end{aligned}
$$
Since $N(t) = N_0 e^{kt}$, we substitute $N(t)$ into the right-hand side to obtain:
$$
N'(t) = k N(t).
$$
This confirms that $N(t) = N_0 e^{kt}$ satisfies the differential relation $N'(t) = kN(t)$ for all $t \in \mathbb{R}$.

---

### Part 2: Finding the Population Doubling Time

Let $T_d$ denote the doubling time starting from $t = 0$, at which the population equals $N(0) = N_0 e^{k \cdot 0} = N_0$. By definition of doubling time, at $t = T_d$ the population reaches $2N_0$:
$$
N(T_d) = 2N_0.
$$
Substituting the model formula $N(T_d) = N_0 e^{k T_d}$ gives:
$$
N_0 e^{k T_d} = 2N_0.
$$
Since the initial population is non-zero ($N_0 > 0$), we divide both sides by $N_0$:
$$
e^{k T_d} = 2.
$$
Taking the natural logarithm ($\ln$) of both sides:
$$
\ln\left(e^{k T_d}\right) = \ln 2 \iff k T_d = \ln 2.
$$
Since $k > 0$, dividing by $k$ yields the doubling time:
$$
T_d = \frac{\ln 2}{k} \approx \frac{0.69315}{k}.
$$

---

### Part 3: Why the Doubling Time Does Not Depend on $N_0$

We can explain the independence of $T_d$ from $N_0$ from both an **algebraic** and a **physical/modeling** perspective:

1. **Algebraic Explanation (Scale Invariance)**:
   The parameter $N_0$ enters the function $N(t) = N_0 e^{kt}$ purely as a linear scaling factor. When we ask for the time $T_d$ required to reach $2N_0$, the factor $N_0$ appears identically on both sides of the equation $N_0 e^{k T_d} = 2N_0$ and cancels out completely. More generally, starting at any arbitrary time $t_1$ with population $N(t_1)$, the ratio of the population after an elapsed time $\Delta t$ to the population at $t_1$ is:
   $$
   \frac{N(t_1 + \Delta t)}{N(t_1)} = \frac{N_0 e^{k(t_1 + \Delta t)}}{N_0 e^{k t_1}} = e^{k \Delta t},
   $$
   which depends solely on the growth rate $k$ and the elapsed time $\Delta t$, not on the starting level $N_0$ or $N(t_1)$.

2. **Physical / Population-Dynamics Explanation**:
   According to the relation $N'(t) = kN(t)$, every individual in the population reproduces at the same average per-capita rate $k = \frac{N'(t)}{N(t)}$. If a population starts twice as large ($2N_0$ instead of $N_0$), it has twice as many individuals to gain in order to double, **but** because there are twice as many individuals reproducing simultaneously, its absolute growth rate $N'(t)$ is also twice as fast at every moment. The doubled requirement and the doubled absolute growth rate cancel each other out, leaving the doubling time $T_d = \frac{\ln 2}{k}$ invariant.

## Verification and Consistency Checks

1. **Direct Substitution Check**:
   Evaluating $N(t)$ at $t = T_d = \frac{\ln 2}{k}$:
   $$
   N\left(\frac{\ln 2}{k}\right) = N_0 \exp\left(k \cdot \frac{\ln 2}{k}\right) = N_0 e^{\ln 2} = 2N_0.
   $$
   More generally, after $m$ doubling periods ($t = m T_d$), we have $N(m T_d) = N_0 e^{m \ln 2} = N_0 \cdot 2^m$.

2. **Dimensional Analysis**:
   Since the exponent $kt$ in $e^{kt}$ must be dimensionless, the units of $k$ are $[\text{time}]^{-1}$. Because $\ln 2$ is a dimensionless pure number, the ratio $T_d = \frac{\ln 2}{k}$ has units of $\frac{1}{[\text{time}]^{-1}} = [\text{time}]$, which is dimensionally consistent.

3. **Limiting Behavior with Respect to $k$**:
   - As $k \to \infty$ (faster growth rate), $T_d = \frac{\ln 2}{k} \to 0$ (the population doubles almost instantaneously).
   - As $k \to 0^+$ (stagnant population), $T_d = \frac{\ln 2}{k} \to +\infty$ (the population takes infinitely long to double).
