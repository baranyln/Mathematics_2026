# Problem 06 Solution

## Problem Statement
For

$$
A(t)=
\begin{pmatrix}
t & 1 \\
2 & t \\
\end{pmatrix}
$$

find all values of $t$ for which the matrix is not invertible. Explain how your answer is related to the determinant being zero.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Determinant of a $2 \times 2$ Parameter Matrix: For $M(t) = \begin{pmatrix} a(t) & b(t) \\ c(t) & d(t) \end{pmatrix}$, the determinant is given by $\det M(t) = a(t)d(t) - b(t)c(t)$.
- Singularity and Non-Invertibility: By the Invertible Matrix Theorem, a square matrix is not invertible (singular) if and only if its determinant is zero.
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **Method Selection & Matrix Setup:**
The matrix depends on the real parameter $t$:

$$
A(t) =
\begin{pmatrix}
t & 1 \\
2 & t \\
\end{pmatrix}.
$$

We first compute the characteristic polynomial representing $\det A(t)$ using the $2 \times 2$ determinant formula, and then find the roots of the equation $\det A(t) = 0$.

2. **Intermediate Calculations:**
We identify the matrix entries:
- Entry $(1,1)$: $a_{11} = t$
- Entry $(1,2)$: $a_{12} = 1$
- Entry $(2,1)$: $a_{21} = 2$
- Entry $(2,2)$: $a_{22} = t$

Setting up the determinant expression:

$$
\det A(t) = (a_{11})(a_{22}) - (a_{12})(a_{21}) = (t)(t) - (1)(2)
$$

Multiplying the terms:

$$
\det A(t) = t^2 - 2
$$

Setting the determinant equal to zero to find values corresponding to non-invertibility:

$$
t^2 - 2 = 0
$$

Factoring the expression as a difference of squares:

$$
(t - \sqrt{2})(t + \sqrt{2}) = 0
$$

3. **Arithmetic Evaluation:**
The roots of the equation are:

$$
\begin{aligned}
t - \sqrt{2} = 0 &\implies t = \sqrt{2} \\
t + \sqrt{2} = 0 &\implies t = -\sqrt{2}
\end{aligned}
$$

**Explanation of Connection to the Determinant Being Zero:**
The determinant of a matrix represents the volume scaling factor of the linear transformation defined by the matrix.
- When $\det A(t) = 0$, the transformation collapses two-dimensional space into a one-dimensional subspace. The nullspace (kernel) contains non-trivial vectors, which means the mapping is not injective.
- At $t = \sqrt{2}$, the second row is a scalar multiple of the first row:

$$
\begin{pmatrix} 2 & \sqrt{2} \\ \end{pmatrix} = \sqrt{2} \begin{pmatrix} \sqrt{2} & 1 \\ \end{pmatrix}
$$

- At $t = -\sqrt{2}$, the second row is also a scalar multiple of the first row:

$$
\begin{pmatrix} 2 & -\sqrt{2} \\ \end{pmatrix} = -\sqrt{2} \begin{pmatrix} -\sqrt{2} & 1 \\ \end{pmatrix}
$$

In both cases, the rows (and columns) are linearly dependent. The rank of $A(t)$ drops to $1 < 2$, making the matrix singular and therefore not invertible.

## Final Answer

$$
\det(A(t)) = t^2 - 2
$$

The matrix $A(t)$ is not invertible for $t = \sqrt{2}$ and $t = -\sqrt{2}$.
