# Problem 11: Decomposition into Parallel and Perpendicular Components

## Problem Statement

Decompose $u=(3,4)$ into components parallel and perpendicular to $v=(1,2)$. Check
$$u=u_{\parallel}+u_{\perp},\qquad u_{\perp}\cdot v=0.$$
Explain why these are two independent checks of correctness.

## Theoretical Background and Concepts

1. **Orthogonal Decomposition Theorem:** Given any vector $u$ and any non-zero reference direction vector $v \neq \mathbf{0}$, $u$ can be decomposed **uniquely** as the sum of two orthogonal vectors:
   $$u = u_{\parallel} + u_{\perp},$$
   where:
   - $u_{\parallel}$ (the **parallel component**) is a scalar multiple of $v$ ($u_{\parallel} = \lambda v$), given by the orthogonal projection of $u$ onto $v$:
     $$u_{\parallel} = \operatorname{proj}_v u = \left(\frac{u \cdot v}{v \cdot v}\right) v = \left(\frac{u \cdot v}{\|v\|^2}\right) v.$$
   - $u_{\perp}$ (the **perpendicular component**) is orthogonal to $v$ ($u_{\perp} \cdot v = 0$), obtained by subtracting the parallel component from $u$:
     $$u_{\perp} = u - u_{\parallel}.$$

2. **Geometric Meaning:** $u_{\parallel}$ and $u_{\perp}$ form the two perpendicular legs of a right-angled triangle whose hypotenuse is $u$, with one leg lying along the line spanned by $v$ and the other perpendicular to it.

## Detailed Step-by-Step Solution

We are given the vectors in $\mathbb{R}^2$:
$$u = (3, 4) \qquad \text{and} \qquad v = (1, 2).$$

### Step 1: Compute the Parallel Component $u_{\parallel}$

The formula for the component of $u$ parallel to $v$ is:
$$u_{\parallel} = \operatorname{proj}_v u = \left(\frac{u \cdot v}{v \cdot v}\right) v.$$

First, we compute the dot product $u \cdot v = u_1 v_1 + u_2 v_2$:
$$\begin{aligned}
u \cdot v &= (3)(1) + (4)(2) \\
          &= 3 + 8 \\
          &= 11.
\end{aligned}$$

Second, we compute $v \cdot v = \|v\|^2 = v_1^2 + v_2^2$:
$$\begin{aligned}
v \cdot v &= 1^2 + 2^2 \\
          &= 1 + 4 \\
          &= 5.
\end{aligned}$$

Substituting $u \cdot v = 11$ and $v \cdot v = 5$ into the projection formula:
$$\begin{aligned}
u_{\parallel} &= \frac{11}{5}(1, 2) \\
              &= \left(\frac{11}{5} \cdot 1,\; \frac{11}{5} \cdot 2\right) \\
              &= \left(\frac{11}{5},\; \frac{22}{5}\right) = (2.2,\; 4.4).
\end{aligned}$$

### Step 2: Compute the Perpendicular Component $u_{\perp}$

Using the subtraction formula $u_{\perp} = u - u_{\parallel}$ and writing $u = (3, 4) = \left(\frac{15}{5}, \frac{20}{5}\right)$ with common denominator $5$:
$$\begin{aligned}
u_{\perp} = u - u_{\parallel} &= (3, 4) - \left(\frac{11}{5},\; \frac{22}{5}\right) \\
                              &= \left(\frac{15}{5} - \frac{11}{5},\; \frac{20}{5} - \frac{22}{5}\right) \\
                              &= \left(\frac{4}{5},\; -\frac{2}{5}\right) = (0.8,\; -0.4).
\end{aligned}$$

### Step 3: Perform the Two Checks

1. **First Check ($u = u_{\parallel} + u_{\perp}$):**
   Adding $u_{\parallel} = \left(\frac{11}{5}, \frac{22}{5}\right)$ and $u_{\perp} = \left(\frac{4}{5}, -\frac{2}{5}\right)$ component by component:
   $$\begin{aligned}
   u_{\parallel} + u_{\perp} &= \left(\frac{11}{5} + \frac{4}{5},\; \frac{22}{5} + \left(-\frac{2}{5}\right)\right) \\
                             &= \left(\frac{15}{5},\; \frac{20}{5}\right) \\
                             &= (3, 4) = u. \quad \checkmark
   \end{aligned}$$

