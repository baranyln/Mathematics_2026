# Problem 04 Solution

## Problem Statement
For $u=(1,2,-1)$ and $v=(2,-1,3)$ compute $u\cdot v$ and determine whether the vectors are perpendicular. Then find $a$ so that $w=(2,-1,a)$ is perpendicular to $u$, and check the result.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Dot Product (Standard Inner Product in $\mathbb{R}^3$): For two vectors $u = (u_1, u_2, u_3)$ and $v = (v_1, v_2, v_3)$, the dot product is defined as the sum of the products of their corresponding components:

$$
u \cdot v = u_1 v_1 + u_2 v_2 + u_3 v_3
$$

- Orthogonality (Perpendicularity) Criterion: Two non-zero vectors $u$ and $v$ are mutually perpendicular ($u \perp v$) if and only if their dot product vanishes:

$$
u \perp v \iff u \cdot v = 0
$$

- Constructing Orthogonal Vectors: Requiring $u \cdot w = 0$ provides a linear scalar equation that uniquely determines an unknown component.
- Formatting Standards: Display math with `$$` on separate lines, no `\text` macros, and all arithmetic products written explicitly.

## Detailed Step-by-Step Solution
1. **Vector Setup & Formula Selection:**
We are given two vectors in $\mathbb{R}^3$:

$$
u = (1, 2, -1), \qquad v = (2, -1, 3)
$$

We will compute the scalar dot product $u \cdot v$ to evaluate whether $u \perp v$. Then, given the vector $w = (2, -1, a)$ with an undetermined parameter $a \in \mathbb{R}$, we impose the orthogonality condition $u \cdot w = 0$ to solve for $a$, followed by an explicit verification check.

2. **Intermediate Calculations:**
- **Step 1: Compute $u \cdot v$:**
Substitute the components of $u$ and $v$ into the inner product formula:

$$
\begin{aligned}
u \cdot v &= (1)(2) + (2)(-1) + (-1)(3) \\
          &= 2 - 2 - 3 \\
          &= -3
\end{aligned}
$$

- **Step 2: Determine perpendicularity of $u$ and $v$:**
Since the dot product is non-zero:

$$
u \cdot v = -3 \neq 0
$$

the vectors $u$ and $v$ are **not perpendicular**. Furthermore, because $u \cdot v < 0$, the angle between $u$ and $v$ is obtuse.

- **Step 3: Find parameter $a$ such that $w \perp u$:**
We are given $w = (2, -1, a)$. Imposing the orthogonality condition $u \cdot w = 0$:

$$
\begin{aligned}
u \cdot w &= (1)(2) + (2)(-1) + (-1)(a) \\
          &= 2 - 2 - a \\
          &= 0 - a \\
          &= -a
\end{aligned}
$$

Setting the dot product to zero:

$$
-a = 0 \implies a = 0
$$

Thus, the vector is $w = (2, -1, 0)$.

- **Step 4: Check the result:**
Substitute $a = 0$ into $w$ and recompute $u \cdot w$:

$$
\begin{aligned}
u \cdot w &= (1, 2, -1) \cdot (2, -1, 0) \\
          &= (1)(2) + (2)(-1) + (-1)(0) \\
          &= 2 - 2 + 0 \\
          &= 0
\end{aligned}
$$

3. **Evaluation:**
- The dot product $u \cdot v = -3$ establishes that $u$ and $v$ are not orthogonal.
- Solving the linear equation $u \cdot w = 0$ yields uniquely $a = 0$.
- The verification confirms that $w = (2, -1, 0)$ is strictly perpendicular to $u = (1, 2, -1)$.

## Final Answer

$$
u \cdot v = -3
$$

Since $u \cdot v \neq 0$, the vectors $u$ and $v$ are not perpendicular.

$$
a = 0
$$

The perpendicular vector is:

$$
w = (2, -1, 0)
$$

with verification:

$$
u \cdot w = 0
$$
