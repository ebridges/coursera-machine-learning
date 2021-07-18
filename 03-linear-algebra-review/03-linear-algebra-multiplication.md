---
Video: machine-learning/03_linear-algebra-review/01_linear-algebra-review/05_matrix-vector-multiplication.mp4
---

## Matrix-vector Multiplication

Start with a special case to multiply a matrix with a vector:
$$
\begin{bmatrix}
1 & 3 \\
4 & 0 \\
2 & 1
\end{bmatrix}
\times
\begin{bmatrix}
1 \\
5
\end{bmatrix}
= \ ?
$$
To get the first element will be to take both elements of each row, and to multiply by both elements of the vector, summing those two products:
$$
1\times1 + 3\times5 = 16 \\
4\times1 + 0\times5 = 4 \\
2\times1 + 1\times5 = 7
$$
The result of multiplying a $3\times2$ matrix by a $2\times1$ vector will result in a $3\times1$ vector:
$$
\begin{bmatrix}
16 \\
4 \\
7
\end{bmatrix}
$$
In other words, the resulting vector will be as long as the number of rows in the matrix.

 ## Application to Hypothesis Function

Let say that given a set of 4 house sizes:
$$
sizes = 
\begin{bmatrix}
    2104 \\
    1416 \\
    1534 \\
     852
\end{bmatrix}
$$
And an hypothesis on how to predict the prices for each based on their size:
$$
h_{0}(x) = -40 + 0.25x
$$
I'd like to compute $h_{0}(x)$ for each of those house sizes.

Start by creating a matrix based on the vector of house sizes, and a vector of $\theta_0$ & $\theta_1$; then the product of those two will result in a vector of values corresponding to the $h_0(x)$ for each house size:
$$
\begin{bmatrix}
    1 & 2104 \\
    1 & 1416 \\
    1 & 1534 \\
    1 &  852
\end{bmatrix}
\times
\begin{bmatrix}
-40 \\
0.25
\end{bmatrix}
=
?
$$
The operation of multiplying this matrix against a vector of house sizes, resulting in a 4x1 matrix :
$$
\begin{bmatrix}
1 \times -40 + 0.25 \times 2104 \\
1 \times -40 + 0.25 \times 1416 \\
1 \times -40 + 0.25 \times 1534 \\
1 \times -40 + 0.25 \times 852 \\
\end{bmatrix}
$$
This matrix is a restatement of our hypothesis for each house size:
$$
\begin{bmatrix}
h_0(2104) \\
h_0(1416) \\
h_0(1534) \\
h_0(852)
\end{bmatrix}
$$
When implementing this in software, you can implement this in one line of code:

```
prediction = dataMatrix * parameters
```
