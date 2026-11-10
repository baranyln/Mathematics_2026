# Problem 15 Solution

## Problem Statement
Let $A$ and $B$ be invertible $2\times2$ matrices with

$$
\det A=-2,\qquad \det B=3.
$$

Without finding the entries of the matrices, compute

$$
\det\left(B^{-1}A^TB\right).
$$

State the determinant properties you use in order and explain why the factors involving $B$ eventually cancel.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Multiplicative Property: The determinant of a product of square matrices equals the product of their individual determinants: $\det(M_1 M_2 \dots M_k) = \det(M_1)\det(M_2)\dots\det(M_k)$.
- Inverse Matrix Property: For an invertible matrix $M$, $\det(M^{-1}) = (\det M)^{-1} = \frac{1}{\det M}$.
- Transposition Property: The determinant of the transpose equals the determinant of the original matrix: $\det(M^T) = \det M$.
- Scalar Commutativity: Determinants are scalars; scalar multiplication is commutative, allowing factors $\frac{1}{\det B}$ and $\det B$ to cancel.
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **Method Selection & Matrix Setup:**
We are given two invertible $2 \times 2$ matrices $A$ and $B$ with determinant values:

$$
\det A = -2, \qquad \det B = 3.
$$

We evaluate $\det\left(B^{-1}A^TB\right)$ without finding the entries of $A$ or $B$ by applying determinant properties in sequential order.

2. **Intermediate Calculations:**
- **Property 1: Determinant of a Product of Matrices**
For any collection of square matrices of the same size:

$$
\det(M_1 M_2 M_3) = \det(M_1) \cdot \det(M_2) \cdot \det(M_3)
$$

Applying this property to the product $B^{-1} \cdot A^T \cdot B$:

$$
\det\left(B^{-1}A^TB\right) = \det\left(B^{-1}\right) \cdot \det\left(A^T\right) \cdot \det(B)
$$

- **Property 2: Determinant of an Inverse Matrix**
Since matrix $B$ is invertible, $B \cdot B^{-1} = I_2$. Taking the determinant of both sides:

$$
\det(B) \cdot \det\left(B^{-1}\right) = \det(I_2) = 1
$$

Since $\det B = 3 \neq 0$:

$$
\det\left(B^{-1}\right) = \frac{1}{\det B}
$$

- **Property 3: Determinant of a Transpose Matrix**
Transposition does not change the determinant:

$$
\det\left(A^T\right) = \det(A)
$$

- **Combining the Properties:**
Substituting Property 2 and Property 3 into the product expansion:

$$
\begin{aligned}
\det\left(B^{-1}A^TB\right) &= \left(\frac{1}{\det B}\right) \cdot \det(A) \cdot \det(B) \\
&= \det(A) \cdot \left(\frac{1}{\det B} \cdot \det B\right) \\
&= \det(A) \cdot 1 \\
&= \det(A)
\end{aligned}
$$

- **Explanation of Why the Factors Involving $B$ Cancel:**
The determinants $\det(B^{-1})$ and $\det(B)$ are non-zero real scalar numbers.
Because scalar multiplication in $\mathbb{R}$ is commutative and associative:

$$
\frac{1}{\det B} \cdot \det B = 1
$$

From an algebraic perspective, the matrix $B^{-1}A^TB$ represents a similarity transformation of $A^T$ with respect to the invertible change-of-basis matrix $B$. Similar matrices represent the same linear transformation under different coordinate bases and therefore have identical determinants, eigenvalues, and characteristic polynomials.

3. **Arithmetic Evaluation:**
We substitute the given numerical values:

$$
\begin{aligned}
\det\left(B^{-1}\right) &= \frac{1}{3} \\
\det\left(A^T\right) &= -2 \\
\det(B) &= 3
\end{aligned}
$$

Evaluating the product:

$$
\begin{aligned}
\det\left(B^{-1}A^TB\right) &= \left(\frac{1}{3}\right) \cdot (-2) \cdot (3) \\
&= \left(\frac{1}{3} \cdot 3\right) \cdot (-2) \\
&= 1 \cdot (-2) \\
&= -2
\end{aligned}
$$

Thus:

$$
\det\left(B^{-1}A^TB\right) = -2
$$

## Final Answer

$$
\det\left(B^{-1}A^TB\right) = -2
$$
