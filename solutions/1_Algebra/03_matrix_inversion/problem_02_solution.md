# Problem 02 Solution

## Problem Statement
Find the inverse of

$$
A=
\begin{pmatrix}
3 & 2 \\
5 & 4 \\
\end{pmatrix}
$$

using the formula for a $2\times2$ matrix. At the end, check the result by computing one product with $A$.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Explicit $2 \times 2$ Inverse Formula: For any $2 \times 2$ matrix $M = \begin{pmatrix} a & b \\ c & d \\ \end{pmatrix}$ with $\det M \neq 0$, the inverse is given by:

$$
M^{-1} = \frac{1}{\det M} \mathrm{adj}(M) = \frac{1}{ad - bc}
\begin{pmatrix}
d & -b \\
-c & a \\
\end{pmatrix}
$$

- Verification: Checking the product $A \cdot A^{-1} = I$ ensures accuracy.
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **Invertibility Check:**
We compute the determinant of matrix $A$:

$$
A =
\begin{pmatrix}
3 & 2 \\
5 & 4 \\
\end{pmatrix}.
$$

We identify the matrix entries:
- Entry $(1,1)$: $a = 3$
- Entry $(1,2)$: $b = 2$
- Entry $(2,1)$: $c = 5$
- Entry $(2,2)$: $d = 4$

Applying the $2 \times 2$ determinant formula:

$$
\begin{aligned}
\det A &= ad - bc \\
       &= (3)(4) - (2)(5) \\
       &= 12 - 10 \\
       &= 2
\end{aligned}
$$

Since $\det A = 2 \neq 0$, matrix $A$ is invertible.

2. **Intermediate Steps:**
We construct the adjugate matrix $\mathrm{adj}(A)$ by swapping the main diagonal entries and negating the off-diagonal entries:

$$
\mathrm{adj}(A) =
\begin{pmatrix}
d & -b \\
-c & a \\
\end{pmatrix} =
\begin{pmatrix}
4 & -2 \\
-5 & 3 \\
\end{pmatrix}.
$$

Applying the inverse formula:

$$
A^{-1} = \frac{1}{\det A} \mathrm{adj}(A) = \frac{1}{2}
\begin{pmatrix}
4 & -2 \\
-5 & 3 \\
\end{pmatrix}.
$$

Distributing the scalar $\frac{1}{2}$ across all entries of the matrix:

$$
A^{-1} =
\begin{pmatrix}
\frac{4}{2} & -\frac{2}{2} \\
-\frac{5}{2} & \frac{3}{2} \\
\end{pmatrix} =
\begin{pmatrix}
2 & -1 \\
-\frac{5}{2} & \frac{3}{2} \\
\end{pmatrix}.
$$

3. **Verification:**
We check the result by computing the product $A \cdot A^{-1}$:

$$
A \cdot A^{-1} =
\begin{pmatrix}
3 & 2 \\
5 & 4 \\
\end{pmatrix}
\begin{pmatrix}
2 & -1 \\
-\frac{5}{2} & \frac{3}{2} \\
\end{pmatrix}.
$$

Evaluating each entry of the product:
- Entry $(1,1)$:

$$
(3)(2) + (2)\left(-\frac{5}{2}\right) = 6 - 5 = 1
$$

- Entry $(1,2)$:

$$
(3)(-1) + (2)\left(\frac{3}{2}\right) = -3 + 3 = 0
$$

- Entry $(2,1)$:

$$
(5)(2) + (4)\left(-\frac{5}{2}\right) = 10 - 10 = 0
$$

- Entry $(2,2)$:

$$
(5)(-1) + (4)\left(\frac{3}{2}\right) = -5 + 6 = 1
$$

Assembling the product matrix:

$$
A \cdot A^{-1} =
\begin{pmatrix}
1 & 0 \\
0 & 1 \\
\end{pmatrix}
= I_2.
$$

The calculation verifies that the resulting matrix is indeed the inverse.

## Final Answer

$$
A^{-1} =
\begin{pmatrix}
2 & -1 \\
-\frac{5}{2} & \frac{3}{2} \\
\end{pmatrix}
$$
