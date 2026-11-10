# Problem 14 Solution

## Problem Statement
Assume that a square matrix $A$ satisfies

$$
A^2=I.
$$

Show that

$$
A^{-1}=A.
$$

Then give an example of a $2\times2$ matrix different from $I$ and $-I$ that satisfies this condition, and verify it by multiplication.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Definition of Involutory Matrix: A matrix $A$ satisfying $A^2 = I$ is called an involutory matrix. By the definition of the inverse, if $A \cdot B = B \cdot A = I$, then $B$ is the unique inverse of $A$. Setting $B = A$ proves $A^{-1} = A$.
- Invertibility Criterion via Determinants: $\det(A^2) = (\det A)^2 = \det(I) = 1 \implies \det A = \pm 1 \neq 0$, guaranteeing invertibility.
- Geometric Interpretation: Geometrically, involutory matrices represent reflections or self-inverse permutations.
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **Invertibility Check:**
We are given that the square matrix $A \in \mathbb{R}^{n \times n}$ satisfies:

$$
A^2 = I_n.
$$

Taking the determinant of both sides and applying the multiplicative property $\det(A^2) = (\det A)^2$:

$$
\det\left(A^2\right) = \det(I_n) \implies (\det A)^2 = 1.
$$

Taking square roots:

$$
\det A = 1 \qquad \mathrm{or} \qquad \det A = -1.
$$

In both cases, $\det A \neq 0$. Therefore, matrix $A$ is non-singular and its inverse $A^{-1}$ exists.

2. **Intermediate Steps:**
**Proof that $A^{-1} = A$:**
By the definition of matrix exponentiation, the condition $A^2 = I$ is written as:

$$
A \cdot A = I_n.
$$

Since $A^{-1}$ exists, we multiply both sides of this equation on the left by $A^{-1}$:

$$
A^{-1}(A \cdot A) = A^{-1} I_n.
$$

Applying the associative property of matrix multiplication:

$$
(A^{-1} A) A = A^{-1}.
$$

Since $A^{-1} A = I_n$:

$$
I_n A = A^{-1} \implies A = A^{-1}.
$$

Equivalently, by the uniqueness of the inverse matrix, any matrix that multiplies $A$ to yield the identity matrix must be its inverse. Since $A$ multiplied by itself yields $I_n$, it follows directly that $A^{-1} = A$.

**Constructing an Example of a $2 \times 2$ Matrix Different from $I$ and $-I$:**
Consider the reflection matrix across the line $y = x$ (which swaps coordinates $x$ and $y$):

$$
A =
\begin{pmatrix}
0 & 1 \\
1 & 0 \\
\end{pmatrix}.
$$

We check that this matrix is distinct from $I_2$ and $-I_2$:

$$
A =
\begin{pmatrix}
0 & 1 \\
1 & 0 \\
\end{pmatrix}
\neq
\begin{pmatrix}
1 & 0 \\
0 & 1 \\
\end{pmatrix}
= I_2
$$

and

$$
A =
\begin{pmatrix}
0 & 1 \\
1 & 0 \\
\end{pmatrix}
\neq
\begin{pmatrix}
-1 & 0 \\
0 & -1 \\
\end{pmatrix}
= -I_2.
$$

3. **Verification:**
We verify that $A^2 = I_2$ by direct matrix multiplication:

$$
A^2 = A \cdot A =
\begin{pmatrix}
0 & 1 \\
1 & 0 \\
\end{pmatrix}
\begin{pmatrix}
0 & 1 \\
1 & 0 \\
\end{pmatrix}.
$$

Evaluating each entry:
- Entry $(1,1)$: $(0)(0) + (1)(1) = 0 + 1 = 1$
- Entry $(1,2)$: $(0)(1) + (1)(0) = 0 + 0 = 0$
- Entry $(2,1)$: $(1)(0) + (0)(1) = 0 + 0 = 0$
- Entry $(2,2)$: $(1)(1) + (0)(0) = 1 + 0 = 1$

Assembling the product matrix:

$$
A^2 =
\begin{pmatrix}
1 & 0 \\
0 & 1 \\
\end{pmatrix}
= I_2.
$$

We also check the determinant of this matrix:

$$
\det A = (0)(0) - (1)(1) = 0 - 1 = -1 \neq 0.
$$

Since $A \cdot A = I_2$, its inverse is:

$$
A^{-1} = A =
\begin{pmatrix}
0 & 1 \\
1 & 0 \\
\end{pmatrix}.
$$

The condition $A^{-1} = A$ is fully verified.

## Final Answer

$$
A^{-1} = A
$$

An example of such a $2 \times 2$ matrix is:

$$
A =
\begin{pmatrix}
0 & 1 \\
1 & 0 \\
\end{pmatrix}
$$

which satisfies $A^2 = I_2$ with $A \neq I_2$ and $A \neq -I_2$.
