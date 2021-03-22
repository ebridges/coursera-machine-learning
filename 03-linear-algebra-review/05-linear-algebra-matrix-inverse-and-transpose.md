---
Video: machine-learning/03_linear-algebra-review/01_linear-algebra-review/11_inverse-and-transpose.mp4
---

## Matrix Inverse & Transpose

### Inverse

As stated earlier, $1$ is the _identity_ for real numbers.  As well all real numbers have a number considered it's _inverse_, example: $3 \times 3^{-1} = 1$, except for 0.

What does it mean to compute the inverse of a matrix?

If $A$ is an $m \times m$ matrix, and if it has an inverse, it will return the identity:
$$
A \times (A^{-1}) = (A^{-1}) \times A = I
$$

* Note, only square matrices have inverses (num rows == nom cols)

For example:
$$
\begin{bmatrix}
3 && 4 \\
2 && 16
\end{bmatrix}
\times
\begin{bmatrix}
0.4 && -0.1 \\
-0.05 && 0.075
\end{bmatrix}
=
\begin{bmatrix}
1 && 0 \\
0 && 1
\end{bmatrix}
$$
You can, at times, calculate the inverse by hand but is typically easier to use software, like Octave to do this:

```octave
>> pinv(A)
ans = 
    0.4000000  -0.100000
   -0.0500000   0.075000
```

When may a matrix _not_ have an inverse? Overall this is beyond the scope of this review, however the matrix of all zeroes is an obvious example of this.  For machine learning applications, this shouldn't be an issue. when a matrix does not have an inverse, it's known as "singular" or "degenerate".

### Matrix Transpose

Example:
$$
A = 
\begin{bmatrix}
1 && 2 && 0 \\
3 && 5 && 9
\end{bmatrix} \\
A^T = 
\begin{bmatrix}
1 && 3 \\
2 && 5 \\
0 && 9
\end{bmatrix} \\
$$

* The first row of $A$ becomes the first column of $A^T$, and the second row of $A$ becomes the second column of $A^T$
* Let $A$ be an $m \times n$ matrix and let $B = A^T$. Then $B$ is an $n \times m$ matrix and $B_{ij} = A_{ji}$.