2. **Second Check ($u_{\perp} \cdot v = 0$):**
   Computing the dot product of $u_{\perp} = \left(\frac{4}{5}, -\frac{2}{5}\right)$ and $v = (1, 2)$:
   $$\begin{aligned}
   u_{\perp} \cdot v &= \left(\frac{4}{5}\right)(1) + \left(-\frac{2}{5}\right)(2) \\
                     &= \frac{4}{5} - \frac{4}{5} \\
                     &= 0. \quad \checkmark
   \end{aligned}$$

### Step 4: Explain Why These Are Two Independent Checks of Correctness

The two equations $u = u_{\parallel} + u_{\perp}$ and $u_{\perp} \cdot v = 0$ test **two logically distinct requirements** of the orthogonal decomposition, and neither implies the other:

1. **What $u = u_{\parallel} + u_{\perp}$ checks (and what it misses):**
   This equation checks **additive completeness**—that the two pieces sum back to the original vector $u$ without an arithmetic error during subtraction. However, it says **nothing** about whether $u_{\parallel}$ was projected with the right scalar factor or whether $u_{\perp}$ is perpendicular to $v$.
   - *Counterexample:* Suppose we mistakenly took $u_{\parallel} = 2v = (2, 4)$ and then correctly subtracted $u_{\perp} = u - (2, 4) = (1, 0)$. Then the first check $u_{\parallel} + u_{\perp} = (2, 4) + (1, 0) = (3, 4) = u$ **passes**, even though $u_{\perp} \cdot v = (1)(1) + (0)(2) = 1 \neq 0$ (the decomposition is not orthogonal!).

2. **What $u_{\perp} \cdot v = 0$ checks (and what it misses):**
   This equation checks **orthogonality**—that the vector $u_{\perp}$ is genuinely perpendicular to the direction $v$. However, on its own, it does not guarantee that $u_{\parallel}$ and $u_{\perp}$ add up to $u$.
   - *Counterexample:* Suppose we correctly found $u_{\parallel} = \left(\frac{11}{5}, \frac{22}{5}\right)$, but scaled $u_{\perp}$ by the wrong factor, say $u_{\perp} = (2, -1)$ (or $u_{\perp} = (0, 0)$). Then the second check $u_{\perp} \cdot v = (2)(1) + (-1)(2) = 0$ **passes**, even though $u_{\parallel} + u_{\perp} \neq u$!

Only when **both** checks hold simultaneously (together with $u_{\parallel}$ being a scalar multiple of $v$) are we guaranteed that we have found the unique orthogonal decomposition of $u$.

```
      y ^
    4.4 | . . . . * u_parallel = (11/5, 22/5)
      4 |        / \  u_perp = (4/5, -2/5)
        |       /   v
      3 |      /     * u = (3, 4)
        |     /    /
      2 |    * v = (1,2)
        |   /  /
      1 |  / /
        | //
      0 +----+----+----+----> x
        0    1    2    3
```

## Verification and Consistency Checks

1. **Direct Orthogonality Between $u_{\parallel}$ and $u_{\perp}$:** Since $u_{\parallel} = \frac{11}{5}v$ and $u_{\perp} \perp v$, we must also have $u_{\parallel} \cdot u_{\perp} = 0$:
   $$u_{\parallel} \cdot u_{\perp} = \left(\frac{11}{5}\right)\left(\frac{4}{5}\right) + \left(\frac{22}{5}\right)\left(-\frac{2}{5}\right) = \frac{44}{25} - \frac{44}{25} = 0. \quad \checkmark$$

2. **Pythagorean Theorem Check ($\|u_{\parallel}\|^2 + \|u_{\perp}\|^2 = \|u\|^2$):**
   - $\|u_{\parallel}\|^2 = \left(\frac{11}{5}\right)^2 + \left(\frac{22}{5}\right)^2 = \frac{121}{25} + \frac{484}{25} = \frac{605}{25}.$
   - $\|u_{\perp}\|^2 = \left(\frac{4}{5}\right)^2 + \left(-\frac{2}{5}\right)^2 = \frac{16}{25} + \frac{4}{25} = \frac{20}{25}.$
   - $\|u\|^2 = 3^2 + 4^2 = 9 + 16 = 25.$
   Summing the squared norms of the two orthogonal components:
   $$\|u_{\parallel}\|^2 + \|u_{\perp}\|^2 = \frac{605}{25} + \frac{20}{25} = \frac{625}{25} = 25 = \|u\|^2. \quad \checkmark$$
