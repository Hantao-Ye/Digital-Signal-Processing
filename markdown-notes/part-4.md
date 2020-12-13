# Part IV The Discrete Fourier Transform

## 4-1 N-Point DFT

The formula for the DFT is given by

$$
X(k) = \sum_{n=0}^{N-1}x(n)W_N^{nk}\quad W_N = e^{-\frac{2j\pi}{N}}
$$

and also could be expressed as the matrix form

$$
\bold{x}_N=
\begin{bmatrix}
x[0]\\[1ex]
x[1]\\[1ex]
\cdots\\[1ex]
x[N-1]   
\end{bmatrix}\quad \bold{W}_N = 
\begin{bmatrix}
    1&1&1&\cdots&1\\[1ex]
    1&W_N^1&W_N^2&\cdots&W_N^{N-1}\\[1ex]
    1&W_N^2&W_N^4&\cdots&W_N^{2(N-1)}\\[1ex]
    \vdots&\vdots&\vdots&\ddots&\vdots\\[1ex]
    1&W_N^{N-1}&W_N^{2(N-1)}&\cdots&W_N^{(N-1)(N-1)}\\[1ex]
\end{bmatrix}
$$

where the N-point DFT could be expressed in the matrix form as

$$
\bold{X}_N = \bold{W}_N\bold{x}_N
$$

## 4-2 Circular or Linear Convolution Using DFT

For example, do the circular convolution of the following teo sequences

$$
x_1[n] = \{2,1,2,1\}\qquad x_2[n] = \{1,2,3,4\}
$$

Then we can get $x_3$ by

$$
x_3[n] = 
\begin{bmatrix}
1&4&3&2\\[1ex]
2&1&4&3\\[1ex]
3&2&1&4\\[1ex]
4&3&2&1   
\end{bmatrix}
\begin{bmatrix}
    2\\[1ex]
    1\\[1ex]
    2\\[1ex]
    1
\end{bmatrix}=\{14,16,14,16\}
$$

in other way

$$
X_1(k) = 2+W_4^k+2W_4^{2k}+W_4^{3k}\qquad X_2(k) = 1+2W_4^k+3W_4^{2k}+4W_4^{3k}
$$

then according to $Y(k)= X_1(k)X_2(k)$

$$
\begin{aligned}
Y(k) = 2&+5W_4^k+10W_4^{2k}+16W_4^{3k}\\[2ex]
       12W_4^{4k}&+11W_4^{5k}+4W_4^{6k}=14+16W_4^k+14W_4^{2k}+16W_4^{3k}\\[2ex]
\end{aligned}
$$