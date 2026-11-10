# Problem 09 Solution

## Problem Statement
For $u=(1,2,0)$ and $v=(0,1,3)$ compute $u\times v$. Use dot products to check perpendicularity to both vectors, compute $v\times u$, and compare the results.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Vector Cross Product in $\mathbb{R}^3$: For vectors $u = (u_1, u_2, u_3)$ and $v = (v_1, v_2, v_3)$, the cross product $u \times v$ produces a vector orthogonal to both $u$ and $v$, defined component-wise by:

$$
u \times v = (u_2 v_3 - u_3 v_2, \; u_3 v_1 - u_1 v_3, \; u_1 v_2 - u_2 v_1)
$$

- Orthogonality Verification: A vector is orthogonal to two given vectors if its dot product with each vector is strictly zero:

$$
(u \times v) \cdot u = 0, \qquad (u \times v) \cdot v = 0
$$

- Anti-commutativity Property: The vector cross product is alternating (anti-commutative):

$$
v \times u = -(u \times v)
$$

- Formatting Standards: Display equations enclosed in `$$` on separate lines, no `\text` macros, and all multiplication and subtraction steps written explicitly.

## Detailed Step-by-Step Solution
1. **Vector Setup & Formula Selection:**
We are given two vectors in $\mathbb{R}^3$:

$$
u = (1, 2, 0), \qquad v = (0, 1, 3)
$$

We will compute the cross product $u \times v$ using the standard component formula, verify orthogonality to both original vectors via scalar dot products, calculate $v \times u$, and analyze the geometric relationship between $u \times v$ and $v \times u$.

2. **Intermediate Calculations:**
- **Step 1: Compute $u \times v$:**
Apply the component formulas for $u \times v$:

$$
\begin{aligned}
(u \times v)_1 &= u_2 v_3 - u_3 v_2 = (2)(3) - (0)(1) = 6 - 0 = 6 \\
(u \times v)_2 &= u_3 v_1 - u_1 v_3 = (0)(0) - (1)(3) = 0 - 3 = -3 \\
(u \times v)_3 &= u_1 v_2 - u_2 v_1 = (1)(1) - (2)(0) = 1 - 0 = 1
\end{aligned}
$$

Assembling the vector components:

$$
u \times v = (6, -3, 1)
$$

- **Step 2: Check perpendicularity to $u$ and $v$ using dot products:**
Compute the dot product with $u = (1, 2, 0)$:

$$
\begin{aligned}
(u \times v) \cdot u &= (6, -3, 1) \cdot (1, 2, 0) \\
                     &= (6)(1) + (-3)(2) + (1)(0) \\
                     &= 6 - 6 + 0 \\
                     &= 0
\end{aligned}
$$

Compute the dot product with $v = (0, 1, 3)$:

$$
\begin{aligned}
(u \times v) \cdot v &= (6, -3, 1) \cdot (0, 1, 3) \\
                     &= (6)(0) + (-3)(1) + (1)(3) \\
                     &= 0 - 3 + 3 \\
                     &= 0
\end{aligned}
$$

Both inner products vanish identically, confirming that $u \times v$ is perpendicular to both $u$ and $v$.

- **Step 3: Compute $v \times u$:**
Apply the cross product formula with the arguments swapped:

$$
\begin{aligned}
(v \times u)_1 &= v_2 u_3 - v_3 u_2 = (1)(0) - (3)(2) = 0 - 6 = -6 \\
(v \times u)_2 &= v_3 u_1 - v_1 u_3 = (3)(1) - (0)(0) = 3 - 0 = 3 \\
(v \times u)_3 &= v_1 u_2 - v_2 u_1 = (0)(2) - (1)(1) = 0 - 1 = -1
\end{aligned}
$$

Assembling the vector components:

$$
v \times u = (-6, 3, -1)
$$

3. **Evaluation & Comparison:**
- **Comparison of $u \times v$ and $v \times u$:**
Comparing the two vectors:

$$
v \times u = (-6, 3, -1) = -(6, -3, 1) = -(u \times v)
$$

- **Geometric Interpretation:**
1. **Magnitude:** Both vectors have identical lengths:

$$
\|u \times v\| = \sqrt{6^2 + (-3)^2 + 1^2} = \sqrt{36 + 9 + 1} = \sqrt{46}
$$

$$
\|v \times u\| = \sqrt{(-6)^2 + 3^2 + (-1)^2} = \sqrt{36 + 9 + 1} = \sqrt{46}
$$

This magnitude equals the area of the parallelogram spanned by $u$ and $v$.
2. **Direction:** Both vectors lie along the same perpendicular line (normal to the plane containing $u$ and $v$).
3. **Orientation:** Reversing the order of arguments reverses the orientation by $180^\circ$ according to the right-hand rule. Thus, the cross product is strictly anti-commutative.

## Final Answer

$$
u \times v = (6, -3, 1)
$$

$$
(u \times v) \cdot u = 0, \qquad (u \times v) \cdot v = 0
$$

$$
v \times u = (-6, 3, -1) = -(u \times v)
$$
