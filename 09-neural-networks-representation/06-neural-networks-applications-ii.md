---
Video: machine-learning/08_neural-networks-representation/03_applications/03_examples-and-intuitions-ii.mp4
---

## Examples and Intuitions II

From these $\Theta^{(1)}$ matrices for AND, NOR, and OR:
$$
\begin{array}{c|c}
AND & \Theta^{(1)}=\left[-30\ 20\ 20 \right]
\\

NOR & \Theta^{(1)}=\left[10\ -20\ -20 \right] 
\\

OR & \Theta^{(1)}=\left[-10\ 20\ 20 \right]
\end{array} \label{ref1}
$$
And, the XNOR function which gives 1 when $x_1$ and $x_2$ are both 0 or both 1:
$$
\begin{array}{cc}0&0&\rightarrow 1\\ 0&1&\rightarrow 0\\ 1&0&\rightarrow 0\\ 1&1&\rightarrow 1\end{array} 
$$
We can combine the matrices in $(\ref{ref1})$ to get the XNOR logical operator:
$$
\begin{bmatrix}x_{0}\\ x_{1}\\ x_{2}\end{bmatrix} \rightarrow \begin{bmatrix}a^{(2)}_{1}\\ a^{(2)}_{2}\end{bmatrix} \rightarrow \begin{bmatrix}a^{(3)}\end{bmatrix} \rightarrow h_{\Theta }(x) \label{ref2}
$$
For the transition from the first to the second layer, we’ll combine the AND and NOR matrices from above into:
$$
\Theta^{(1)}=\begin{bmatrix}-30&20&20&10&-20&-20 \end{bmatrix}
$$
And, for the transition from the second and third layers, we’ll use the values for OR:
$$
\Theta^{(2)}=\begin{bmatrix} -10&20&20 \end{bmatrix}
$$
Given these, each of the nodes from $(\ref{ref2})$ can be expressed as follows presenting us with the XNOR operator using a hidden layer with two nodes.:
$$
\begin{aligned}a^{(2)}&=g(\Theta^{(1)} \times x)\\ a^{(3)}&=g(\Theta^{(2)} \times a^{(2)})\\ h_{\Theta }(x)&=a^{(3)}\end{aligned}
$$


