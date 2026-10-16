# Problem 1: Vector Operations and Their Meaning

## Problem Statement

For $u=(2,-1,3)$ and $v=(-1,4,2)$ compute
$$u+v,\qquad u-v,\qquad 3u-2v.$$
Then verify that $(u+v)-v=u$, and explain geometrically what adding two vectors means.

## Theoretical Background and Concepts

A **vector** in three-dimensional Euclidean space $\mathbb{R}^3$ is an ordered triple of real numbers $u = (u_1, u_2, u_3)$ that represents a directed displacement—a quantity possessing both **magnitude** (length) and **direction** (orientation in space). The numbers $u_1, u_2, u_3$ are called the **components** (or coordinates) of the vector along the $x$-, $y$-, and $z$-axes, respectively.

The fundamental algebraic operations on vectors in $\mathbb{R}^3$ are performed **component-by-component**:

1. **Vector Addition:** Given $u = (u_1, u_2, u_3)$ and $v = (v_1, v_2, v_3)$, their sum is obtained by adding corresponding components:
   $$u + v = (u_1 + v_1,\; u_2 + v_2,\; u_3 + v_3).$$
2. **Scalar Multiplication:** Given a real number (scalar) $c \in \mathbb{R}$ and a vector $u = (u_1, u_2, u_3)$, multiplying $u$ by $c$ scales every component by $c$:
   $$cu = (cu_1,\; cu_2,\; cu_3).$$
   Geometrically, if $c > 0$, $cu$ points in the same direction as $u$ with length multiplied by $c$; if $c < 0$, $cu$ reverses orientation and scales the length by $|c|$. In particular, $-v = (-1)v = (-v_1, -v_2, -v_3)$ is the **opposite vector** of $v$.
3. **Vector Subtraction:** Subtracting $v$ from $u$ is defined as adding the opposite vector $-v$ to $u$:
   $$u - v = u + (-v) = (u_1 - v_1,\; u_2 - v_2,\; u_3 - v_3).$$
4. **Linear Combination:** An expression of the form $au + bv$ (where $a, b \in \mathbb{R}$) combines scalar multiplication and vector addition:
   $$au + bv = (au_1 + bv_1,\; au_2 + bv_2,\; au_3 + bv_3).$$

## Detailed Step-by-Step Solution

We are given the vectors
$$u = (2, -1, 3) \qquad \text{and} \qquad v = (-1, 4, 2).$$

### Step 1: Compute $u + v$

Using the component-wise vector addition formula
$$u + v = (u_1 + v_1,\; u_2 + v_2,\; u_3 + v_3),$$
we substitute the components of $u$ and $v$:
$$\begin{aligned}
u + v &= (2 + (-1),\; -1 + 4,\; 3 + 2) \\
      &= (2 - 1,\; 3,\; 5) \\
      &= (1, 3, 5).
\end{aligned}$$

### Step 2: Compute $u - v$

Using the component-wise vector subtraction formula
$$u - v = (u_1 - v_1,\; u_2 - v_2,\; u_3 - v_3),$$
we substitute the components of $u$ and $v$, taking care with the double negative in the first component:
$$\begin{aligned}
u - v &= (2 - (-1),\; -1 - 4,\; 3 - 2) \\
      &= (2 + 1,\; -5,\; 1) \\
      &= (3, -5, 1).
\end{aligned}$$

### Step 3: Compute $3u - 2v$

To evaluate the linear combination $3u - 2v$, we first apply scalar multiplication to find $3u$ and $2v$ separately, and then subtract corresponding components.

First, scale $u$ by $3$ using $3u = (3u_1, 3u_2, 3u_3)$:
$$\begin{aligned}
3u &= 3(2, -1, 3) \\
   &= (3 \cdot 2,\; 3 \cdot (-1),\; 3 \cdot 3) \\
   &= (6, -3, 9).
\end{aligned}$$

Next, scale $v$ by $2$ using $2v = (2v_1, 2v_2, 2v_3)$:
$$\begin{aligned}
2v &= 2(-1, 4, 2) \\
   &= (2 \cdot (-1),\; 2 \cdot 4,\; 2 \cdot 2) \\
   &= (-2, 8, 4).
\end{aligned}$$

