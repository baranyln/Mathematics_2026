# Problem 01 Solution

## Problem Statement
Write the system

$$
\begin{cases}
2x-y+z=4, \\
x+3y-2z=1, \\
3x+y+z=7.
\end{cases}
$$

in the form $Ax=b$.
Identify the coefficient matrix, the vector of unknowns, and the right-hand side vector. Explain how each row of the matrix corresponds to one equation.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Matrix Formulation of a Linear System: Any system of $m$ linear equations in $n$ unknowns can be represented in matrix form as $Ax = b$, where $A \in \mathbb{R}^{m \times n}$ is the coefficient matrix, $x \in \mathbb{R}^n$ is the column vector of unknowns, and $b \in \mathbb{R}^m$ is the right-hand side constant vector.
- Row-to-Equation Correspondence: The $i$-th row of $A$ contains the coefficients multiplying the variables in the $i$-th equation, and their scalar dot product with $x$ equals the $i$-th component of $b$.
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 5 (`cases` environment with rows on separate lines ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **System Setup & Matrix Formulation:**
We are given the system of 3 linear equations in 3 unknowns ($x, y, z$):

$$
\begin{cases}
2x - 1y + 1z = 4, \\
1x + 3y - 2z = 1, \\
3x + 1y + 1z = 7.
\end{cases}
$$

We extract the coefficients of the unknowns $x, y, z$ into the matrix $A$:

$$
A =
\begin{pmatrix}
2 & -1 & 1 \\
1 & 3 & -2 \\
3 & 1 & 1 \\
\end{pmatrix}.
$$

We collect the unknowns into the column vector $x$:

$$
x =
\begin{pmatrix}
x \\
y \\
z \\
\end{pmatrix}.
$$

We place the constants from the right-hand sides into the column vector $b$:

$$
b =
\begin{pmatrix}
4 \\
1 \\
7 \\
\end{pmatrix}.
$$

Thus, the system in matrix form $Ax = b$ is:

$$
\begin{pmatrix}
2 & -1 & 1 \\
1 & 3 & -2 \\
3 & 1 & 1 \\
\end{pmatrix}
\begin{pmatrix}
x \\
y \\
z \\
\end{pmatrix} =
\begin{pmatrix}
4 \\
1 \\
7 \\
\end{pmatrix}.
$$

The augmented matrix $[A \mid b]$ is written as:

$$
\begin{pmatrix}
2 & -1 & 1 & \mid & 4 \\
1 & 3 & -2 & \mid & 1 \\
3 & 1 & 1 & \mid & 7 \\
\end{pmatrix}.
$$

2. **Intermediate Steps:**
**Explanation of Row-to-Equation Correspondence:**
By the definition of matrix-vector multiplication, the product $Ax$ computes the linear combination of the columns of $A$ weighted by the entries of $x$, or equivalently, the dot product of each row vector $R_i$ of $A$ with the vector $x$:

- **Row 1:** The first row of $A$ is $R_1 = \begin{pmatrix} 2 & -1 & 1 \end{pmatrix}$. Computing its dot product with $x$:

$$
(2)(x) + (-1)(y) + (1)(z) = 2x - y + z
$$

Equating this to the first entry of $b$ gives the first equation:

$$
2x - y + z = 4.
$$

- **Row 2:** The second row of $A$ is $R_2 = \begin{pmatrix} 1 & 3 & -2 \end{pmatrix}$. Computing its dot product with $x$:

$$
(1)(x) + (3)(y) + (-2)(z) = x + 3y - 2z
$$

Equating this to the second entry of $b$ gives the second equation:

$$
x + 3y - 2z = 1.
$$

- **Row 3:** The third row of $A$ is $R_3 = \begin{pmatrix} 3 & 1 & 1 \end{pmatrix}$. Computing its dot product with $x$:

$$
(3)(x) + (1)(y) + (1)(z) = 3x + y + z
$$

Equating this to the third entry of $b$ gives the third equation:

$$
3x + y + z = 7.
$$

Each row $i$ of the matrix corresponds to the linear constraint imposed by the $i$-th equation of the system.

3. **Variable Evaluation & Consistency Check:**
We verify that the system is consistent by evaluating the determinant of the coefficient matrix $A$:

$$
\begin{aligned}
\det A &= 2 \cdot \det\begin{pmatrix} 3 & -2 \\ 1 & 1 \\ \end{pmatrix} - (-1) \cdot \det\begin{pmatrix} 1 & -2 \\ 3 & 1 \\ \end{pmatrix} + 1 \cdot \det\begin{pmatrix} 1 & 3 \\ 3 & 1 \\ \end{pmatrix} \\
       &= 2(3 + 2) + 1(1 + 6) + 1(1 - 9) \\
       &= 2(5) + 1(7) + 1(-8) \\
       &= 10 + 7 - 8 \\
       &= 9
\end{aligned}
$$

Because $\det A = 9 \neq 0$, the matrix $A$ is non-singular and the system has a unique solution.
Solving by Gaussian elimination:
- From $[A \mid b]$, subtracting Row 1 from Row 3 gives:

$$
(3x + y + z) - (2x - y + z) = 7 - 4 \implies x + 2y = 3 \implies x = 3 - 2y
$$

- Substituting $x = 3 - 2y$ into the second equation:

$$
(3 - 2y) + 3y - 2z = 1 \implies y - 2z = -2 \implies y = 2z - 2
$$

- Expressing $x$ in terms of $z$:

$$
x = 3 - 2(2z - 2) = 3 - 4z + 4 = 7 - 4z
$$

- Substituting $x$ and $y$ into the first equation:

$$
2(7 - 4z) - (2z - 2) + z = 4 \implies 14 - 8z - 2z + 2 + z = 4 \implies 16 - 9z = 4
$$

$$
-9z = -12 \implies z = \frac{12}{9} = \frac{4}{3}
$$

- Computing $y$ and $x$:

$$
y = 2\left(\frac{4}{3}\right) - 2 = \frac{8}{3} - \frac{6}{3} = \frac{2}{3}
$$

$$
x = 7 - 4\left(\frac{4}{3}\right) = \frac{21}{3} - \frac{16}{3} = \frac{5}{3}
$$

**Consistency Check:**
- Equation 1: $2\left(\frac{5}{3}\right) - \left(\frac{2}{3}\right) + \left(\frac{4}{3}\right) = \frac{10 - 2 + 4}{3} = \frac{12}{3} = 4$. Correct.
- Equation 2: $\left(\frac{5}{3}\right) + 3\left(\frac{2}{3}\right) - 2\left(\frac{4}{3}\right) = \frac{5 + 6 - 8}{3} = \frac{3}{3} = 1$. Correct.
- Equation 3: $3\left(\frac{5}{3}\right) + \left(\frac{2}{3}\right) + \left(\frac{4}{3}\right) = \frac{15 + 2 + 4}{3} = \frac{21}{3} = 7$. Correct.

## Final Answer

$$
A =
\begin{pmatrix}
2 & -1 & 1 \\
1 & 3 & -2 \\
3 & 1 & 1 \\
\end{pmatrix}, \qquad x =
\begin{pmatrix}
x \\
y \\
z \\
\end{pmatrix}, \qquad b =
\begin{pmatrix}
4 \\
1 \\
7 \\
\end{pmatrix}
$$

The unique solution to the system is:

$$
x = \frac{5}{3}, \quad y = \frac{2}{3}, \quad z = \frac{4}{3}
$$
