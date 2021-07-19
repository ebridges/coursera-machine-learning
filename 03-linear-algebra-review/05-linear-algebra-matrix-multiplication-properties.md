## Matrix Multiplication Properties [^15]

Using matrix multiplication is very useful for packing a lot of computation into just one matrix multiplication operation.

### Not Commutative

When working with scalars or real numbers, multiplication is commutative: $3\times5 = 5\times3$. 

However, matrix multiplication is _not_ commutative: $A \times B \neq B \times A$

Example:
$$
\begin{bmatrix}
1 && 1 \\
0 && 0
\end{bmatrix}
\times
\begin{bmatrix}
0 && 0 \\
2 && 0
\end{bmatrix}
=
\begin{bmatrix}
2 && 0 \\
0 && 0
\end{bmatrix}
\\
\neq
\\
\begin{bmatrix}
0 && 0 \\
2 && 0
\end{bmatrix}
\times
\begin{bmatrix}
1 && 1 \\
0 && 0
\end{bmatrix}
=
\begin{bmatrix}
0 && 0 \\
2 && 0 
\end{bmatrix}
$$
This can even change the dimensions of the outcome.

### Is Associative

With scalar numbers, $(3\times5)\times2 = 3\times(5\times2)$ the association of the operands _is associative_: the same product will result regardless of the order of multiplication.

This is also the case with matrix multiplication, which _is also associative_: $(A \times B) \times C = A \times (B \times C)$

Example:
$$
Let\ D = B \times C, then\ compute\ A \times D.
$$
Or,
$$
Let\ E = A \times B, then\ compute\ E \times C.
$$
Both (3) & (4) will result in the same product.

### Identity Matrix

$1$ is the identity operation, for any $z$:
$$
1 \times z = z \times 1 = z
$$
Examples of identity matrices:
$$
I_{2 \times 2} = \begin{bmatrix}
1 && 0 \\
0 && 1
\end{bmatrix}
\\
or \\
\\
I_{4 \times 4} = \begin{bmatrix}
1 && 0 && 0 && 0 \\
0 && 1 && 0 && 0 \\
0 && 0 && 1 && 0 \\
0 && 0 && 0 && 1
\end{bmatrix}
$$
The identity matrix has the property of ones along the diagonal and zeroes everyone else.  

As well it has the property for any matrix $A$, which is the identity property:
$$
A \cdot I = I \cdot A = A
$$

* The identity matrix must have the same dimension as $A$

* In general $A \times B \neq B \times A$, however this does hold true if $B$ is an identity matrix.