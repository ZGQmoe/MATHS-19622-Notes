# Integral Multivariate Calculus — Master Notes

## 1. Double Integrals

### 1.1 Double Integrals over Rectangles

Let

```math
R=[a,b]\times[c,d]
```

where `$f(x,y)$` is continuous.

Double integral:

```math
\iint_R f(x,y)\,dA
```

or

```math
\iint_R f(x,y)\,dx\,dy
```

#### Meaning

- `$f(x,y)\ge 0$` → **volume under surface**
- General case → **signed volume**

---

### 1.2 Discrete Riemann Sum Definition

Partition:

```math
a=x_1<\cdots<x_N=b
```

```math
c=y_1<\cdots<y_M=d
```

Small rectangles:

```math
R_{jk}=[x_j,x_{j+1}]\times[y_k,y_{k+1}]
```

Widths:

```math
\Delta x_j=x_{j+1}-x_j
```

```math
\Delta y_k=y_{k+1}-y_k
```

Sample point:

```math
(\xi_j,\eta_k)\in R_{jk}
```

Small volume:

```math
\Delta V_{jk}\approx f(\xi_j,\eta_k)\Delta x_j\Delta y_k
```

Approximation:

```math
\iint_R f(x,y)\,dA
\approx
\sum_{j=1}^{N-1}\sum_{k=1}^{M-1}
f(\xi_j,\eta_k)\Delta x_j\Delta y_k
```

Limit definition:

```math
\iint_R f(x,y)\,dA
=
\lim_{\max(\Delta x_j,\Delta y_k)\to 0}
\sum_{j=1}^{N-1}\sum_{k=1}^{M-1}
f(\xi_j,\eta_k)\Delta x_j\Delta y_k
```

---

### 1.3 Fubini's Theorem

If `$f$` is continuous on `$R$`, then

```math
\iint_R f(x,y)\,dA
=
\int_a^b
\left(
\int_c^d f(x,y)\,dy
\right)
dx
```

and

```math
\iint_R f(x,y)\,dA
=
\int_c^d
\left(
\int_a^b f(x,y)\,dx
\right)
dy
```

#### Meaning

- **2D integral** → repeated **1D integrals**
- Evaluate **inner integral first**
- Order can be swapped on **rectangular domains**

---

### 1.4 Non-Rectangular Regions

General form:

```math
\iint_D f(x,y)\,dA
```

Limits depend on the geometry of `$D$`.

---

### 1.5 Type I Region: Vertical Slices

Region:

```math
a\le x\le b
```

```math
t_L(x)\le y\le t_U(x)
```

Integral:

```math
\iint_D f(x,y)\,dA
=
\int_a^b
\int_{t_L(x)}^{t_U(x)}
f(x,y)\,dy\,dx
```

#### Meaning

- Fix `$x$`
- `$y$`: **lower curve** → **upper curve**

---

### 1.6 Type II Region: Horizontal Slices

Region:

```math
c\le y\le d
```

```math
s_L(y)\le x\le s_R(y)
```

Integral:

```math
\iint_D f(x,y)\,dA
=
\int_c^d
\int_{s_L(y)}^{s_R(y)}
f(x,y)\,dx\,dy
```

#### Meaning

- Fix `$y$`
- `$x$`: **left curve** → **right curve**

---

### 1.7 Choosing Integration Order

| Region type | Outer variable | Inner variable | Inner limits |
|---|---|---|---|
| **Type I** | `$x$` | `$y$` | `$t_L(x)\to t_U(x)$` |
| **Type II** | `$y$` | `$x$` | `$s_L(y)\to s_R(y)$` |

#### Strategy

- Choose simpler limits
- Avoid splitting region
- Inner limits depend on outer variable

---

### 1.8 Reversing Order of Integration

#### Procedure

1. Read original bounds
2. Describe/sketch region
3. Convert boundary equations
4. Rewrite limits in new order

---

#### Example

Original integral:

```math
\int_0^4
\int_{\sqrt{y}}^2
f(x,y)\,dx\,dy
```

Original bounds:

```math
0\le y\le 4
```

```math
\sqrt{y}\le x\le 2
```

Boundary conversion:

```math
x\ge \sqrt{y}
```

```math
y\le x^2
```

New bounds:

```math
0\le x\le 2
```

```math
0\le y\le x^2
```

Reversed integral:

```math
\int_0^4
\int_{\sqrt{y}}^2
f(x,y)\,dx\,dy
=
\int_0^2
\int_0^{x^2}
f(x,y)\,dy\,dx
```

#### Key Idea

- Original order `$dx\,dy$` → **horizontal slicing**
- New order `$dy\,dx$` → **vertical slicing**
- Same region, different limits