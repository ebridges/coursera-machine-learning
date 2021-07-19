## Matrices & Vectors [^10]

### Matrix

A rectangular array of numbers written in a square bracket, also known as a "2D" array.
$$
M = 
\begin{bmatrix}
1 & 2 & 3 & 4 & 5 \\
3 & 4 & 5 & 6 & 7
\end{bmatrix}
$$


The *dimesion of a matrix* is written as number of rows x number of columns.  

The _entries of a matrix_ are written as $M_{ij}$ = "_i,j_ entry" in the $i^{th}$ row, the $j_{th}$ column.  Example: $M_{32}$ = 5.

### Vector

A special case of a matrix, one which has only one column, an n x 1 matrix.
$$
v = 
\begin{bmatrix}
1 \\
3 \\
5 \\
7
\end{bmatrix}
$$
(2) has 4 entries, so it is a 4 x 1 matrix, or a 4-dimensional vector: a vector with 4 elements.

You refer to the elements of a vector by saying $v_i$ = the $i^{th}$ element of vector $v$. There are two conventions for how to index into a vector: 1-indexed vs. 0-indexed. Example: $v_3$ = 5, when 1-indexed, and $v_3$ = 7 when 0-indexed.
