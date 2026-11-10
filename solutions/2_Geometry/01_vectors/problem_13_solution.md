# Problem 13 Solution

## Problem Statement
Given

$$
A=(0,0,0),\qquad B=(1,2,0),\qquad C=(0,1,1),\qquad D=(2,5,1).
$$

1. Construct $\overrightarrow{AB}$ and $\overrightarrow{AC}$.
2. Find $n=\overrightarrow{AB}\times\overrightarrow{AC}$.
3. Construct $\overrightarrow{AD}$ and check whether $\overrightarrow{AD}\cdot n=0$.
4. Based on this, decide whether $D$ lies in the plane determined by $A,B,C$, and justify the criterion.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Plane Normal via Cross Product: For three points $A, B, C$, the cross product:

$$
n = \overrightarrow{AB} \times \overrightarrow{AC}
$$

is perpendicular to every vector lying in the plane of $A, B, C$.
- Coplanarity Test (Scalar Triple Product): A fourth point $D$ lies in the plane through $A, B, C$ if and only if the displacement $\overrightarrow{AD}$ is perpendicular to the plane's normal vector $n$:

$$
\overrightarrow{AD} \cdot n = 0 \iff D \in \mathrm{plane}(A, B, C)
$$

This condition is equivalent to requiring the scalar triple product $\overrightarrow{AB} \cdot (\overrightarrow{AC} \times \overrightarrow{AD}) = 0$, which equals zero if and only if the three edge vectors from $A$ span zero volume.
- Cross Product Component Formula:

$$
p \times q = (p_2 q_3 - p_3 q_2, \; p_3 q_1 - p_1 q_3, \; p_1 q_2 - p_2 q_1)
$$

- Formatting Standards: Display math with `$$` on separate lines, no `\text` macros, and all arithmetic products stated explicitly.

## Detailed Step-by-Step Solution
1. **Vector Setup & Formula Selection:**
We are given four points in $\mathbb{R}^3$:

$$
A = (0, 0, 0), \qquad B = (1, 2, 0), \qquad C = (0, 1, 1), \qquad D = (2, 5, 1)
$$

We will construct three edge vectors from vertex $A$, compute the normal vector $n$ to the plane through $A, B, C$, evaluate the dot product $\overrightarrow{AD} \cdot n$, and use the result to decide coplanarity.

2. **Intermediate Calculations:**
- **Step 1: Construct displacement vectors $\overrightarrow{AB}$ and $\overrightarrow{AC}$:**
Subtract coordinates of $A = (0,0,0)$ from $B$:

$$
\begin{aligned}
\overrightarrow{AB} &= B - A \\
                   &= (1 - 0, 2 - 0, 0 - 0) \\
                   &= (1, 2, 0)
\end{aligned}
$$

Subtract coordinates of $A$ from $C$:

$$
\begin{aligned}
\overrightarrow{AC} &= C - A \\
                   &= (0 - 0, 1 - 0, 1 - 0) \\
                   &= (0, 1, 1)
\end{aligned}
$$

- **Step 2: Compute the normal vector $n = \overrightarrow{AB} \times \overrightarrow{AC}$:**
Let $p = \overrightarrow{AB} = (1, 2, 0)$ and $q = \overrightarrow{AC} = (0, 1, 1)$. Apply the cross product component formulas:

$$
\begin{aligned}
n_1 &= p_2 q_3 - p_3 q_2 = (2)(1) - (0)(1) = 2 - 0 = 2 \\
n_2 &= p_3 q_1 - p_1 q_3 = (0)(0) - (1)(1) = 0 - 1 = -1 \\
n_3 &= p_1 q_2 - p_2 q_1 = (1)(1) - (2)(0) = 1 - 0 = 1
\end{aligned}
$$

Assembling the components:

$$
n = \overrightarrow{AB} \times \overrightarrow{AC} = (2, -1, 1)
$$

- **Step 3: Construct displacement vector $\overrightarrow{AD}$:**
Subtract coordinates of $A = (0,0,0)$ from $D$:

$$
\begin{aligned}
\overrightarrow{AD} &= D - A \\
                   &= (2 - 0, 5 - 0, 1 - 0) \\
                   &= (2, 5, 1)
\end{aligned}
$$

- **Step 4: Compute the dot product $\overrightarrow{AD} \cdot n$:**
Substitute the components of $\overrightarrow{AD} = (2, 5, 1)$ and $n = (2, -1, 1)$:

$$
\begin{aligned}
\overrightarrow{AD} \cdot n &= (2)(2) + (5)(-1) + (1)(1) \\
                            &= 4 - 5 + 1 \\
                            &= 0
\end{aligned}
$$

3. **Evaluation & Geometric Justification:**
- **Decision:** Since $\overrightarrow{AD} \cdot n = 0$, the displacement vector from $A$ to $D$ is perpendicular to the normal of the plane through $A, B, C$. Therefore, $\overrightarrow{AD}$ lies within the plane, which means point $D$ lies in the same plane as $A, B, C$.

- **Geometric Justification of the Criterion:**
The normal vector $n = \overrightarrow{AB} \times \overrightarrow{AC}$ points perpendicularly out of the plane containing $A$, $B$, and $C$. Any vector that lies inside this plane must be perpendicular to the outward normal $n$. The dot product $\overrightarrow{AD} \cdot n$ measures the projection of $\overrightarrow{AD}$ onto the normal direction, which equals the signed height of $D$ above the plane measured perpendicularly. When this dot product is zero, $D$ has zero height above the plane, meaning $D$ is in the plane. This is precisely the scalar triple product criterion: the volume of the parallelepiped spanned by $\overrightarrow{AB}$, $\overrightarrow{AC}$, $\overrightarrow{AD}$ equals $|\overrightarrow{AB} \cdot (\overrightarrow{AC} \times \overrightarrow{AD})|$, and zero volume means the four points are coplanar.

## Final Answer

$$
\overrightarrow{AB} = (1, 2, 0), \qquad \overrightarrow{AC} = (0, 1, 1)
$$

$$
n = \overrightarrow{AB} \times \overrightarrow{AC} = (2, -1, 1)
$$

$$
\overrightarrow{AD} = (2, 5, 1)
$$

$$
\overrightarrow{AD} \cdot n = 4 - 5 + 1 = 0
$$

Since $\overrightarrow{AD} \cdot n = 0$, point $D$ lies in the plane determined by $A$, $B$, and $C$.
