# Problem 15 Solution

## Problem Statement
For

$$
A=
\begin{pmatrix}
2 & 1 \\
1 & 3 \\
\end{pmatrix},\qquad b=
\begin{pmatrix}
7 \\
8 \\
\end{pmatrix}
$$

solve $Ax=b$ in two ways:

1. using $A^{-1}b$,
2. using Gaussian elimination.

Compare both solutions, the number of essential steps, and state which method was simpler in this example.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Method 1: Matrix Inversion: $x = A^{-1}b$, where $A^{-1} = \frac{1}{\det A} \mathrm{adj}(A)$.
- Method 2: Gaussian Elimination: Form the augmented matrix $[A \mid b]$, apply row operations to reach upper triangular form, and solve via back-substitution.
- Comparative Complexity Analysis: Compare operation counts and computational overhead for a single system versus multiple right-hand sides.
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

Since $\det A = 5 \neq 0$, matrix $A$ is non-singular and the linear system $Ax = b$ has a unique solution.

2. **Intermediate Steps:**
**Method 1: Solving via Matrix Inversion ($x = A^{-1}b$)**
We find $A^{-1}$ using the explicit $2 \times 2$ inverse formula:

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
\end{pmatrix} =
\begin{pmatrix}
\frac{3}{5} & -\frac{1}{5} \\
-\frac{1}{5} & \frac{2}{5} \\
\end{pmatrix}.
$$

We now multiply $A^{-1}$ by $b$:

$$
x = A^{-1}b = \frac{1}{5}
\begin{pmatrix}
3 & -1 \\
-1 & 2 \\
\end{pmatrix}
\begin{pmatrix}
7 \\
8 \\
\end{pmatrix}.
$$

Evaluating each component:
- First component:

$$
(3)(7) + (-1)(8) = 21 - 8 = 13
$$

- Second component:

$$
(-1)(7) + (2)(8) = -7 + 16 = 9
$$

Assembling the solution vector:

$$
x = \frac{1}{5}
\begin{pmatrix}
13 \\
9 \\
\end{pmatrix} =
\begin{pmatrix}
\frac{13}{5} \\
\frac{9}{5} \\
\end{pmatrix}.
$$

**Method 2: Solving via Gaussian Elimination**
We form the augmented matrix $[A \mid b]$:

$$
\begin{pmatrix}
2 & 1 & \mid & 7 \\
1 & 3 & \mid & 8 \\
\end{pmatrix}.
$$

**Step 1: Swap Row 1 and Row 2 ($R_1 \leftrightarrow R_2$) to obtain pivot 1**

$$
\begin{pmatrix}
1 & 3 & \mid & 8 \\
2 & 1 & \mid & 7 \\
\end{pmatrix}.
$$

**Step 2: Eliminate entry $(2,1)$ using operation $R_2 \leftarrow R_2 - 2R_1$**
We compute the new entries of Row 2:

$$
\begin{aligned}
r_{21} &= 2 - 2(1) = 2 - 2 = 0 \\
r_{22} &= 1 - 2(3) = 1 - 6 = -5 \\
r_{23} &= 7 - 2(8) = 7 - 16 = -9
\end{aligned}
$$

The augmented matrix in row echelon form is:

$$
\begin{pmatrix}
1 & 3 & \mid & 8 \\
0 & -5 & \mid & -9 \\
\end{pmatrix}.
$$

**Step 3: Back-Substitution**
From Row 2:

$$
-5x_2 = -9 \implies x_2 = \frac{9}{5}
$$

From Row 1:

$$
x_1 + 3x_2 = 8 \implies x_1 = 8 - 3x_2
$$

Substituting $x_2 = \frac{9}{5}$:

$$
x_1 = 8 - 3\left(\frac{9}{5}\right) = \frac{40}{5} - \frac{27}{5} = \frac{13}{5}
$$

Assembling the solution vector:

$$
x =
\begin{pmatrix}
\frac{13}{5} \\
\frac{9}{5} \\
\end{pmatrix}.
$$

3. **Verification & Comparison of Methods:**
We check the solution vector by substituting it into the original equations:

$$
Ax =
\begin{pmatrix}
2 & 1 \\
1 & 3 \\
\end{pmatrix}
\begin{pmatrix}
\frac{13}{5} \\
\frac{9}{5} \\
\end{pmatrix}.
$$

Evaluating each row:
- First row:

$$
2\left(\frac{13}{5}\right) + 1\left(\frac{9}{5}\right) = \frac{26}{5} + \frac{9}{5} = \frac{35}{5} = 7
$$

- Second row:

$$
1\left(\frac{13}{5}\right) + 3\left(\frac{9}{5}\right) = \frac{13}{5} + \frac{27}{5} = \frac{40}{5} = 8
$$

Both equations match the entries of $b = \begin{pmatrix} 7 \\ 8 \\ \end{pmatrix}$.

**Comparison of Both Solutions:**
- **Number of essential steps:**
  - Method 1 requires computing the determinant (3 operations), constructing the adjugate matrix, scaling by $\frac{1}{\det A}$ (4 operations), and performing a matrix-vector product (4 multiplications and 2 additions). In total, about 13 arithmetic operations.
  - Method 2 requires one row swap, one row elimination step (2 multiplications, 2 subtractions), and back-substitution (1 division, 1 multiplication, 1 subtraction). In total, about 7 arithmetic operations.
- **Simpler Method for this Example:**
  Gaussian elimination was simpler and faster because it worked directly on the augmented vector $b$ in a single elimination step without the overhead of computing all four entries of the full inverse matrix $A^{-1}$. Finding $A^{-1}$ is only more efficient when the same matrix $A$ is used to solve $Ax = b$ for many different vectors $b$.

## Final Answer

$$
x =
\begin{pmatrix}
\frac{13}{5} \\
\frac{9}{5} \\
\end{pmatrix}, \qquad A^{-1} =
\begin{pmatrix}
\frac{3}{5} & -\frac{1}{5} \\
-\frac{1}{5} & \frac{2}{5} \\
\end{pmatrix}
$$

Both methods yield the identical solution. Gaussian elimination is simpler and requires fewer arithmetic steps for this single problem instance.
