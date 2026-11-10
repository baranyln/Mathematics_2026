# Problem 01 Solution

## Problem Statement
For

$$
A=
\begin{pmatrix}
2 & 1 \\
1 & 1 \\
\end{pmatrix},\qquad B=
\begin{pmatrix}
1 & -1 \\
-1 & 2 \\
\end{pmatrix}
$$

check, without using a formula, whether $B=A^{-1}$. Compute $AB$ and $BA$ and relate the result to the definition of the inverse.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Definition of Matrix Inverse: A square matrix $B$ is the inverse of matrix $A$ if and only if $AB = I$ and $BA = I$, where $I$ is the identity matrix of the same order.
- Invertibility Criterion: A square matrix $A$ possesses an inverse if and only if its determinant is non-zero ($\det A \neq 0$).
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **Invertibility Check:**
We compute the determinant of matrix $A$ to confirm that it is invertible:

$$
A =
\begin{pmatrix}
2 & 1 \\
1 & 1 \\
\end{pmatrix}.
$$

Applying the $2 \times 2$ determinant formula:

$$
\begin{aligned}
\det A &= (a_{11})(a_{22}) - (a_{12})(a_{21}) \\
       &= (2)(1) - (1)(1) \\
       &= 2 - 1 \\
       &= 1
\end{aligned}
$$

Since $\det A = 1 \neq 0$, matrix $A$ is non-singular and its inverse $A^{-1}$ exists.

2. **Intermediate Steps:**
We check whether $B = A^{-1}$ directly by computing both matrix products $AB$ and $BA$ entry by entry without using an explicit inversion formula.

**Computation of $AB$:**

$$
AB =
\begin{pmatrix}
2 & 1 \\
1 & 1 \\
\end{pmatrix}
\begin{pmatrix}
1 & -1 \\
-1 & 2 \\
\end{pmatrix}
$$

We evaluate each entry of the product:
- Entry $(1,1)$: $(2)(1) + (1)(-1) = 2 - 1 = 1$
- Entry $(1,2)$: $(2)(-1) + (1)(2) = -2 + 2 = 0$
- Entry $(2,1)$: $(1)(1) + (1)(-1) = 1 - 1 = 0$
- Entry $(2,2)$: $(1)(-1) + (1)(2) = -1 + 2 = 1$

Assembling the resulting matrix:

$$
AB =
\begin{pmatrix}
1 & 0 \\
0 & 1 \\
\end{pmatrix}
= I_2
$$

**Computation of $BA$:**

$$
BA =
\begin{pmatrix}
1 & -1 \\
-1 & 2 \\
\end{pmatrix}
\begin{pmatrix}
2 & 1 \\
1 & 1 \\
\end{pmatrix}
$$

We evaluate each entry of the product:
- Entry $(1,1)$: $(1)(2) + (-1)(1) = 2 - 1 = 1$
- Entry $(1,2)$: $(1)(1) + (-1)(1) = 1 - 1 = 0$
- Entry $(2,1)$: $(-1)(2) + (2)(1) = -2 + 2 = 0$
- Entry $(2,2)$: $(-1)(1) + (2)(1) = -1 + 2 = 1$

Assembling the resulting matrix:

$$
BA =
\begin{pmatrix}
1 & 0 \\
0 & 1 \\
\end{pmatrix}
= I_2
$$

3. **Verification:**
By definition, for square matrices of the same dimension, $B$ is the two-sided inverse of $A$ if and only if:

$$
AB = BA = I_2
$$

Since our direct calculations show that:

$$
AB = I_2, \qquad BA = I_2
$$

matrix $B$ satisfies the algebraic definition of the inverse matrix, confirming that:

$$
B = A^{-1}
$$

## Final Answer

$$
A^{-1} =
\begin{pmatrix}
1 & -1 \\
-1 & 2 \\
\end{pmatrix}
$$
