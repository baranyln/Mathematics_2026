# Problem 08 Solution

## Problem Statement
Let $A,B$ be square matrices such that $\det A=3$ and $\det B=-5$. Compute $\det(AB)$, $\det(BA)$ and, if it exists, $\det(A^{-1}B)$. Explain why the first two results are equal even though usually $AB\neq BA$.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Multiplicative Property of Determinants: For square matrices $A$ and $B$ of the same size, $\det(AB) = \det(A)\det(B)$.
- Inverse Determinant Rule: If $\det A \neq 0$, then $A^{-1}$ exists and $\det(A^{-1}) = \frac{1}{\det A}$.
- Scalar Commutativity: While matrix multiplication is non-commutative ($AB \neq BA$), the determinants $\det A$ and $\det B$ are real scalars, and multiplication of real numbers is commutative: $\det(A)\det(B) = \det(B)\det(A)$.
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **Method Selection & Matrix Setup:**
We are given two square matrices $A$ and $B$ of the same size $n \times n$ with determinants:

$$
\det A = 3, \qquad \det B = -5.
$$

We use the algebraic properties of the determinant map to compute the determinants of the matrix products and the inverse product.

2. **Intermediate Calculations:**
- **Product Formula for $\det(AB)$:**

$$
\det(AB) = \det(A) \cdot \det(B) = (3) \cdot (-5)
$$

- **Product Formula for $\det(BA)$:**

$$
\det(BA) = \det(B) \cdot \det(A) = (-5) \cdot (3)
$$

- **Explanation of Equality $\det(AB) = \det(BA)$:**
Matrix multiplication is generally non-commutative, so $AB \neq BA$ in most cases. However, the determinant map assigns to each matrix a scalar value in the field $\mathbb{R}$.
Multiplication of scalars in $\mathbb{R}$ is commutative:

$$
\det(A) \cdot \det(B) = \det(B) \cdot \det(A)
$$

Therefore:

$$
\det(AB) = \det(BA)
$$

- **Evaluation of $\det(A^{-1}B)$:**
Since $\det A = 3 \neq 0$, matrix $A$ is invertible, which ensures that $A^{-1}$ exists.
Because $A A^{-1} = I$, taking the determinant of both sides gives:

$$
\det(A) \cdot \det(A^{-1}) = \det(I) = 1 \implies \det(A^{-1}) = \frac{1}{\det A} = \frac{1}{3}
$$

Applying the product property to $A^{-1}B$:

$$
\det(A^{-1}B) = \det(A^{-1}) \cdot \det(B) = \left(\frac{1}{\det A}\right) \cdot \det(B) = \left(\frac{1}{3}\right) \cdot (-5)
$$

3. **Arithmetic Evaluation:**
We compute each value:

$$
\begin{aligned}
\det(AB) &= (3) \cdot (-5) = -15 \\
\det(BA) &= (-5) \cdot (3) = -15 \\
\det(A^{-1}B) &= \left(\frac{1}{3}\right) \cdot (-5) = -\frac{5}{3}
\end{aligned}
$$

## Final Answer

$$
\det(AB) = -15, \qquad \det(BA) = -15, \qquad \det(A^{-1}B) = -\frac{5}{3}
$$
