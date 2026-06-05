# Integral Multivariate Calculus — Master Notes

## 1. Double Integrals

### 1.1 Double Integrals over Rectangles

Let

$$
R=[a,b]\times[c,d]
$$

where \( f(x,y) \) is continuous.

The double integral is

$$
\iint_R f(x,y)\,dA
$$

or equivalently

$$
\iint_R f(x,y)\,dx\,dy
$$

#### Meaning

- \( f(x,y)\ge 0 \): **volume under surface**
- General case: **signed volume**

---

### 1.2 Discrete Riemann Sum Definition

Partition the rectangle:

$$
a=x_1<\cdots<x_N=b
$$

$$
c=y_1<\cdots<y_M=d
$$

Small rectangles:

$$
R_{jk}=[x_j,x_{j+1}]\times[y_k,y_{k+1}]
$$

Widths:

$$
\Delta x_j=x_{j+1}-x_j
$$

$$
\Delta y_k=y_{k+1}-y_k
$$

Sample point:

$$
(\xi_j,\eta_k)\in R_{jk}
$$

Small volume:

$$
\Delta V_{jk}\approx f(\xi_j,\eta_k)\Delta x_j\Delta y_k
$$

Approximation:

$$
\iint_R f(x,y)\,dA
\approx
\sum_{j=1}^{N-1}\sum_{k=1}^{M-1}
f(\xi_j,\eta_k)\Delta x_j\Delta y_k
$$

Limit definition:

$$
\iint_R f(x,y)\,dA
=
\lim_{\max(\Delta x_j,\Delta y_k)\to 0}
\sum_{j=1}^{N-1}\sum_{k=1}^{M-1}
f(\xi_j,\eta_k)\Delta x_j\Delta y_k
$$

---

### 1.3 Fubini's Theorem

If \( f \) is continuous on \( R \), then

$$
\iint_R f(x,y)\,dA
=
\int_a^b
\left(
\int_c^d f(x,y)\,dy
\right)
dx
$$

and

$$
\iint_R f(x,y)\,dA
=
\int_c^d
\left(
\int_a^b f(x,y)\,dx
\right)
dy
$$

#### Meaning

- **2D integral** becomes repeated **1D integrals**
- Inner integral first
- Order can be swapped on rectangular domains

---

### 1.4 Non-Rectangular Regions

For a general region \( D \),

$$
\iint_D f(x,y)\,dA
$$

The limits depend on the geometry of \( D \).

---

### 1.5 Type I Region: Vertical Slices

Region:

$$
a\le x\le b
$$

$$
t_L(x)\le y\le t_U(x)
$$

Integral:

$$
\iint_D f(x,y)\,dA
=
\int_a^b
\int_{t_L(x)}^{t_U(x)}
f(x,y)\,dy\,dx
$$

#### Meaning

- Fix \( x \)
- \( y \) varies from **lower curve** to **upper curve**

---

### 1.6 Type II Region: Horizontal Slices

Region:

$$
c\le y\le d
$$

$$
s_L(y)\le x\le s_R(y)
$$

Integral:

$$
\iint_D f(x,y)\,dA
=
\int_c^d
\int_{s_L(y)}^{s_R(y)}
f(x,y)\,dx\,dy
$$

#### Meaning

- Fix \( y \)
- \( x \) varies from **left curve** to **right curve**

---

### 1.7 Choosing Integration Order

| Region type | Outer variable | Inner variable | Inner limits |
|---|---|---|---|
| **Type I** | \( x \) | \( y \) | \( t_L(x) \to t_U(x) \) |
| **Type II** | \( y \) | \( x \) | \( s_L(y) \to s_R(y) \) |

#### Strategy

- Choose simpler limits
- Avoid splitting the region if possible
- Inner limits usually depend on outer variable

---

### 1.8 Reversing Order of Integration

#### Procedure

1. Read the original bounds
2. Sketch or describe the region
3. Convert boundary equations
4. Rewrite limits in the new order

---

#### Example

Original integral:

$$
\int_0^4
\int_{\sqrt{y}}^2
f(x,y)\,dx\,dy
$$

Original bounds:

$$
0\le y\le 4
$$

$$
\sqrt{y}\le x\le 2
$$

Boundary conversion:

$$
x\ge \sqrt{y}
$$

$$
y\le x^2
$$

New bounds:

$$
0\le x\le 2
$$

$$
0\le y\le x^2
$$

Reversed integral:

$$
\int_0^4
\int_{\sqrt{y}}^2
f(x,y)\,dx\,dy
=
\int_0^2
\int_0^{x^2}
f(x,y)\,dy\,dx
$$

#### Key Idea

- Original order \( dx\,dy \): **horizontal slicing**
- New order \( dy\,dx \): **vertical slicing**
- Same region, different limits