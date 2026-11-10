# Problem 09 Solution

## Problem Statement
The vectors

$$
u=
\begin{pmatrix}
3 \\
1 \\
\end{pmatrix},\qquad v=
\begin{pmatrix}
1 \\
4 \\
\end{pmatrix}
$$

span a parallelogram. Compute its area using a determinant. Then reverse the order of the vectors and explain what changes in the determinant and what does not change in the area.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Geometric Area and the Determinant: The signed area of the parallelogram spanned by two column vectors $u, v \in \mathbb{R}^2$ is given by the determinant $\det \begin{pmatrix} u & v \end{pmatrix}$. The geometric area is the absolute value of this determinant:

$$
\mathrm{Area} = \left|\det \begin{pmatrix} u & v \end{pmatrix}\right|
$$

- Column Swap and Orientation: Interchanging two columns negates the determinant, corresponding to a change in the orientation of the vector pair, while the absolute area remains invariant.
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **Method Selection & Matrix Setup:**
We are given two vectors in $\mathbb{R}^2$:

$$
u =
\begin{pmatrix}
3 \\
1 \\
\end{pmatrix}, \qquad
v =
\begin{pmatrix}
1 \\
4 \\
\end{pmatrix}.
$$

We form the $2 \times 2$ matrix $M_1$ whose columns are $u$ and $v$ in order:

$$
M_1 =
\begin{pmatrix}
3 & 1 \\
1 & 4 \\
\end{pmatrix}.
$$

When reversing the order of the vectors, we form the matrix $M_2$ with columns $v$ and $u$:

$$
M_2 =
\begin{pmatrix}
1 & 3 \\
4 & 1 \\
\end{pmatrix}.
$$

2. **Intermediate Calculations:**
Setting up the determinant for $M_1$:

$$
\det(M_1) = (3)(4) - (1)(1)
$$

Setting up the determinant for $M_2$:

$$
\det(M_2) = (1)(1) - (3)(4)
$$

3. **Arithmetic Evaluation:**
We evaluate $\det(M_1)$:

$$
\begin{aligned}
\det(M_1) &= (3)(4) - (1)(1) \\
          &= 12 - 1 \\
          &= 11
\end{aligned}
$$

The geometric area of the parallelogram spanned by $u$ and $v$ is:

$$
\mathrm{Area} = |\det(M_1)| = |11| = 11
$$

We evaluate $\det(M_2)$:

$$
\begin{aligned}
\det(M_2) &= (1)(1) - (3)(4) \\
          &= 1 - 12 \\
          &= -11
\end{aligned}
$$

The geometric area computed from $M_2$ is:

$$
\mathrm{Area} = |\det(M_2)| = |-11| = 11
$$

**Explanation of What Changes and What Does Not Change:**
- **What changes:** The determinant changes sign from $+11$ to $-11$. The matrix $M_2$ is obtained from $M_1$ by swapping its two columns. By the alternating property of determinants, swapping two columns multiplies the determinant by $-1$. Geometrically, this sign change corresponds to a reversal of the orientation of the ordered pair: the pair $(u, v)$ is oriented counterclockwise (positive orientation), whereas $(v, u)$ is oriented clockwise (negative orientation).
- **What does not change:** The geometric area does not change. Geometric area is an unsigned magnitude defined as the absolute value of the determinant ($|\det M|$). Since $|11| = |-11| = 11$, the area remains $11$.

## Final Answer

$$
\mathrm{Area} = 11, \qquad \det\begin{pmatrix} u & v \end{pmatrix} = 11, \qquad \det\begin{pmatrix} v & u \end{pmatrix} = -11
$$
