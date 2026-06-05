# Integral Multivariate Calculus — Master Notes

Based on MATH19622 Part II Integral Multivariate Calculus.  
Main scope: double/triple integrals, Jacobians, curves/surfaces, line/surface integrals, conservative fields, Green/Stokes/Divergence theorem, Maxwell equations.

---

## 1. Double Integrals

### 1.1 Double Integrals over Rectangles

Let

```math
R=[a,b]\times[c,d]
```

where $f(x,y)$ is continuous.

Double integral:

```math
\iint_R f(x,y)\,dA
```

or

```math
\iint_R f(x,y)\,dx\,dy
```

#### Meaning

- $f(x,y)\ge 0$ → **volume under surface**
- General case → **signed volume**

---

### 1.2 Riemann Sum Definition

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

If $f$ is continuous on $R$, then

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

### 1.4 Application: Total Charge

If surface charge density is $\rho(x,y)$:

```math
Q=\iint_R \rho(x,y)\,dA
```

---

### 1.5 Non-Rectangular Regions

General form:

```math
\iint_D f(x,y)\,dA
```

Limits depend on the geometry of $D$.

#### Domain Decomposition

If $D$ is split into non-overlapping subdomains $D_m$:

```math
\iint_D f\,dA
=
\sum_{m=1}^{N}
\iint_{D_m} f\,dA
```

---

### 1.6 Type I Region: Vertical Slices

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

- Fix $x$
- $y$: **lower curve** → **upper curve**

---

### 1.7 Type II Region: Horizontal Slices

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

- Fix $y$
- $x$: **left curve** → **right curve**

---

### 1.8 Choosing Integration Order

| Region type | Outer variable | Inner variable | Inner limits |
|---|---|---|---|
| **Type I** | $x$ | $y$ | $t_L(x)\to t_U(x)$ |
| **Type II** | $y$ | $x$ | $s_L(y)\to s_R(y)$ |

#### Strategy

- Choose simpler limits
- Avoid splitting region
- Inner limits depend on outer variable

---

### 1.9 Reversing Order of Integration

#### Procedure

1. Read original bounds
2. Describe/sketch region
3. Convert boundary equations
4. Rewrite limits in new order

#### Key Idea

- Original order $dx\,dy$ → **horizontal slicing**
- New order $dy\,dx$ → **vertical slicing**
- Same region, different limits

---

## 2. Change of Variables and Jacobians

### 2.1 General 2D Change of Variables

Let

```math
x=x(u,v),\qquad y=y(u,v)
```

Jacobian:

```math
J=
\frac{\partial(x,y)}{\partial(u,v)}
=
\begin{vmatrix}
\frac{\partial x}{\partial u} & \frac{\partial x}{\partial v} \\
\frac{\partial y}{\partial u} & \frac{\partial y}{\partial v}
\end{vmatrix}
```

Area element:

```math
dA=|J|\,du\,dv
```

Change of variables:

```math
\iint_D f(x,y)\,dA
=
\iint_{D'}
f(x(u,v),y(u,v))
\left|
\frac{\partial(x,y)}{\partial(u,v)}
\right|
du\,dv
```

#### Meaning

- **Jacobian** = local area scale factor
- Absolute value gives area scaling
- Sign gives orientation

---

### 2.2 Polar Coordinates

Transform:

```math
x=r\cos\theta
```

```math
y=r\sin\theta
```

Jacobian:

```math
\left|
\frac{\partial(x,y)}{\partial(r,\theta)}
\right|
=r
```

Area element:

```math
dA=r\,dr\,d\theta
```

Double integral:

```math
\iint_D f(x,y)\,dA
=
\iint_{D'}
f(r\cos\theta,r\sin\theta)\,r\,dr\,d\theta
```

#### Common Bounds

Circle radius $a$:

```math
0\le r\le a
```

```math
0\le \theta\le 2\pi
```

Sector:

```math
\alpha\le \theta\le \beta
```

```math
r_0(\theta)\le r\le r_1(\theta)
```

---

## 3. Triple Integrals

### 3.1 Triple Integral

For region $V\subset\mathbb R^3$:

```math
\iiint_V f(x,y,z)\,dV
```

Cartesian volume element:

```math
dV=dx\,dy\,dz
```

#### Meaning

- Integral over **3D volume**
- If $f=1$, integral gives **volume**

---

### 3.2 Triple Integral over a Box

Let

```math
B=[a,b]\times[c,d]\times[e,f]
```

Then

