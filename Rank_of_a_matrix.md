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

In matrix A, vectors $\mathbf{a_1}$ & $\mathbf{a_2}$ are not a linear combination of other previous vector in the group

$\mathbf{a_1 = 1a_1 +0a_2 + 0a_3 + 0a_4 + 0a_5}$

$\mathbf{a_2 = 0a_1 +1a_2 + 0a_3 + 0a_4 + 0a_5}$ 

$\mathbf{a_3 = 1a_1 +1a_2 + 0a_3 + 0a_4 + 0a_5}$ 

$\mathbf{a_4 = 1a_1 +0a_2 + 3a_3 + 0a_4 + 0a_5}$ 

$\mathbf{a_5 = 2a_1 +0a_2 + 0a_3 + 0a_4 + 0a_5}$ 


## 2. The application of matrix rank in Machine Learning

In Machine Learning, there are many type of data (e.g., text, time-series, audio, images, and video). Data is converted into a matrix. Rank of a matrix is important because it can be used for matrix reduction. Let's decompose matrix A:
$$A = A' * R$$, where $A'$ is a ingredient matrix determined by rank, and $R$ is recepies which is not important to repsent the original input $A$.

In bigdata,  it is important to reduce the dimension of the input data. If $A'$ can be used to represent the original input A, it would be great. Let's decompose the matrix $A$ in the example above.

$$
A = A' * R
$$

$$
\left(\begin{array}{ccccc}
1&1&2&4&2\\
2&1&3&5&4\\
1&1&2&4&2\\
0&1&1&3&0
\end{array}\right) =  
\left(\begin{array}{cc}
1&1\\
2&1\\
1&1\\
0&1\\
\end{array}\right) * 
\left(\begin{array}{ccccc}
1&0&1&1&2\\
0&1&1&3&0\\
\end{array}\right)
$$

Now, let's analyze the ratio compression after decomposing input $A$.
Dimension of $A(4,5), A'(4,2), R(2,5)$ we reduce the total element in input $A$ from $20$ to $(8+10)$, it is that much. However, when generalizing the dimension with bigdata input. We have $A(N,P), A'(N,k), R(k,P)$, where $P$ is the number of features, $k$ is the rank of $A'$.  Then the total element of $A'$ and $R$ is 

$$
N*k + k*P = k(N+P)
$$

So the reduction:

$$
	\frac{k(N+P)}{NP}
$$

If $N = 10000, P= 10, k =5$, then the compression is nearly 50%
