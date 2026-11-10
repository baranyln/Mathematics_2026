# Problem 06 Solution

## Problem Statement
Solve

$$
Ax=b,
$$

where

$$
A=
\begin{pmatrix}
2 & 1 \\
1 & 3 \\
\end{pmatrix},\qquad b=
\begin{pmatrix}
5 \\
7 \\
\end{pmatrix},
$$

using $x=A^{-1}b$. Then substitute the resulting vector back into the equation and check the result.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Solving Linear Systems via Matrix Inversion: If $A$ is invertible ($\det A \neq 0$), multiplying the matrix equation $Ax = b$ on the left by $A^{-1}$ yields the unique solution vector $x = A^{-1}b$.
- Formula for $2 \times 2$ Inverse: $A^{-1} = \frac{1}{\det A} \mathrm{adj}(A) = \frac{1}{ad - bc} \begin{pmatrix} d & -b \\ -c & a \\ \end{pmatrix}$.
- Verification: Substituting $x$ into $Ax$ confirms that $Ax = b$.
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **Invertibility Check:**
We compute the determinant of the coefficient matrix $A$:

$$
A =
\begin{pmatrix}
2 & 1 \\
1 & 3 \\
\end{pmatrix}.
$$

Applying the $2 \times 2$ determinant formula:

$$
\begin{aligned}
\det A &= (a_{11})(a_{22}) - (a_{12})(a_{21}) \\
       &= (2)(3) - (1)(1) \\
       &= 6 - 1 \\
       &= 5
\end{aligned}
$$

Since $\det A = 5 \neq 0$, matrix $A$ is invertible, which guarantees a unique solution for any right-hand side vector $b$.

2. **Intermediate Steps:**
We determine $A^{-1}$ using the explicit $2 \times 2$ inverse formula:

$$
A^{-1} = \frac{1}{\det A}
\begin{pmatrix}
d & -b \\
-c & a \\
\end{pmatrix}
= \frac{1}{5}
\begin{pmatrix}
3 & -1 \\
-1 & 2 \\
\end{pmatrix}.
$$

Distributing the scalar:

$$
A^{-1} =
\begin{pmatrix}
\frac{3}{5} & -\frac{1}{5} \\
-\frac{1}{5} & \frac{2}{5} \\
\end{pmatrix}.
$$

Now we compute the solution vector $x = A^{-1}b$:

$$
x = \frac{1}{5}
\begin{pmatrix}
3 & -1 \\
-1 & 2 \\
\end{pmatrix}
\begin{pmatrix}
5 \\
7 \\
\end{pmatrix}.
$$

Evaluating the matrix-vector multiplication entry by entry:
- First component:

$$
(3)(5) + (-1)(7) = 15 - 7 = 8
$$

- Second component:

$$
(-1)(5) + (2)(7) = -5 + 14 = 9
$$

Assembling the vector $x$:

$$
x = \frac{1}{5}
\begin{pmatrix}
8 \\
9 \\
\end{pmatrix} =
\begin{pmatrix}
\frac{8}{5} \\
\frac{9}{5} \\
\end{pmatrix}.
$$

3. **Verification:**
We substitute the vector $x$ back into the original equation $Ax$:

$$
Ax =
\begin{pmatrix}
2 & 1 \\
1 & 3 \\
\end{pmatrix}
\begin{pmatrix}
\frac{8}{5} \\
\frac{9}{5} \\
\end{pmatrix}.
$$

Evaluating each component:
- First component:

$$
2\left(\frac{8}{5}\right) + 1\left(\frac{9}{5}\right) = \frac{16}{5} + \frac{9}{5} = \frac{25}{5} = 5
$$

- Second component:

$$
1\left(\frac{8}{5}\right) + 3\left(\frac{9}{5}\right) = \frac{8}{5} + \frac{27}{5} = \frac{35}{5} = 7
$$

Assembling the resulting vector:

$$
Ax =
\begin{pmatrix}
5 \\
7 \\
\end{pmatrix}
= b.
$$

The result matches the vector $b$ exactly.

## Final Answer

$$
x =
\begin{pmatrix}
\frac{8}{5} \\
\frac{9}{5} \\
\end{pmatrix}, \qquad A^{-1} =
\begin{pmatrix}
\frac{3}{5} & -\frac{1}{5} \\
-\frac{1}{5} & \frac{2}{5} \\
\end{pmatrix}
$$
