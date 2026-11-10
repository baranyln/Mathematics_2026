# Problem 12 Solution

## Problem Statement
It is known that

$$
A^{-1}=
\begin{pmatrix}
2 & -1 \\
-3 & 2 \\
\end{pmatrix}.
$$

Without finding $A$, compute $(3A)^{-1}$, $(A^T)^{-1}$, and $(A^2)^{-1}$. Justify each result using the appropriate property.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Inverse of Scalar Multiple: For any non-zero scalar $c$ and invertible matrix $A$, $(cA)^{-1} = \frac{1}{c} A^{-1}$.
- Inverse of Transpose: The operations of inversion and transposition commute: $(A^T)^{-1} = (A^{-1})^T$.
- Inverse of Matrix Power: For any positive integer $k$, $(A^k)^{-1} = (A^{-1})^k$. In particular for $k = 2$, $(A^2)^{-1} = (A^{-1})^2$.
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **Invertibility Check:**
We compute the determinant of the given inverse matrix $A^{-1}$:

$$
A^{-1} =
\begin{pmatrix}
2 & -1 \\
-3 & 2 \\
\end{pmatrix}.
$$

Applying the $2 \times 2$ determinant formula:

$$
\begin{aligned}
\det\left(A^{-1}\right) &= (2)(2) - (-1)(-3) \\
                       &= 4 - 3 \\
                       &= 1
\end{aligned}
$$

Because $\det(A^{-1}) = 1 \neq 0$, the inverse matrix is non-singular.
Using the reciprocal determinant property:

$$
\det A = \frac{1}{\det(A^{-1})} = \frac{1}{1} = 1 \neq 0
$$

Thus, matrix $A$ is invertible, which ensures that all requested inverses $(3A)^{-1}$, $(A^T)^{-1}$, and $(A^2)^{-1}$ exist.

2. **Intermediate Steps:**
**Part 1: Computation of $(3A)^{-1}$**
- *Applicable Property:* For any scalar $c \neq 0$:

$$
(cA)^{-1} = \frac{1}{c} A^{-1}
$$

- Substituting $c = 3$ and the matrix $A^{-1}$:

$$
(3A)^{-1} = \frac{1}{3}
\begin{pmatrix}
2 & -1 \\
-3 & 2 \\
\end{pmatrix} =
\begin{pmatrix}
\frac{2}{3} & -\frac{1}{3} \\
-\frac{3}{3} & \frac{2}{3} \\
\end{pmatrix} =
\begin{pmatrix}
\frac{2}{3} & -\frac{1}{3} \\
-1 & \frac{2}{3} \\
\end{pmatrix}.
$$

**Part 2: Computation of $(A^T)^{-1}$**
- *Applicable Property:* Transposition and inversion commute:

$$
(A^T)^{-1} = (A^{-1})^T
$$

- Transposing matrix $A^{-1}$ (interchanging rows and columns):

$$
(A^{-1})^T =
\begin{pmatrix}
2 & -1 \\
-3 & 2 \\
\end{pmatrix}^T =
\begin{pmatrix}
2 & -3 \\
-1 & 2 \\
\end{pmatrix}.
$$

Thus:

$$
(A^T)^{-1} =
\begin{pmatrix}
2 & -3 \\
-1 & 2 \\
\end{pmatrix}.
$$

**Part 3: Computation of $(A^2)^{-1}$**
- *Applicable Property:* Inversion of matrix powers:

$$
(A^2)^{-1} = (A \cdot A)^{-1} = A^{-1} \cdot A^{-1} = (A^{-1})^2
$$

- Evaluating the matrix product $A^{-1} \cdot A^{-1}$:

$$
(A^{-1})^2 =
\begin{pmatrix}
2 & -1 \\
-3 & 2 \\
\end{pmatrix}
\begin{pmatrix}
2 & -1 \\
-3 & 2 \\
\end{pmatrix}.
$$

Evaluating each entry:
- Entry $(1,1)$: $(2)(2) + (-1)(-3) = 4 + 3 = 7$
- Entry $(1,2)$: $(2)(-1) + (-1)(2) = -2 - 2 = -4$
- Entry $(2,1)$: $(-3)(2) + (2)(-3) = -6 - 6 = -12$
- Entry $(2,2)$: $(-3)(-1) + (2)(2) = 3 + 4 = 7$

Assembling the matrix:

$$
(A^2)^{-1} =
\begin{pmatrix}
7 & -4 \\
-12 & 7 \\
\end{pmatrix}.
$$

3. **Verification:**
We verify each identity using matrix algebra definitions:
- For $(3A)^{-1}$:

$$
(3A)\left[\frac{1}{3}A^{-1}\right] = \left(3 \cdot \frac{1}{3}\right)(A A^{-1}) = 1 \cdot I_2 = I_2.
$$

- For $(A^T)^{-1}$:

$$
A^T (A^{-1})^T = (A^{-1} A)^T = (I_2)^T = I_2.
$$

- For $(A^2)^{-1}$:

$$
A^2 (A^{-1})^2 = (A \cdot A)(A^{-1} \cdot A^{-1}) = A (A A^{-1}) A^{-1} = A (I_2) A^{-1} = A A^{-1} = I_2.
$$

All three results are verified.

## Final Answer

$$
(3A)^{-1} =
\begin{pmatrix}
\frac{2}{3} & -\frac{1}{3} \\
-1 & \frac{2}{3} \\
\end{pmatrix}, \qquad (A^T)^{-1} =
\begin{pmatrix}
2 & -3 \\
-1 & 2 \\
\end{pmatrix}, \qquad (A^2)^{-1} =
\begin{pmatrix}
7 & -4 \\
-12 & 7 \\
\end{pmatrix}
$$