```math
\iiint_B F(x,y,z)\,dV
=
\int_a^b
\int_c^d
\int_e^f
F(x,y,z)\,dz\,dy\,dx
```

---

### 3.3 Cylindrical Coordinates

Transform:

```math
x=\rho\cos\phi
```

```math
y=\rho\sin\phi
```

```math
z=z
```

Jacobian:

```math
\left|
\frac{\partial(x,y,z)}{\partial(\rho,\phi,z)}
\right|
=\rho
```

Volume element:

```math
dV=\rho\,d\rho\,d\phi\,dz
```

Use when:
- circular cylinder
- radial symmetry around $z$-axis

---

### 3.4 Spherical Coordinates

Transform:

```math
x=r\sin\theta\cos\phi
```

```math
y=r\sin\theta\sin\phi
```

```math
z=r\cos\theta
```

Jacobian:

```math
\left|
\frac{\partial(x,y,z)}{\partial(r,\theta,\phi)}
\right|
=
r^2\sin\theta
```

Volume element:

```math
dV=r^2\sin\theta\,dr\,d\theta\,d\phi
```

Use when:
- sphere
- cone
- radial symmetry from origin

---

## 4. Curves and Surfaces in 3D

### 4.1 Curves

#### 4.1.1 Curve Types

- **Open curve**: endpoints different
- **Closed curve**: start point = end point
- **Oriented curve**: direction is specified

#### 4.1.2 Implicit Curve

A curve in $\mathbb R^3$ can be intersection of two surfaces:

```math
f(x,y,z)=0
```

```math
g(x,y,z)=0
```

#### 4.1.3 Parametric Curve

```math
\mathbf r(t)=[x(t),y(t),z(t)]
```

```math
a\le t\le b
```

Closed curve condition:

```math
\mathbf r(a)=\mathbf r(b)
```

---

### 4.2 Tangent Vector and Tangent Line

Tangent vector:

```math
\mathbf r'(t)=[x'(t),y'(t),z'(t)]
```

Tangent line at $t=t_0$:

```math
\mathbf q(w)=\mathbf r(t_0)+w\mathbf r'(t_0)
```

Condition:

```math
\mathbf r'(t_0)\ne \mathbf 0
```

---

### 4.3 Surfaces

#### 4.3.1 Explicit Surface

```math
z=f(x,y)
```

#### 4.3.2 Implicit Surface

```math
\Phi(x,y,z)=0
```

#### 4.3.3 Parametric Surface

```math
\mathbf r(s,t)=[x(s,t),y(s,t),z(s,t)]
```

---

### 4.4 Surface Tangents and Normals

For parametric surface $\mathbf r(s,t)$:

```math
\frac{\partial\mathbf r}{\partial s}
```

and

```math
\frac{\partial\mathbf r}{\partial t}
```

are tangent vectors.

Normal vector:

```math
\mathbf N=
\frac{\partial\mathbf r}{\partial s}
\times
\frac{\partial\mathbf r}{\partial t}
```

For implicit surface $\Phi(x,y,z)=0$:

```math
\nabla\Phi
```

is normal to the surface.

Tangent plane at $\mathbf r=\mathbf r_0$:

```math
\nabla\Phi(\mathbf r_0)\cdot(\mathbf r-\mathbf r_0)=0
```

Unit normal:

```math
\hat{\mathbf n}
=
\frac{\nabla\Phi}{|\nabla\Phi|}
```

For closed surfaces:
- usually choose **outward normal**

---

## 5. Line Integrals and Conservative Fields

### 5.1 Vector Line Integral

For vector field $\mathbf F$ along curve $C$:

```math
\int_C \mathbf F\cdot d\mathbf r
```

Parametrise:

```math
\mathbf r(t)=\langle x(t),y(t),z(t)\rangle
```

```math
a\le t\le b
```

Then

```math
d\mathbf r=\mathbf r'(t)\,dt
```

Formula:

```math
\int_C \mathbf F\cdot d\mathbf r
=
\int_a^b
\mathbf F(\mathbf r(t))\cdot \mathbf r'(t)\,dt
```

#### Meaning

- Work done along path
- Direction matters

---

### 5.2 Closed Curve Integral

For closed curve $C$:

```math
\oint_C \mathbf F\cdot d\mathbf r
```

Meaning:
- **circulation** around $C$

---

### 5.3 Work

```math
W=\int_C \mathbf F\cdot d\mathbf r
```

---

### 5.4 Ampere's Law Example

```math
\oint_C \mathbf B\cdot d\mathbf r
=
\mu_0 I_{\text{enc}}
```

