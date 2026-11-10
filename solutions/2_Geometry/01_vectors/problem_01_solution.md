# Problem 01 Solution

## Problem Statement
For $u=(2,-1,3)$ and $v=(-1,4,2)$ compute

$$
u+v,\qquad u-v,\qquad 3u-2v.
$$

Then verify that $(u+v)-v=u$, and explain geometrically what adding two vectors means.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Component-wise Vector Addition and Subtraction: For vectors $u = (u_1, u_2, u_3)$ and $v = (v_1, v_2, v_3)$, addition and subtraction are performed entry by entry:

$$
u \pm v = (u_1 \pm v_1, u_2 \pm v_2, u_3 \pm v_3)
$$

- Scalar Multiplication: For scalar $c \in \mathbb{R}$, $c u = (c u_1, c u_2, c u_3)$.
- Geometric Meaning of Addition: Vector addition represents consecutive displacements (the head-to-tail triangle rule) or the main diagonal of the parallelogram spanned by the two vectors.
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **Vector Setup & Formula Selection:**
We are given two vectors in $\mathbb{R}^3$:

$$
u = (2, -1, 3), \qquad v = (-1, 4, 2).
$$

We compute the vector sum $u + v$, the vector difference $u - v$, and the linear combination $3u - 2v$. Then we verify the algebraic identity $(u + v) - v = u$ and provide the geometric interpretation of vector addition.

2. **Intermediate Calculations:**
- **Computation of $u + v$:**
We add corresponding components:

$$
\begin{aligned}
u + v &= (2 + (-1), -1 + 4, 3 + 2) \\
      &= (2 - 1, 3, 5) \\
      &= (1, 3, 5)
\end{aligned}
$$

- **Computation of $u - v$:**
We subtract corresponding components:

$$
\begin{aligned}
u - v &= (2 - (-1), -1 - 4, 3 - 2) \\
      &= (2 + 1, -5, 1) \\
      &= (3, -5, 1)
\end{aligned}
$$

- **Computation of $3u - 2v$:**
First, evaluate the scalar multiples $3u$ and $2v$:

$$
3u = 3(2, -1, 3) = (3 \cdot 2, 3 \cdot (-1), 3 \cdot 3) = (6, -3, 9)
$$

$$
2v = 2(-1, 4, 2) = (2 \cdot (-1), 2 \cdot 4, 2 \cdot 2) = (-2, 8, 4)
$$

Now subtract the components of $2v$ from $3u$:

$$
\begin{aligned}
3u - 2v &= (6 - (-2), -3 - 8, 9 - 4) \\
        &= (6 + 2, -11, 5) \\
        &= (8, -11, 5)
\end{aligned}
$$

- **Verification of $(u + v) - v = u$:**
Substitute the computed vector $u + v = (1, 3, 5)$ and $v = (-1, 4, 2)$:

$$
\begin{aligned}
(u + v) - v &= (1 - (-1), 3 - 4, 5 - 2) \\
            &= (1 + 1, -1, 3) \\
            &= (2, -1, 3)
\end{aligned}
$$

Comparing with $u = (2, -1, 3)$:

$$
(u + v) - v = u.
$$

The identity holds algebraically.

3. **Evaluation & Geometric Explanation:**
**Geometric Meaning of Vector Addition:**
Geometrically, a vector represents a translation or displacement in space having both magnitude and direction.
- **Triangle Rule (Head-to-Tail):** Adding vector $v$ to vector $u$ means placing the tail (initial point) of $v$ at the head (terminal point) of $u$. The sum vector $u + v$ is the net displacement directed from the initial point of $u$ directly to the terminal point of $v$.
- **Parallelogram Law:** When $u$ and $v$ emanate from the same initial origin point, they define adjacent sides of a parallelogram. The sum vector $u + v$ corresponds to the directed main diagonal of this parallelogram starting from the shared origin.
- The identity $(u + v) - v = u$ geometrically illustrates that traveling along displacement $u$, continuing along displacement $v$, and then reversing displacement $v$ returns exactly to the endpoint of displacement $u$.

## Final Answer

$$
u + v = (1, 3, 5), \qquad u - v = (3, -5, 1), \qquad 3u - 2v = (8, -11, 5)
$$

The verification confirms:

$$
(u + v) - v = (2, -1, 3) = u
$$
