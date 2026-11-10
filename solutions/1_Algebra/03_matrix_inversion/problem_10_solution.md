# Problem 10 Solution

## Problem Statement
Given

$$
D=
\begin{pmatrix}
2 & 0 & 0 \\
0 & -3 & 0 \\
0 & 0 & 5 \\
\end{pmatrix},\qquad E=
\begin{pmatrix}
2 & 0 & 0 \\
0 & 0 & 0 \\
0 & 0 & 5 \\
\end{pmatrix}.
$$

Without using Gauss–Jordan elimination, decide which matrix is invertible. For the invertible matrix, give the inverse and check the result by multiplication.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Invertibility of Diagonal Matrices: A diagonal matrix $M = \mathrm{diag}(d_1, d_2, \dots, d_n)$ is invertible if and only if all of its diagonal entries are non-zero ($d_i \neq 0$ for all $i$), which is equivalent to $\det M = \prod d_i \neq 0$.
- Inversion of Diagonal Matrices: The inverse of an invertible diagonal matrix is obtained simply by replacing each diagonal entry with its reciprocal: $M^{-1} = \mathrm{diag}\left(\frac{1}{d_1}, \frac{1}{d_2}, \dots, \frac{1}{d_n}\right)$.
- Non-Invertibility via Zero Rows: A matrix containing a row of all zeros has determinant zero and cannot be invertible.
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **Invertibility Check:**
We analyze the determinant of both diagonal matrices without using Gauss-Jordan elimination.
The determinant of a diagonal matrix is the product of its diagonal entries.

For matrix $D$:

$$
D =
\begin{pmatrix}
2 & 0 & 0 \\
0 & -3 & 0 \\
0 & 0 & 5 \\
\end{pmatrix}.
$$

The diagonal entries are $d_{11} = 2$, $d_{22} = -3$, and $d_{33} = 5$.
Computing the determinant:

$$
\begin{aligned}
\det D &= d_{11} \cdot d_{22} \cdot d_{33} \\
       &= (2)(-3)(5) \\
       &= -30
\end{aligned}
$$

Since $\det D = -30 \neq 0$ and all diagonal entries are non-zero ($2 \neq 0, -3 \neq 0, 5 \neq 0$), matrix $D$ is invertible.

For matrix $E$:

$$
E =
\begin{pmatrix}
2 & 0 & 0 \\
0 & 0 & 0 \\
0 & 0 & 5 \\
\end{pmatrix}.
$$

The diagonal entries are $e_{11} = 2$, $e_{22} = 0$, and $e_{33} = 5$.
Computing the determinant:

$$
\begin{aligned}
\det E &= e_{11} \cdot e_{22} \cdot e_{33} \\
       &= (2)(0)(5) \\
       &= 0
\end{aligned}
$$

Since $\det E = 0$ (and its second row consists entirely of zeros), matrix $E$ is singular and not invertible.

2. **Intermediate Steps:**
For the invertible diagonal matrix $D$, the inverse matrix $D^{-1}$ is formed by taking the reciprocal of each main diagonal entry while keeping all off-diagonal entries equal to zero:

$$
D^{-1} =
\begin{pmatrix}
\frac{1}{d_{11}} & 0 & 0 \\
0 & \frac{1}{d_{22}} & 0 \\
0 & 0 & \frac{1}{d_{33}} \\
\end{pmatrix}.
$$

Computing each reciprocal:
- First diagonal entry: $\frac{1}{2}$
- Second diagonal entry: $\frac{1}{-3} = -\frac{1}{3}$
- Third diagonal entry: $\frac{1}{5}$

Assembling the inverse matrix:

$$
D^{-1} =
\begin{pmatrix}
\frac{1}{2} & 0 & 0 \\
0 & -\frac{1}{3} & 0 \\
0 & 0 & \frac{1}{5} \\
\end{pmatrix}.
$$

3. **Verification:**
We check the result by computing the product $D \cdot D^{-1}$:

$$
D \cdot D^{-1} =
\begin{pmatrix}
2 & 0 & 0 \\
0 & -3 & 0 \\
0 & 0 & 5 \\
\end{pmatrix}
\begin{pmatrix}
\frac{1}{2} & 0 & 0 \\
0 & -\frac{1}{3} & 0 \\
0 & 0 & \frac{1}{5} \\
\end{pmatrix}.
$$

Evaluating the product:
- Entry $(1,1)$: $(2)\left(\frac{1}{2}\right) = 1$
- Entry $(2,2)$: $(-3)\left(-\frac{1}{3}\right) = 1$
- Entry $(3,3)$: $(5)\left(\frac{1}{5}\right) = 1$
- All off-diagonal entries are sums of products involving zeros, so they evaluate to $0$.

Assembling the product matrix:

$$
D \cdot D^{-1} =
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1 \\
\end{pmatrix}
= I_3.
$$

The result confirms that $D^{-1}$ is the exact inverse of $D$.

## Final Answer

Matrix $D$ is invertible, while matrix $E$ is not invertible.

$$
D^{-1} =
\begin{pmatrix}
\frac{1}{2} & 0 & 0 \\
0 & -\frac{1}{3} & 0 \\
0 & 0 & \frac{1}{5} \\
\end{pmatrix}
$$