---

### 5.5 Properties of Line Integrals

#### 5.5.1 Linearity

```math
\int_C k\mathbf F\cdot d\mathbf r
=
k\int_C \mathbf F\cdot d\mathbf r
```

```math
\int_C(\mathbf F+\mathbf G)\cdot d\mathbf r
=
\int_C\mathbf F\cdot d\mathbf r
+
\int_C\mathbf G\cdot d\mathbf r
```

#### 5.5.2 Additivity

If $C=C_1\cup C_2$:

```math
\int_C\mathbf F\cdot d\mathbf r
=
\int_{C_1}\mathbf F\cdot d\mathbf r
+
\int_{C_2}\mathbf F\cdot d\mathbf r
```

#### 5.5.3 Reversing Orientation

```math
\int_{C^-}\mathbf F\cdot d\mathbf r
=
-
\int_C\mathbf F\cdot d\mathbf r
```

#### 5.5.4 Reparametrisation

- Same curve + same orientation → same integral value

---

### 5.6 Conservative Vector Fields

#### 5.6.1 Definition

$\mathbf F$ is conservative if:

```math
\mathbf F=\nabla\Phi
```

where $\Phi$ is scalar potential.

#### 5.6.2 Path Independence

If $\mathbf F=\nabla\Phi$:

```math
\int_C\mathbf F\cdot d\mathbf r
=
\Phi(B)-\Phi(A)
```

#### 5.6.3 Closed Curve Result

```math
\oint_C\mathbf F\cdot d\mathbf r=0
```

#### 5.6.4 Curl Test

If $\mathbf F$ is conservative:

```math
\nabla\times\mathbf F=0
```

If domain is **simply connected** and

```math
\nabla\times\mathbf F=0
```

then $\mathbf F$ is conservative.

In 2D, for $\mathbf F=[F_1,F_2]$:

```math
\frac{\partial F_1}{\partial y}
=
\frac{\partial F_2}{\partial x}
```

---

### 5.7 Equipotentials

If

```math
\mathbf F=\nabla\Phi
```

then equipotentials are level sets:

```math
\Phi=\text{constant}
```

Along equipotential:

```math
d\Phi=\nabla\Phi\cdot d\mathbf r=0
```

So:
- $\nabla\Phi$ is perpendicular to equipotentials

Electrostatics:

```math
\mathbf E=-\nabla\phi
```

---

### 5.8 Helmholtz Decomposition

Irrotational field:

```math
\nabla\times\mathbf F=0
```

Solenoidal field:

```math
\nabla\cdot\mathbf F=0
```

Helmholtz form:

```math
\mathbf F=\nabla\Phi+\nabla\times\mathbf A
```

---

## 6. Surface Integrals

### 6.1 Surface Element

Parametric surface:

```math
\mathbf r(s,t)=[x(s,t),y(s,t),z(s,t)]
```

Surface element vector:

```math
d\mathbf S=
\left(
\frac{\partial\mathbf r}{\partial s}
\times
\frac{\partial\mathbf r}{\partial t}
\right)
ds\,dt
```

Surface area element:

```math
dS=
\left|
\frac{\partial\mathbf r}{\partial s}
\times
\frac{\partial\mathbf r}{\partial t}
\right|
ds\,dt
```

---

### 6.2 Scalar Surface Integral

For scalar field $f$:

```math
\iint_S f\,dS
```

Formula:

```math
\iint_S f\,dS
=
\iint_D
f(\mathbf r(s,t))
\left|
\frac{\partial\mathbf r}{\partial s}
\times
\frac{\partial\mathbf r}{\partial t}
\right|
ds\,dt
```

---

### 6.3 Flux Surface Integral

For vector field $\mathbf F$:

```math
\iint_S \mathbf F\cdot d\mathbf S
```

Formula:

```math
\iint_S \mathbf F\cdot d\mathbf S
=
\iint_D
\mathbf F(\mathbf r(s,t))
\cdot
\left(
\frac{\partial\mathbf r}{\partial s}
\times
\frac{\partial\mathbf r}{\partial t}
\right)
ds\,dt
```

#### Meaning

- Measures flow through surface
- Orientation matters

---

## 7. Integral Theorems of Vector Calculus

### 7.1 Green's Theorem

Let $C$ be positively oriented, simple, closed curve bounding region $A$.

For

```math
\mathbf F(x,y)=[F_1(x,y),F_2(x,y)]
```

Green's theorem:

