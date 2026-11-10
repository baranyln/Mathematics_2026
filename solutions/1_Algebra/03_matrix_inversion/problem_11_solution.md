# Problem 11 Solution

## Problem Statement
For

$$
A(t)=
\begin{pmatrix}
1 & t \\
t & 1 \\
\end{pmatrix}
$$

find all $t$ for which the matrix is invertible, and then give a formula for $A(t)^{-1}$. Explain what happens to this formula at the excluded values.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Parameter Invertibility Condition: A parameterized matrix $A(t)$ is invertible if and only if its determinant polynomial is non-zero: $\det A(t) \neq 0$.
- Parameterized Inverse Formula: For $A(t) = \begin{pmatrix} a & b \\ c & d \\ \end{pmatrix}$, $A(t)^{-1} = \frac{1}{\det A(t)} \begin{pmatrix} d & -b \\ -c & a \\ \end{pmatrix}$.
- Analysis of Singularities: At values where $\det A(t) = 0$, the inverse formula fails due to division by zero, reflecting a collapse in matrix rank and linear dependence of the rows.
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **Invertibility Check:**
We compute the determinant of $A(t)$:

$$
A(t) =
\begin{pmatrix}
1 & t \\
t & 1 \\
\end{pmatrix}.
$$

Applying the $2 \times 2$ determinant formula:

$$
\begin{aligned}
\det A(t) &= (a_{11})(a_{22}) - (a_{12})(a_{21}) \\
          &= (1)(1) - (t)(t) \\
          &= 1 - t^2
\end{aligned}
$$

Setting the determinant equal to zero to identify non-invertible values:

$$
1 - t^2 = 0 \iff (1 - t)(1 + t) = 0
$$

This gives two solutions: $t = 1$ and $t = -1$.

Therefore, matrix $A(t)$ is invertible for all real values of $t$ except $t = 1$ and $t = -1$:

$$
t \in \mathbb{R} \setminus \{-1, 1\}
$$

2. **Intermediate Steps:**
For all $t \neq \pm 1$, we construct the adjugate matrix $\mathrm{adj}(A(t))$:

$$
\mathrm{adj}(A(t)) =
\begin{pmatrix}
1 & -t \\
-t & 1 \\
\end{pmatrix}.
$$

Applying the inverse formula:

$$
A(t)^{-1} = \frac{1}{\det A(t)} \mathrm{adj}(A(t)) = \frac{1}{1 - t^2}
\begin{pmatrix}
1 & -t \\
-t & 1 \\
\end{pmatrix}.
$$

Distributing the scalar $\frac{1}{1 - t^2}$ across all entries:

$$
A(t)^{-1} =
\begin{pmatrix}
\frac{1}{1 - t^2} & -\frac{t}{1 - t^2} \\
-\frac{t}{1 - t^2} & \frac{1}{1 - t^2} \\
\end{pmatrix}.
$$

**Explanation of What Happens at the Excluded Values:**
- At $t = 1$: The denominator $1 - t^2 = 1 - 1^2 = 0$. The formula requires dividing by zero, which is undefined. Substituting $t = 1$ into $A(t)$ gives:

$$
A(1) =
\begin{pmatrix}
1 & 1 \\
1 & 1 \\
\end{pmatrix}.
$$

Here, Row 1 and Row 2 are identical ($R_1 = R_2$). The rows are linearly dependent, and the rank of $A(1)$ drops to $1 < 2$.
- At $t = -1$: The denominator $1 - t^2 = 1 - (-1)^2 = 0$, again leading to division by zero. Substituting $t = -1$ into $A(t)$ gives:

$$
A(-1) =
\begin{pmatrix}
1 & -1 \\
-1 & 1 \\
\end{pmatrix}.
$$

Here, Row 2 is the exact negative of Row 1 ($R_2 = -R_1$). The rows are linearly dependent, and the rank of $A(-1)$ is $1 < 2$.
- In both cases, the linear transformation represented by $A(t)$ collapses $\mathbb{R}^2$ onto a one-dimensional line, so the mapping is not bijective and no inverse transformation can exist.

3. **Verification:**
For any $t \neq \pm 1$, we check the product $A(t) \cdot A(t)^{-1}$:

$$
A(t) \cdot A(t)^{-1} =
\begin{pmatrix}
1 & t \\
t & 1 \\
\end{pmatrix}
\left[\frac{1}{1 - t^2}
\begin{pmatrix}
1 & -t \\
-t & 1 \\
\end{pmatrix}\right].
$$

Evaluating the matrix product:
- Entry $(1,1)$: $(1)(1) + (t)(-t) = 1 - t^2$
- Entry $(1,2)$: $(1)(-t) + (t)(1) = -t + t = 0$
- Entry $(2,1)$: $(t)(1) + (1)(-t) = t - t = 0$
- Entry $(2,2)$: $(t)(-t) + (1)(1) = -t^2 + 1 = 1 - t^2$

Multiplying by $\frac{1}{1 - t^2}$:

$$
A(t) \cdot A(t)^{-1} = \frac{1}{1 - t^2}
\begin{pmatrix}
1 - t^2 & 0 \\
0 & 1 - t^2 \\
\end{pmatrix} =
\begin{pmatrix}
1 & 0 \\
0 & 1 \\
\end{pmatrix}
= I_2.
$$

The formula is completely verified.

## Final Answer

The matrix $A(t)$ is invertible for all $t \in \mathbb{R} \setminus \{-1, 1\}$.

$$
A(t)^{-1} = \frac{1}{1 - t^2}
\begin{pmatrix}
1 & -t \\
-t & 1 \\
\end{pmatrix}
$$
