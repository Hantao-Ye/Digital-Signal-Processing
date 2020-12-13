# Chapter 2 Discrete-Time Signals and Systems

## 2-1 Classification of Discrete-Time Signal and System

### Energy and Power Signals

$$
\begin{aligned}
    E &= \sum_{-\infty}^{\infty}{\|x[n]\|^2}\\[2ex]
    P &= \lim_{N\to\infty}\frac{1}{2N+1}\sum_{x = -N}^{N}{\|x[n]\|^2}
\end{aligned}
$$

### Periodic Signals

$$
x(n+N) = x(n)
$$

### Even and Odd Signals

$$
\begin{aligned}
    \text{Even}:\quad x[-n] &= x[n]\\[2ex]
    \text{Odd}:\quad x[-n] &= -x[n]
\end{aligned}
$$

### Systems

- **FIR**: **finite** impulse response system
- **IIR**: **infinite** impulse response system

> $x[n]\to \delta[n]\qquad y[n]\to h[n]$

## 2-2 Properties of Discrete-Time Signals

### Linear Property

$$
\begin{aligned}
    x_1[n]\rightarrow y_1[n] &\qquad x_2[n]\rightarrow y_2[n]\\[2ex]
    ax_1[n]+bx_2[n]&\longrightarrow ay_1[n]+by_2[n]
\end{aligned}
$$

### Displacement Invariant Property

$$
\begin{aligned}
    x[n]&\rightarrow y[n]\\[2ex]
    x[n-n_0]&\rightarrow y[n-n_0]
\end{aligned}
$$

### Causality

The output of the system at some time instant only depends on the time before.

In other words,

$$
h(n) = 0\qquad n<0
$$

### Stability

The input is bounded as well as the output is bounded

$$
\begin{aligned}
    \|x[n]\|\leq M_x<\infty\\[2ex]
    \|y[n]\|\leq M_y<\infty
\end{aligned}
$$

## 2-3 Convolution of Discrete-Time Systems

$$
\begin{aligned}
    y[n] &= x[n]*h[n]\\[2ex]
         &= \sum_{k=-\infty}^{\infty}{x[n]h[n-k]}   
\end{aligned}
$$



## 2-4 Correlation Sequences

the **cross correlation** of two energy $x(n)$ and $y(n)$ is defined as 

$$
r_{xy}(l)=\sum_{n=-\infty}^{\infty}{x(n)y(n-l)}
$$


### Properties

- $r_{yx}(l) = r_{xy}(-l)$
- $r_{xx}(l)=\sum_{n = -\infty}^{\infty}{x(n)x(n-l)}$
- $r_{xx}(l)=r_{xx}(-l)$
- $r_{xy}(l)=x(l)*y(-l)$

### Normalized Correlation Sequences

the correlation sequences are often normalized to the range $[-1,1]$

$$
\rho_{xy}(l) =\frac{r_{xy}(l)}{\sqrt{r_{xx}(0)r_{yy}(0)}}
$$

### Correlation of Periodic Sequences

$$
\begin{aligned}
    r_{xy}(l) = \frac{1}{N}\sum_{n=0}^{N-1}{x(n)y(n-l)}\\[2ex]
    r_{xx}(l) = \frac{1}{N}\sum_{n=0}^{N-1}{x(n)x(n-l)}
\end{aligned}
$$

### Detection of Hidden Periodicity

For a periodic signal $s(n)$, suppose that the signal is buried in noise. Let $\omega(n)$ be the zero-mean white noise. What can we observe is the noisy signal $x(n)$

$$
x(n) = s(n)+\omega(n)
$$

Calculate the autocorrelation sequence of $x(n)$

$$
r_{xx}(l) = r_{ss}(l)+r_{s\omega}+r_{\omega s}+r_{\omega\omega}(l)
$$

Since $\omega(n)$ is a zero-mean white noise signal

$$
r_{s\omega}(l) = 0\qquad r_{\omega s}(l)=0 \qquad r_{s\omega}(l)=0\qquad r_{\omega\omega}(l) = \sigma^2\delta(l)
$$

Then we get

$$
r_{xx}(l) =r_{ss}(l)+\sigma^2\delta(l)
$$