Now subtract $2v$ from $3u$ component by component:
$$\begin{aligned}
3u - 2v &= (6, -3, 9) - (-2, 8, 4) \\
        &= (6 - (-2),\; -3 - 8,\; 9 - 4) \\
        &= (6 + 2,\; -11,\; 5) \\
        &= (8, -11, 5).
\end{aligned}$$

### Step 4: Verify that $(u + v) - v = u$

We take our previously computed sum $u + v = (1, 3, 5)$ and subtract $v = (-1, 4, 2)$ component by component:
$$\begin{aligned}
(u + v) - v &= (1, 3, 5) - (-1, 4, 2) \\
            &= (1 - (-1),\; 3 - 4,\; 5 - 2) \\
            &= (1 + 1,\; -1,\; 3) \\
            &= (2, -1, 3).
\end{aligned}$$
Comparing this with the original vector $u = (2, -1, 3)$, we see that $(u + v) - v = u$ holds identically. Algebraically, this reflects the associativity of vector addition and the additive inverse property:
$$(u + v) - v = u + (v + (-v)) = u + \mathbf{0} = u.$$

### Step 5: Geometric Meaning of Adding Two Vectors

Geometrically, a vector represents a directed displacement (a step of a given length in a given direction). Adding two vectors $u$ and $v$ means **chaining two displacements one after the other**, which can be visualized in two equivalent ways:

1. **The Tip-to-Tail (Triangle) Rule:** Place the tail (initial point) of $v$ at the tip (terminal point) of $u$. If you start at the origin $O$, first move along $u$ to reach point $P$, and from $P$ move along the displacement $v$ to reach point $Q$, then the sum $u + v$ is the single net displacement vector from the starting point $O$ directly to the final point $Q$.
2. **The Parallelogram Rule:** Place both $u$ and $v$ with their tails at the same starting point $O$. Together they form two adjacent sides of a parallelogram; the sum vector $u + v$ is the directed diagonal of this parallelogram starting at $O$.

```
         Tip-to-Tail Rule                     Parallelogram Rule
                 Q                                    P'--------> Q
                / ^                                  /           /
               /   \  v                             /     u+v   /
        u+v   /     \                            u /     /     / u
             /       \                            /   /       /
            /         P                          / /         /
           O ------->                           O --------> R
                u                                     v
```

This geometric picture also explains why $(u + v) - v = u$: starting at $O$, walking along $u$ and then along $v$ brings you to the tip of $u + v$. Subtracting $v$ means adding $-v$, which walks backward along the exact path of $v$, returning you to the tip of $u$.

## Verification and Consistency Checks

1. **Inverse Check for $u - v$:** If $u - v = (3, -5, 1)$ is correct, then adding $v = (-1, 4, 2)$ back to $u - v$ must recover $u$:
   $$(u - v) + v = (3 + (-1),\; -5 + 4,\; 1 + 2) = (2, -1, 3) = u. \quad \checkmark$$

2. **Independent Decomposition Check for $3u - 2v$:** Notice that algebraically $3u - 2v = u + 2(u - v)$. Using $u = (2, -1, 3)$ and our result $u - v = (3, -5, 1)$, we compute:
   $$\begin{aligned}
   u + 2(u - v) &= (2, -1, 3) + 2(3, -5, 1) \\
                &= (2, -1, 3) + (6, -10, 2) \\
                &= (2 + 6,\; -1 - 10,\; 3 + 2) \\
                &= (8, -11, 5) = 3u - 2v. \quad \checkmark
   \end{aligned}$$

3. **Triangle Inequality Check:** The length of the sum of two vectors cannot exceed the sum of their individual lengths ($\|u + v\| \le \|u\| + \|v\|$). Computing the norms:
   $$\|u\| = \sqrt{2^2 + (-1)^2 + 3^2} = \sqrt{4 + 1 + 9} = \sqrt{14} \approx 3.7417,$$
   $$\|v\| = \sqrt{(-1)^2 + 4^2 + 2^2} = \sqrt{1 + 16 + 4} = \sqrt{21} \approx 4.5826,$$
   $$\|u + v\| = \sqrt{1^2 + 3^2 + 5^2} = \sqrt{1 + 9 + 25} = \sqrt{35} \approx 5.9161.$$
   Since $5.9161 \le 3.7417 + 4.5826 = 8.3243$, the triangle inequality is satisfied.
