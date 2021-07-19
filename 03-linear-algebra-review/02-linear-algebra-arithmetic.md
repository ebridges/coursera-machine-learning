## Addition and Scalar multiplication [^11]

### Addition

Suppose we have two matrices that we'd like to add:
$$
\begin{bmatrix}
1 & 0 \\
2 & 5 \\
3 & 1
\end{bmatrix} +
\begin{bmatrix}
4 & 0.5 \\
2 & 5 \\
0 & 1
\end{bmatrix} =
\begin{bmatrix}
5 & 0.5 \\
4 & 10 \\
3 & 2
\end{bmatrix}
$$
The result would be a matrix where you sum up each corresponding member of the two matrices.  Matrices must be of the same dimensions in order to do this.

Subtraction works the same way.

### Scalar multiplication

$$
3 \times 
\begin{bmatrix}
1 & 0 \\
2 & 5 \\
3 & 1
\end{bmatrix} =
\begin{bmatrix}
3 & 0 \\
6 & 15 \\
9 & 3
\end{bmatrix}
$$
Multiply each member of the matrix by the scalar value. Result is a matrix of the same dimension as the multplicand.  Division is treated as multiplication by the inverse of the divisor.
$$
\begin{bmatrix}
4 & 0 \\
6 & 3
\end{bmatrix} 
\div 4
=
\begin{bmatrix}
4 & 0 \\
6 & 3
\end{bmatrix} 
\times \frac{1}{4} 
=
\begin{bmatrix}
1 & 0 \\
\frac{3}{2} & \frac{3}{4}
\end{bmatrix}
$$

### Combination of Operands

Order of operations follows the same sequence as in ordinary arithmetic.  Given the following set of operations:
$$
3 \times 
\begin{bmatrix}
1 \\
4 \\
2
\end{bmatrix} 
+
\begin{bmatrix}
0 \\
0 \\
5
\end{bmatrix}
-
\begin{bmatrix}
3 \\
0 \\
2
\end{bmatrix}
\div
3
$$
Do multiplication and division first:
$$
\begin{bmatrix}
3 \\
12 \\
6
\end{bmatrix} 
+
\begin{bmatrix}
0 \\
0 \\
5
\end{bmatrix}
-
\begin{bmatrix}
1 \\
0 \\
\frac{2}{3}
\end{bmatrix}
$$
Then do the addition and subtraction:
$$
\begin{bmatrix}
2 \\
12 \\
10\frac{1}{3}
\end{bmatrix}
$$
Note vector arithmetic is the same as matrix arithmetic, as a vector is a special case of a matrix.