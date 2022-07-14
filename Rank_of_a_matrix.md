# Rank of a maxtrix 
## 1. How to compute rank of a matrix
A matrix is a group of vectors that have the same dimensions. Rank of a matrix is **the number of vector that is not a linear combination of previous vectors in the group**. Let's take a look at the following examples.

$$
\left(\begin{array}{cc}
1 & 1 \\ 
1 & 2
\end{array}\right)
&rarr; R_k = 2
$$

$$
\left(\begin{array}{cc}
1 & 2\\
1 & 2\\
\end{array}\right)
&rarr; R_k = 1
$$

$$
\left(\begin{array}{cc}
0 & 0\\
0 & 0\\
\end{array}\right)
&rarr; R_k = 0
$$

$$
A = \left(\begin{array}{ccccc}
1&1&2&4&2\\
2&1&3&5&4\\
1&1&2&4&2\\
0&1&1&3&0
\end{array}\right)
&rarr; R_k = 2
$$ 

Interpretation:  

In matrix A, vectors $a_1$ & $a_2$ are not a linear combination of other previous vector in the group

$\mathbf{a_1 = 1a_1 +0a_2 + 0a_3 + 0a_4 + 0a_5}$

$\mathbf{a_2 = 0a_1 +1a_2 + 0a_3 + 0a_4 + 0a_5}$ 

$\mathbf{a_3 = 1a_1 +1a_2 + 0a_3 + 0a_4 + 0a_5}$ 

$\mathbf{a_4 = 1a_1 +0a_2 + 3a_3 + 0a_4 + 0a_5}$ 

$\mathbf{a_5 = 2a_1 +0a_2 + 0a_3 + 0a_4 + 0a_5}$ 


## 2. The application of matrix rank in Machine Learning
