# Problem 01 Solution

## Problem Statement
Compute

$$
\det
\begin{pmatrix}
3 & -2 \\
5 & 4 \\
\end{pmatrix},\qquad \det
\begin{pmatrix}
1 & 7 \\
2 & 14 \\
\end{pmatrix}.
$$

Which matrix is invertible? Justify your answer.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Determinant of a $2 \times 2$ Matrix: For any $2 \times 2$ matrix $M = \begin{pmatrix} a & b \\ c & d \end{pmatrix}$, the determinant is evaluated by the formula $\det(M) = ad - bc$.
- Invertibility Criterion: A square matrix is invertible if and only if its determinant is non-zero ($\det(M) \neq 0$). A matrix with determinant zero is singular and non-invertible.
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **Method Selection & Matrix Setup:**
We define the two given matrices as $A$ and $B$:

$$
A =
\begin{pmatrix}
3 & -2 \\
5 & 4 \\
\end{pmatrix}
$$

and

$$
B =
\begin{pmatrix}
1 & 7 \\
2 & 14 \\
\end{pmatrix}.
$$

Both matrices have size $2 \times 2$. We apply the direct definition of the $2 \times 2$ determinant: the product of the main diagonal entries minus the product of the off-diagonal entries.

2. **Intermediate Calculations:**
For matrix $A$, we identify the entries:
- Row 1, Column 1: $a_{11} = 3$
- Row 1, Column 2: $a_{12} = -2$
- Row 2, Column 1: $a_{21} = 5$
- Row 2, Column 2: $a_{22} = 4$

The intermediate product setup for matrix $A$ is:

$$
\det A = (a_{11})(a_{22}) - (a_{12})(a_{21}) = (3)(4) - (-2)(5)
$$

For matrix $B$, we identify the entries:
- Row 1, Column 1: $b_{11} = 1$
- Row 1, Column 2: $b_{12} = 7$
- Row 2, Column 1: $b_{21} = 2$
- Row 2, Column 2: $b_{22} = 14$

The intermediate product setup for matrix $B$ is:

$$
\det B = (b_{11})(b_{22}) - (b_{12})(b_{21}) = (1)(14) - (7)(2)
$$

3. **Arithmetic Evaluation:**
We compute the arithmetic evaluation for matrix $A$:

$$
\begin{aligned}
\det A &= (3)(4) - (-2)(5) \\
       &= 12 - (-10) \\
       &= 12 + 10 \\
       &= 22
\end{aligned}
$$

We compute the arithmetic evaluation for matrix $B$:

$$
\begin{aligned}
\det B &= (1)(14) - (7)(2) \\
       &= 14 - 14 \\
       &= 0
\end{aligned}
$$

Invertibility justification:
- For matrix $A$: $\det A = 22 \neq 0$. Therefore, matrix $A$ is invertible.
- For matrix $B$: $\det B = 0$. Therefore, matrix $B$ is not invertible. Note that the second row is an exact scalar multiple of the first row ($R_2 = 2R_1$), meaning the rows are linearly dependent.

## Final Answer

$$
\det(A) = 22, \qquad \det(B) = 0
$$

Matrix $A$ is invertible because $\det(A) \neq 0$. Matrix $B$ is not invertible because $\det(B) = 0$.