```math
\oint_C(F_1\,dx+F_2\,dy)
=
\iint_A
\left(
\frac{\partial F_2}{\partial x}
-
\frac{\partial F_1}{\partial y}
\right)
dx\,dy
```

#### Meaning

- Closed **line integral** ↔ **double integral**
- 2D theorem
- Positive orientation = counter-clockwise

---

### 7.2 Stokes' Theorem

Let $S$ be oriented surface with boundary curve $\partial S=C$.

```math
\iint_S(\nabla\times\mathbf F)\cdot d\mathbf S
=
\oint_C\mathbf F\cdot d\mathbf r
```

#### Meaning

- Surface integral of **curl**
- Equals line integral around **boundary**

---

### 7.3 Divergence Theorem

Let $V$ be volume with closed boundary surface $S=\partial V$.

Surface is oriented outward.

```math
\iint_S\mathbf F\cdot d\mathbf S
=
\iiint_V(\nabla\cdot\mathbf F)\,dV
```

#### Meaning

- Flux through closed surface
- Equals triple integral of divergence

---

## 8. Maxwell's Equations

### 8.1 Integral Form

Gauss's law for electricity:

```math
\iint_S\mathbf E\cdot d\mathbf S
=
\frac{1}{\varepsilon_0}
\iiint_V\rho\,dV
```

Gauss's law for magnetism:

```math
\iint_S\mathbf B\cdot d\mathbf S=0
```

Faraday's law:

```math
\oint_C\mathbf E\cdot d\mathbf r
=
-\frac{d}{dt}
\iint_S\mathbf B\cdot d\mathbf S
```

Ampere-Maxwell law:

```math
\oint_C\mathbf B\cdot d\mathbf r
=
\mu_0\iint_S\mathbf J\cdot d\mathbf S
+
\mu_0\varepsilon_0
\frac{d}{dt}
\iint_S\mathbf E\cdot d\mathbf S
```

---

### 8.2 Differential Form

```math
\nabla\cdot\mathbf E=\frac{\rho}{\varepsilon_0}
```

```math
\nabla\cdot\mathbf B=0
```

```math
\nabla\times\mathbf E=-\frac{\partial\mathbf B}{\partial t}
```

```math
\nabla\times\mathbf B=
\mu_0\mathbf J+
\mu_0\varepsilon_0
\frac{\partial\mathbf E}{\partial t}
```

---

### 8.3 Electromagnetic Wave Form

In vacuum:

```math
\rho=0,\qquad \mathbf J=0
```

Wave equations:

```math
\nabla^2\mathbf E-\mu_0\varepsilon_0
\frac{\partial^2\mathbf E}{\partial t^2}
=0
```

```math
\nabla^2\mathbf B-\mu_0\varepsilon_0
\frac{\partial^2\mathbf B}{\partial t^2}
=0
```

Wave speed:

```math
c=\frac{1}{\sqrt{\mu_0\varepsilon_0}}
\approx 3\times10^8\text{ m/s}
```

---

## 9. Method Selection

### 9.1 Double Integrals

- **Rectangle** → constant limits
- **Type I** → fix $x$, integrate $y$
- **Type II** → fix $y$, integrate $x$
- **Reverse order** → rewrite same region
- **Complicated region** → split into subdomains

---

### 9.2 Coordinate Systems

- **Cartesian** → rectangular boundaries
- **Polar** → circles / sectors
- **Cylindrical** → circular cylinder / $z$-axis symmetry
- **Spherical** → spheres / origin symmetry

---

### 9.3 Curves and Surfaces

- **Curve implicit form** → intersection of two surfaces
- **Curve parametric form** → $\mathbf r(t)$
- **Surface explicit form** → $z=f(x,y)$
- **Surface implicit form** → $\Phi(x,y,z)=0$
- **Surface parametric form** → $\mathbf r(s,t)$

---

### 9.4 Integral Type

- **Double integral** → area region
- **Triple integral** → volume region
- **Line integral** → vector field along curve
- **Closed line integral** → circulation
- **Scalar surface integral** → scalar over surface
- **Flux integral** → vector flow through surface

---

### 9.5 Conservative Fields

- Check whether $\mathbf F=\nabla\Phi$
- Conservative → path independent
- Closed curve integral = 0
- Conservative → $\nabla\times\mathbf F=0$
- Simply connected + zero curl → conservative

---

### 9.6 Integral Theorems

- **Green**: closed line integral ↔ double integral
- **Stokes**: boundary line integral ↔ surface integral of curl
- **Divergence**: closed flux integral ↔ triple integral of divergence