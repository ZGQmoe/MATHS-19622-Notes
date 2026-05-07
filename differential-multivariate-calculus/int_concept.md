# Integral Multivariate Calculus — Master Notes

---

## 1. Double Integrals

---

## 1.1 Double Integrals over Rectangles

Let

$$
R=[a,b]\times[c,d]
$$

and $f(x,y)$ continuous.

Double integral:

$$
\iint_R f(x,y)\,dx\,dy
$$

### Interpretation

- $f(x,y) \ge 0$ → **volume under surface**
- General case → **signed volume**

---

## 1.2 Discrete Riemann Sum (Definition)

Partition:

$$
a=x_1<\cdots<x_N=b, \quad c=y_1<\cdots<y_M=d
$$

Small rectangles:

$$
R_{jk}=[x_j,x_{j+1}]\times[y_k,y_{k+1}]
$$

Lengths:

$$
\Delta x_j, \quad \Delta y_k
$$

Sample point:

$$
(\xi_j,\eta_k) \in R_{jk}
$$

Approximation:

$$
\delta V_{jk} \approx f(\xi_j,\eta_k)\Delta x_j\Delta y_k
$$

Total sum:

$$
\iint_R f(x,y)\,dx\,dy
\approx
\sum_{j=1}^{N-1}\sum_{k=1}^{M-1}
f(\xi_j,\eta_k)\Delta x_j\Delta y_k
$$

Limit definition:

$$
\iint_R f(x,y)\,dx\,dy
=
\lim_{\max(\Delta x_j,\Delta y_k)\to 0}
\sum f(\xi_j,\eta_k)\Delta x_j\Delta y_k
$$

---

## 1.3 Fubini’s Theorem

If $f$ continuous on $R$:

$$
\iint_R f(x,y)\,dx\,dy
=
\int_a^b \left(\int_c^d f(x,y)\,dy\right) dx
=
\int_c^d \left(\int_a^b f(x,y)\,dx\right) dy
$$

### Meaning

- Convert **2D integral → 1D integrals**
- Order can be swapped (rectangular domain)
- Evaluate **inner first**

---

## 1.4 Non-Rectangular Regions

General form:

$$
\iint_D f(x,y)\,dA
$$

Limits depend on region geometry.

---

## 1.5 Type I Region (Vertical Slices)

Region defined by:

$$
a \le x \le b, \quad t_L(x) \le y \le t_U(x)
$$

Integral:

$$
\iint_D f(x,y)\,dA
=
\int_a^b \int_{t_L(x)}^{t_U(x)} f(x,y)\,dy\,dx
$$

### Interpretation

- Fix $x$
- $y$ varies between lower and upper curves

---

## 1.6 Type II Region (Horizontal Slices)

Region defined by:

$$
c \le y \le d, \quad s_L(y) \le x \le s_R(y)
$$

Integral:

$$
\iint_D f(x,y)\,dA
=
\int_c^d \int_{s_L(y)}^{s_R(y)} f(x,y)\,dx\,dy
$$

### Interpretation

- Fix $y$
- $x$ varies between left and right curves

---

## 1.7 Choosing Integration Order

| Type | Outer Variable | Inner Variable | Limits |
|------|------|------|------|
| Type I | $x$ | $y$ | $t_L(x) \to t_U(x)$ |
| Type II | $y$ | $x$ | $s_L(y) \to s_R(y)$ |

### Strategy

- Choose simpler limits
- Avoid splitting region if possible

---

## 1.8 Reversing Order of Integration

To reverse the order:

1. Identify original bounds  
2. Rewrite the region  
3. Convert boundary equations  
4. Express new limits  

---

### Example

$$
\int_0^4 \int_{\sqrt{y}}^2 f(x,y)\,dx\,dy
$$

Original bounds:

$$
0\le y\le 4,
\qquad
\sqrt{y}\le x\le 2
$$

Rewrite boundary:

$$
x \ge \sqrt{y}
\Longleftrightarrow
y \le x^2
$$

New bounds:

$$
0\le x\le 2,
\qquad
0\le y\le x^2
$$

Therefore:

$$
\int_0^4 \int_{\sqrt{y}}^2 f(x,y)\,dx\,dy
=
\int_0^2 \int_0^{x^2} f(x,y)\,dy\,dx
$$

---

### Key Idea

- Original: horizontal slicing ($dx\,dy$)
- Reversed: vertical slicing ($dy\,dx$)
- Same region, different description