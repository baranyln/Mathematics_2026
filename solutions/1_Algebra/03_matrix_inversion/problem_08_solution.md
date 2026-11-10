# Problem 08 Solution

## Problem Statement
The matrix

$$
S=
\begin{pmatrix}
2 & 0 \\
0 & \frac12 \\
\end{pmatrix}
$$

describes a scaling of the plane. Find $S^{-1}$ and explain geometrically what the inverse transformation does. Check the action of the pair $S,S^{-1}$ on one simple vector.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Inverse of a Diagonal Matrix: For an invertible diagonal matrix $D = \mathrm{diag}(d_1, d_2, \dots, d_n)$, the inverse is obtained by taking the reciprocal of each non-zero diagonal entry: $D^{-1} = \mathrm{diag}\left(\frac{1}{d_1}, \frac{1}{d_2}, \dots, \frac{1}{d_n}\right)$.
- Geometric Transformation Interpretation: Matrix inversion geometrically corresponds to reversing the directional scaling: scaling by factor $k$ is inverted by scaling by factor $\frac{1}{k}$.
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **Invertibility Check:**
We compute the determinant of the diagonal matrix $S$:

$$
S =
\begin{pmatrix}
2 & 0 \\
0 & \frac{1}{2} \\
\end{pmatrix}.
$$

Applying the determinant formula:

$$
\begin{aligned}
\det S &= (s_{11})(s_{22}) - (s_{12})(s_{21}) \\
       &= (2)\left(\frac{1}{2}\right) - (0)(0) \\
       &= 1 - 0 \\
       &= 1
\end{aligned}
$$

Since $\det S = 1 \neq 0$, the scaling matrix $S$ is non-singular and invertible.

2. **Intermediate Steps:**
For a $2 \times 2$ diagonal matrix $D = \begin{pmatrix} d_1 & 0 \\ 0 & d_2 \\ \end{pmatrix}$, the inverse is given by:

$$
D^{-1} =
\begin{pmatrix}
\frac{1}{d_1} & 0 \\
0 & \frac{1}{d_2} \\
\end{pmatrix}.
$$

Here, $d_1 = 2$ and $d_2 = \frac{1}{2}$. We evaluate each reciprocal:

$$
\frac{1}{d_1} = \frac{1}{2}
$$

$$
\frac{1}{d_2} = \frac{1}{1/2} = 2
$$

Thus, the inverse matrix is:

$$
S^{-1} =
\begin{pmatrix}
\frac{1}{2} & 0 \\
0 & 2 \\
\end{pmatrix}.
$$

**Geometric Explanation of the Inverse Transformation:**
- The forward matrix $S$ scales the horizontal coordinate ($x$-direction) by a factor of $2$ (a horizontal expansion / stretching) and scales the vertical coordinate ($y$-direction) by a factor of $\frac{1}{2}$ (a vertical compression).
- The inverse matrix $S^{-1}$ performs the exact undoing of this transformation: it compresses the horizontal coordinate by a factor of $\frac{1}{2}$ and expands the vertical coordinate by a factor of $2$.
- Consequently, applying $S^{-1}$ after $S$ restores the original coordinates and shape of every geometric figure in the plane.

3. **Verification:**
We test the forward and inverse transformations on the test vector:

$$
v =
\begin{pmatrix}
4 \\
6 \\
\end{pmatrix}.
$$

Applying the forward transformation $S$:

$$
w = Sv =
\begin{pmatrix}
2 & 0 \\
0 & \frac{1}{2} \\
\end{pmatrix}
\begin{pmatrix}
4 \\
6 \\
\end{pmatrix} =
\begin{pmatrix}
(2)(4) + (0)(6) \\
(0)(4) + \left(\frac{1}{2}\right)(6) \\
\end{pmatrix} =
\begin{pmatrix}
8 \\
3 \\
\end{pmatrix}.
$$

Applying the inverse transformation $S^{-1}$ to the result $w$:

$$
S^{-1}w =
\begin{pmatrix}
\frac{1}{2} & 0 \\
0 & 2 \\
\end{pmatrix}
\begin{pmatrix}
8 \\
3 \\
\end{pmatrix} =
\begin{pmatrix}
\left(\frac{1}{2}\right)(8) + (0)(3) \\
(0)(8) + (2)(3) \\
\end{pmatrix} =
\begin{pmatrix}
4 \\
6 \\
\end{pmatrix}
= v.
$$

We also verify the matrix product $S \cdot S^{-1}$:

$$
S \cdot S^{-1} =
\begin{pmatrix}
2 & 0 \\
0 & \frac{1}{2} \\
\end{pmatrix}
\begin{pmatrix}
\frac{1}{2} & 0 \\
0 & 2 \\
\end{pmatrix} =
\begin{pmatrix}
2\left(\frac{1}{2}\right) & 0 \\
0 & \left(\frac{1}{2}\right)(2) \\
\end{pmatrix} =
\begin{pmatrix}
1 & 0 \\
0 & 1 \\
\end{pmatrix}
= I_2.
$$

The action of the inverse transformation is completely verified.

## Final Answer

$$
S^{-1} =
\begin{pmatrix}
\frac{1}{2} & 0 \\
0 & 2 \\
\end{pmatrix}
$$
