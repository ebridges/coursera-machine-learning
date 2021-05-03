---
Video: machine-learning/09_neural-networks-learning/02_backpropagation-in-practice/01_implementation-note-unrolling-parameters.mp4
---

## Implementation Note: Unrolling Parameters

With neural networks, we are working with sets of matrices:
$$
\Theta^{(1)}, \Theta^{(2)}, \Theta^{(3)}, ...\\
D^{(1)}, D^{(2)}, D^{(3)}, ...
$$
And, in order to use optimizing functions such as `fminunc()`, we will want to "unroll" the elements of these matrices and put them in one long vector:

```octave
thetaVector = [ Theta1(:); Theta2(:); Theta3(:); ]
deltaVector = [ D1(:); D2(:); D3(:); ]
```

If the dimensions of Theta1 is 10×11, Theta2 is 10×11, and Theta3 is 1×11, then we can get back our original matrices from the "unrolled" versions as follows:

```octave
Theta1 = reshape(thetaVector(1:110),10,11)
Theta2 = reshape(thetaVector(111:220),10,11)
Theta3 = reshape(thetaVector(221:231),1,11)
```

