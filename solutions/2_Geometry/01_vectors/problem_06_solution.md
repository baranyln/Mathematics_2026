# Problem 06 Solution

## Problem Statement
Find the projection of $u=(4,2)$ onto the direction $v=(1,1)$. Then compute

$$
r=u-\mathrm{proj}_v\,u
$$

and verify that $r\cdot v=0$. Explain this result geometrically.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Orthogonal Vector Projection: The vector projection of vector $u$ onto a non-zero direction vector $v$ is given by:

$$
\mathrm{proj}_v\,u = \frac{u \cdot v}{v \cdot v} v = \frac{u \cdot v}{\|v\|^2} v
$$

(As specified in Section 7 of `hints.md`, use `\mathrm{proj}_v\,u` rather than `\operatorname{proj}`).
- Perpendicular Component (Residual Vector): The vector difference between $u$ and its projection is:

$$
r = u - \mathrm{proj}_v\,u
$$

- Orthogonality Verification: The residual vector $r$ is orthogonal to the direction vector $v$:

$$
r \cdot v = 0
$$

- Geometric Decomposition: Resolving $u$ into $u = \mathrm{proj}_v\,u + r$ represents the orthogonal decomposition of $u$ into a component parallel to $v$ and a component perpendicular to $v$.
- Formatting Standards: Display equations enclosed in `$$` on independent lines with proper vertical spacing and no `\text` macros.

## Detailed Step-by-Step Solution
1. **Vector Setup & Formula Selection:**
We are given two vectors in the Euclidean plane $\mathbb{R}^2$:

$$
u = (4, 2), \qquad v = (1, 1)
$$

We will compute the scalar dot products $u \cdot v$ and $v \cdot v$, evaluate the projection vector $\mathrm{proj}_v\,u$, calculate the perpendicular residual vector $r = u - \mathrm{proj}_v\,u$, verify the orthogonality condition $r \cdot v = 0$, and interpret the geometric significance.

2. **Intermediate Calculations:**
- **Step 1: Compute scalar dot products $u \cdot v$ and $v \cdot v$:**
For $u \cdot v$:

$$
\begin{aligned}
u \cdot v &= (4)(1) + (2)(1) \\
          &= 4 + 2 \\
          &= 6
\end{aligned}
$$

For $v \cdot v = \|v\|^2$:

$$
\begin{aligned}
v \cdot v &= (1)(1) + (1)(1) \\
          &= 1 + 1 \\
          &= 2
\end{aligned}
$$

- **Step 2: Compute the projection vector $\mathrm{proj}_v\,u$:**
Multiply the direction vector $v$ by the projection scalar $\frac{u \cdot v}{v \cdot v} = \frac{6}{2} = 3$:

$$
\begin{aligned}
\mathrm{proj}_v\,u &= \frac{u \cdot v}{v \cdot v} v \\
                   &= \frac{6}{2} (1, 1) \\
                   &= 3 (1, 1) \\
                   &= (3 \cdot 1, 3 \cdot 1) \\
                   &= (3, 3)
\end{aligned}
$$

- **Step 3: Compute the residual vector $r = u - \mathrm{proj}_v\,u$:**
Subtract the components of $\mathrm{proj}_v\,u$ from $u$:

$$
\begin{aligned}
r &= u - \mathrm{proj}_v\,u \\
  &= (4, 2) - (3, 3) \\
  &= (4 - 3, 2 - 3) \\
  &= (1, -1)
\end{aligned}
$$

- **Step 4: Verify that $r \cdot v = 0$:**
Compute the dot product between $r$ and $v$:

$$
\begin{aligned}
r \cdot v &= (1, -1) \cdot (1, 1) \\
          &= (1)(1) + (-1)(1) \\
          &= 1 - 1 \\
          &= 0
\end{aligned}
$$

The identity $r \cdot v = 0$ is strictly verified.

3. **Evaluation & Geometric Explanation:**
- **Geometric Decomposition:**
The equation:

$$
u = \mathrm{proj}_v\,u + r = (3, 3) + (1, -1) = (4, 2)
$$

decomposes vector $u$ into two mutually perpendicular geometric components:
1. **Parallel component ($\mathrm{proj}_v\,u$):** The vector $(3, 3)$ lies directly along the line spanned by $v = (1, 1)$. It represents the "shadow" cast orthogonally by $u$ onto the line of $v$.
2. **Perpendicular component ($r$):** The vector $(1, -1)$ is strictly orthogonal to $v$ ($r \cdot v = 0$). It represents the perpendicular displacement from the line of $v$ to the tip of vector $u$.

Together, $\mathrm{proj}_v\,u$, $r$, and $u$ form a right-angled triangle in $\mathbb{R}^2$ with $u$ as the hypotenuse, satisfying the Pythagorean relation:

$$
\|\mathrm{proj}_v\,u\|^2 + \|r\|^2 = (3^2 + 3^2) + (1^2 + (-1)^2) = 18 + 2 = 20 = \|u\|^2
$$

where $\|u\|^2 = 4^2 + 2^2 = 20$.

## Final Answer

$$
\mathrm{proj}_v\,u = (3, 3)
$$

$$
r = u - \mathrm{proj}_v\,u = (1, -1)
$$

$$
r \cdot v = (1)(1) + (-1)(1) = 0
$$
