# CH-2

[TOC]

## 1 - Correlation Sequences

the **cross correlation** of two energy $x(n)$ and $y(n)$ is defined as 

$$
r_{xy}(l)=\sum_{n=-\infty}^{\infty}{x(n)y(n-l)}
$$


### Properties

- $r_{yx}(l) = r_{xy}(-l)$
- $r_{xx}(l)=\sum_{n = \infty}^{\infty}{x(n)x(n-l)}$
- $r_{xx}(l)=r_{xx}(-l)$
- $r_{xy}(l)=x(l)*y(-l)$

### Normalized Correlation Sequences

the correlation sequences are often normalized to the range $[-1,1]$

$$
\rho_{xy}(l) =\frac{r_{xy}(l)}{\sqrt{r_{xx}(0)r_{yy}(0)}}
$$

## 2 - Detection of Hidden Periodicity

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