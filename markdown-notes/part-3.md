# Part III The z-Transform

## 3-1 The Direct z-Transform

the z-transform of a general discrete-time signal $x[n]$ is defined as

$$
X(z) = \sum_{n=-\infty}^{\infty}{x[n]z^{-n}}
$$

## 3-2 The Inverse z-Transform

$$
X(z) = \sum_{i=1}^{m} \frac{A_i}{1-a_iz^{-1}}
$$

- ROC outside the pole: $\frac{A_i}{1-a_iz^{-1}}\leftrightarrow A_i a_i^nu[n]$
- ROC outside the pole: $\frac{A_i}{1-a_iz^{-1}}\leftrightarrow -A_i a_i^nu[-n-1]$

### Power-series Expansion

$$
X(z) = \sum_{n=-\infty}^{\infty}{x[n]z^{-n}}
$$

The coefficients in this power series are the sequence values $x[n]$ since $\delta[n+n_0]\leftrightarrow z^{n_0}$

## 3-3 Properties of the z-Transform

### Linearity

$$
ax_1[n]+bx_2[n] \longleftrightarrow aX_1(z)+bX_2(z)
$$

with the ROC containing $R_1\cap R_2$

### Time Shifting

$$
x[n-k]\longleftrightarrow z^{-k}X(z)
$$

with ROC = R, except for the possible addition or deletion of the origin or infinity

> For $n_0>0$, poles will be introduced at $z=0$
> For $n_0<0$, zeros will be introduced at $z=0$

### Scaling in the z-Domain

$$
a^nx[n]\longleftrightarrow X(a^{-1} z)
$$

with ROC = $|a|R$

### Time Reversal

$$
x[-n]\longleftrightarrow X(z^{-1})
$$

with ROC = $\frac{1}{R}$

### Differentiation in the z-Domain

$$
nx[n]\longleftrightarrow -z\frac{\mathrm{d}X(z)}{\mathrm{d}z}
$$

with ROC = R

### Convolution Property

$$
x_1[n]*x_2[n]\longleftrightarrow X_1(z)X_2(z)
$$

### Initial-Value and Final-Value Theorems

if $x[n]$ is a casual sequence, then

$$
x[0] = \lim_{z\to\infty}{X(z)}
$$

|        Time-Domain        |                              z-Domain                              |      ROC      |
| :-----------------------: | :----------------------------------------------------------------: | :-----------: |
|        $\delta[n]$        |                                $1$                                 |     all z     |
|          $u[n]$           |                        $\frac{1}{1-z^{-1}}$                        |   $\|z\|>1$   |
|         $a^nu[n]$         |                       $\frac{1}{1-az^{-1}}$                        | $\|z\|>\|a\|$ |
|       $-a^nu[-n-1]$       |                       $\frac{1}{1-az^{-1}}$                        | $\|z\|<\|a\|$ |
|        $na^nu[n]$         |                  $\frac{az^{-1}}{(1-az^{-1})^2}$                   | $\|z\|>\|a\|$ |
|      $-na^nu[-n-1]$       |                  $\frac{az^{-1}}{(1-az^{-1})^2}$                   | $\|z\|<\|a\|$ |
|  $\cos(\omega_0 n)u[n]$   |   $\frac{1-z^{-1}\cos(\omega_0)}{1-2z^{-1}\cos\omega_0+z^{-2}}$    |   $\|z\|>1$   |
|  $\sin(\omega_0 n)u[n]$   |    $\frac{z^{-1}\sin(\omega_0)}{1-2z^{-1}\cos\omega_0+z^{-2}}$     |   $\|z\|>1$   |
| $a^n\cos(\omega_0 n)u[n]$ | $\frac{1-az^{-1}\cos(\omega_0)}{1-2az^{-1}\cos\omega_0+a^2z^{-2}}$ |   $\|z\|>1$   |
|  $\sin(\omega_0 n)u[n]$   |  $\frac{az^{-1}\sin(\omega_0)}{1-2az^{-1}\cos\omega_0+a^2z^{-2}}$  |   $\|z\|>1$   |

## 3-4 Analysis of LTI System Using z-Transform

$$
Y(z) = X(z)H(z)
$$

where $H(z)$ is the system function/transfer function

### Causality

**Definition**: if the ROC of its system function is the exterior of a circle, including infinity

A system with rational system with rational system function $H(z)$ is casual if and only if:

- the ROC is the exterior of a circle outside the outermost pole
- for $H(z)$, the order of numerator cannot be greater than the order of the denominator

### Stability

**Definition**: the ROC of its system function $H(z)$ includes the unit circle, $|z|=1$

A system with rational system function $H(z)$ is stable if and only if all of the poles of $H(z)$ lie inside the i=unit circle

## 3-5 The Inverse z-Transform Methods

- Inspection Method
  - using the properties and transform paris to get the inverse transform directly

- Power Series Method
  - has only few terms
  - can be found easily using Taylor series expansion/long division

- **Partial Fraction Expansion Method**
  - Simple poles
  - Repeated poles