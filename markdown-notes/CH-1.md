# CH-1

[TOC]

## 1 - Continuous Time Signal and System

### Useful Signals

#### Unit Step Function

$$
u(t-t_0)=
\begin{cases}
    0\qquad t<t_0\\[1ex]
    1\qquad t>t_0
\end{cases}
$$

#### Unit Impulse Function

$$
\int_{-\infty}^{\infty}{\delta(t)\mathrm{d}t} = 1
$$

- sampling property: 
  - $$
  \begin{cases}
      \delta(t)=x(0)\delta(t)\\[2ex]
      \int x(t)\delta(t)=x(0)
  \end{cases}
    $$
  - $$
  \begin{cases}
      x(t)\delta(t-t_0)=x(0)\delta(t-t_0)\\[2ex]
      \int x(t)\delta(t-t_0)=x(t_0)
  \end{cases}
    $$
- differentiation and integration
  - $$
  \begin{cases}
      u(t)=\int_{-\infty}^{t}{\delta(\tau)\mathrm{d}\tau}\\[2ex]
      \delta(t)=\frac{\mathrm{d}u(t)}{\mathrm{d}t}
  \end{cases}
    $$

## 2 - Fourier Transformation

$$
F(j\omega)=\int_{-\infty}^{\infty}{f(t)e^{-j\omega t}\mathrm{d}t}\qquad f(t)= \frac{1}{2\pi}\int_{-\infty}^{\infty}{F(j\omega)e^{jn\omega t}\mathrm{d}\omega}
$$

### Useful Fourier Transform Pair

|           Aperiodic Signal           |                    Fourier Signal                    |                              Signal                               |                               Fourier Transform                               | Fourier series coefficients |
| :----------------------------------: | :--------------------------------------------------: | :---------------------------------------------------------------: | :---------------------------------------------------------------------------: | :-------------------------: |
|            $ax(t)+by(t)$             |              $aX(j\omega)+bY(j\omega)$               |          $\sum_{k=-\infty}^{\infty}{a_ke^{j\omega_0 t}}$          |         $2\pi \sum_{k=-\infty}^{\infty}{a_k\delta(\omega-k\omega_0)}$         |            $a_k$            |
|              $x(t-t_0)$              |             $e^{-j\omega t_0}X(j\omega)$             |                         $e^{j\omega_0 t}$                         |                        $2\pi \delta (\omega-\omega_0)$                        |      $a_1=1\;a_k = 0$       |
|        $e^{j\omega_0 t}x(t)$         |               $X(j(\omega-\omega_0))$                |                          $\cos\omega_0t$                          |            $\pi[\delta(\omega-\omega_0)+\delta(\omega+\omega_0)]$             |  $a_1=a_{-1}=1/2\; a_k=0$   |
|               $x^*(t)$               |                   $X^*(-j\omega)$                    |                          $\sin\omega_0t$                          |       $\frac{\pi}{j}[\delta(\omega-\omega_0)-\delta(\omega+\omega_0)]$        | $a_1=-a_{-1}=1/2j\; a_k=0$  |
|               $x(-t)$                |                    $X(-j\omega)$                     |                             $x(t)=1$                              |                             $2\pi\delta(\omega)$                              |       $a_0=1\; a_k=0$       |
|               $x(at)$                |        $\frac{1}{\|a\|}X(\frac{j\omega}{a})$         | $x(t)=\begin{cases}1\quad \|t\|<T_1\\0\quad \|t\|>T_1\end{cases}$ |                       $\frac{2\sin\omega T_1}{\omega}$                        |
|             $x(t)*y(t)$              |                $X(j\omega)Y(j\omega)$                |                      $\frac{\sin Wt}{\pi t}$                      | $X(j\omega)=\begin{cases}1\quad \|\omega\|<W\\0\quad \|\omega\|>W\end{cases}$ |
|              $x(t)y(t)$              |        $\frac{1}{2\pi}X(j\omega)*Y(j\omega)$         |                           $\delta (t)$                            |                                       1                                       |
| $\frac{\mathrm{d}}{\mathrm{d}t}x(t)$ |                 $j\omega X(j\omega)$                 |                              $u(t)$                               |                     $\frac{1}{j\omega}+\pi\delta(\omega)$                     |
| $\int_{-\infty}^t{x(t)\mathrm{d}t}$  | $\frac{1}{j\omega}X(j\omega)+\pi X(0)\delta(\omega)$ |                          $\delta(t-t_0)$                          |                               $e^{j\omega t_0}$                               |
|               $tx(t)$                |   $j\frac{\mathrm{d}}{\mathrm{d}\omega}X(j\omega)$   |                           $e^{-at}u(t)$                           |                             $\frac{1}{a+j\omega}$                             |
|               $X(jt)$                |                  $2\pi x(-\omega)$                   |                          $te^{-at}u(t)$                           |                           $\frac{1}{(a+j\omega)^2}$                           |

### Energy Theorem

$$
W=\int_{-\infty}^{\infty}{|x(t)|^2\mathrm{d}t}=\frac{1}{2\pi}\int_{-\infty}^{\infty}\Big|X(j\omega)\Big|^2\mathrm{d}\omega
$$

## 3 - Discrete Linear Displacement Invariant System

### Species

- FIR: finite impulse response system
- IIR: infinite impulse response system

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

### Convolution

$$
\begin{aligned}
    y[n] &= x[n]h[n]\\[2ex]
         &= \sum_{k=-\infty}^{\infty}{x[n]h[n-k]}   
\end{aligned}
$$

## 4 - Sampling

### Normalized Frequency

the signal with an analog frequency of $F$ is sampled at a rate of $F_s$

then the relationship between the **normalized frequency $f$** and the **analog frequency $F$** is

$$
f = \frac{F}{F_s}
$$

### Sampling Theorem

- If maximum frequency of the signal is known to be $F_{max}$, the **minimum sampling rate** would be

$$
\text{Nyquist Rate} = 2\times F_{max}
$$
- If the sampling rate is know to be $F_s$, the maximum frequency in the signal must not exceed

$$
\text{Nyquist Rate} = \frac{1}{2}F_{S}
$$