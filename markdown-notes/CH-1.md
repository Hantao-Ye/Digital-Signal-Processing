# Part I Sampling

## 1-1 Sampling of Analog Signal

Consider a continuous-time signal $x_a(t)$ and a discrete-time signal $x[n]$ is obtained by periodic sampling. 

Let $T$ be the **sampling period**, then we define $x[n]= x_a(nT)$

If $x_a(t) = A\cos(2\pi Ft+\phi)$ and the signal is sampled at a rate of $F_s=\frac{1}{T}$

then $x[n] = A\cos(2\pi FTn+\phi)=A\cos(2\pi nf+\phi)$

### Normalized Frequency

the signal with an analog frequency of $F$ is sampled at a rate of $F_s$

then the relationship between the **normalized frequency $f$** and the **analog frequency $F$** is

$$
f = \frac{F}{F_s}
$$

## 1-2 Sampling Theorem

- If maximum frequency of the signal is known to be $F_{max}$, the **minimum** sampling rate would be

$$
\text{Nyquist Rate} = 2\times F_{max}
$$
- If the sampling rate is know to be $F_s$, the **maximum** frequency in the **signal** must not exceed

$$
\text{Nyquist Rate} = \frac{1}{2}F_{S}
$$