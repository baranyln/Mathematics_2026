# Problem 03 Solution

## Problem Statement
For

$$
A=
\begin{pmatrix}
2 & 4 \\
1 & 2 \\
\end{pmatrix}
$$

explain in two ways why $A^{-1}$ does not exist: using the determinant and using dependence between the rows.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Determinant Criterion for Invertibility: A square matrix $A$ is invertible if and only if $\det A \neq 0$. If $\det A = 0$, the matrix is singular and has no inverse.
- Linear Dependence of Rows: A matrix is invertible if and only if its row vectors are linearly independent. If one row is a scalar multiple of another, the matrix rank is strictly less than its dimension ($n$), preventing row reduction to the identity matrix.
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **Invertibility Check:**
We compute the determinant of the matrix:

$$
A =
\begin{pmatrix}
2 & 4 \\
1 & 2 \\
\end{pmatrix}.
$$

Applying the $2 \times 2$ determinant formula:

$$
\begin{aligned}
\det A &= (a_{11})(a_{22}) - (a_{12})(a_{21}) \\
       &= (2)(2) - (4)(1) \\
       &= 4 - 4 \\
       &= 0
\end{aligned}
$$

**Explanation via Way 1 (The Determinant Criterion):**
By the multiplicative property of determinants, if an inverse matrix $A^{-1}$ existed, then:

$$
A \cdot A^{-1} = I_2 \implies \det(A \cdot A^{-1}) = \det(I_2)
$$

$$
\det(A) \cdot \det\left(A^{-1}\right) = 1
$$

Substituting $\det A = 0$:

$$
0 \cdot \det\left(A^{-1}\right) = 1 \implies 0 = 1
$$

This contradiction proves that no such matrix $A^{-1}$ can exist. A determinant of zero indicates that the area scaling factor of the linear mapping is zero, collapsing two-dimensional space onto a line.

2. **Intermediate Steps:**
**Explanation via Way 2 (Dependence Between the Rows):**
We express the matrix in terms of its two row vectors in $\mathbb{R}^2$:

$$
R_1 =
\begin{pmatrix}
2 & 4 \\
\end{pmatrix}, \qquad
R_2 =
\begin{pmatrix}
1 & 2 \\
\end{pmatrix}.
$$

We compare the components of $R_1$ and $R_2$:

$$
\begin{aligned}
r_{11} &= 2 = 2 \cdot 1 = 2 \cdot r_{21} \\
r_{12} &= 4 = 2 \cdot 2 = 2 \cdot r_{22}
\end{aligned}
$$

Thus, Row 1 is an exact scalar multiple of Row 2:

$$
R_1 = 2 R_2
$$

Equivalently, this non-trivial linear combination produces the zero vector:

$$
R_1 - 2 R_2 =
\begin{pmatrix}
0 & 0 \\
\end{pmatrix}.
$$

When performing Gauss-Jordan elimination on the augmented matrix $[A \mid I]$:

$$
\begin{pmatrix}
2 & 4 & \mid & 1 & 0 \\
1 & 2 & \mid & 0 & 1 \\
\end{pmatrix}.
$$

Applying the row operation $R_1 \leftarrow R_1 - 2R_2$:

$$
\begin{pmatrix}
0 & 0 & \mid & 1 & -2 \\
1 & 2 & \mid & 0 & 1 \\
\end{pmatrix}.
$$

The first row on the left is entirely zero, which means the left-hand side can never be reduced to the identity matrix $I_2$. Hence, the rank of $A$ is $1 < 2$, and the matrix is singular.

3. **Verification:**
To demonstrate why no matrix $B = \begin{pmatrix} x & y \\ z & w \\ \end{pmatrix}$ can satisfy $AB = I_2$, we compute the product $AB$:

$$
AB =
\begin{pmatrix}
2 & 4 \\
1 & 2 \\
\end{pmatrix}
\begin{pmatrix}
x & y \\
z & w \\
\end{pmatrix} =
\begin{pmatrix}
2x + 4z & 2y + 4w \\
x + 2z & y + 2w \\
\end{pmatrix}.
$$

Notice that the first row of $AB$ is strictly twice the second row:

$$
\begin{pmatrix}
2x + 4z & 2y + 4w \\
\end{pmatrix}
= 2
\begin{pmatrix}
x + 2z & y + 2w \\
\end{pmatrix}.
$$

For $AB = I_2 = \begin{pmatrix} 1 & 0 \\ 0 & 1 \\ \end{pmatrix}$, the first row must be $\begin{pmatrix} 1 & 0 \end{pmatrix}$ and the second row must be $\begin{pmatrix} 0 & 1 \end{pmatrix}$.
However:

$$
\begin{pmatrix} 1 & 0 \end{pmatrix} \neq 2 \begin{pmatrix} 0 & 1 \end{pmatrix} = \begin{pmatrix} 0 & 2 \end{pmatrix}.
$$

This contradiction confirms that no choice of entries for $B$ can produce the identity matrix.

## Final Answer

The matrix inverse $A^{-1}$ does not exist.

The inverse $A^{-1}$ does not exist because $\det A = 0$ (determinant criterion) and the rows of $A$ are linearly dependent via $R_1 = 2R_2$ (row dependence criterion).
