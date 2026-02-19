# Multivariable Calculus — Partial Differentiation & Fields

---

## 1. Functions of Multiple Variables

A function of two variables:

$$
z = f(x,y)
$$

Geometric interpretation:

- Graph is a **surface** in $\mathbb{R}^3$
- Coordinates: $(x,y,z)$
- Each $(x,y)$ corresponds to a height $z$

---

## 2. Partial Differentiation

### 2.1 Definition

For $z=f(x,y)$:

$$
\frac{\partial z}{\partial x}, 
\qquad
\frac{\partial z}{\partial y}
$$

Meaning:

- Differentiate with respect to one variable  
- Treat all other variables as constants  

---

### 2.2 Derivative vs Differential

| Concept | Single Variable | Multivariable |
|----------|----------------|---------------|
| Derivative | $\dfrac{dy}{dx}$ | — |
| Partial derivative | — | $\dfrac{\partial z}{\partial x}$ |
| Differential | $dy = f'(x)dx$ | $dz = f_x dx + f_y dy$ |

A **differential** describes small changes.

---

## 3. Higher-Order Derivatives

Second-order partials:

$$
f_{xx}, \quad f_{yy}, \quad f_{xy}, \quad f_{yx}
$$

---

### 3.1 Clairaut’s Theorem (Mixed Partials)

If second partial derivatives are continuous near $(a,b)$:

$$
f_{xy} = f_{yx}
$$

---

## 4. Chain Rule (Multivariable)

If

$$
z=f(x,y), \quad x=x(u,v), \quad y=y(u,v)
$$

Then:

$$
\frac{\partial z}{\partial u} = \frac{\partial z}{\partial x}\frac{\partial x}{\partial u} + \frac{\partial z}{\partial y}\frac{\partial y}{\partial u}
$$

$$
\frac{\partial z}{\partial v} = \frac{\partial z}{\partial x}\frac{\partial x}{\partial v} + \frac{\partial z}{\partial y}\frac{\partial y}{\partial v}
$$

Interpretation:

- Sensitivity of $z$ to $u$ comes through both $x$ and $y$.

---

## 5. Total Differential (Small Changes)

If $z=f(x,y)$ and small changes $\Delta x, \Delta y$ occur:

$$
\Delta z \approx \frac{\partial f}{\partial x}\Delta x + \frac{\partial f}{\partial y}\Delta y
$$

In differential form:

$$
dz = f_x dx + f_y dy
$$

More generally, for $f(x_1,\dots,x_n)$:

$$
dz = \sum_{k=1}^{n} \frac{\partial f}{\partial x_k} dx_k
$$

This is called the **total differential**.

It gives a **linear approximation**.

---

## 6. Error Propagation (Important)

If a quantity depends on measured variables:

Example:

$$
P = \frac{v^2}{r}
$$

Then:

$$
dP = \frac{\partial P}{\partial r} dr + \frac{\partial P}{\partial v} dv
$$

Relative error:

$$
\frac{dP}{P} = -\frac{dr}{r} + 2\frac{dv}{v}
$$

---

### 6.1 Maximum Relative Error

Worst case:

$$
\frac{\Delta P}{P}=\left| \frac{\Delta r}{r} \right| + 2\left| \frac{\Delta v}{v} \right|
$$

---

### 6.2 RMS (Expected) Relative Error

If errors are independent:

$$
\left(\frac{\Delta P}{P}\right)_{\text{RMS}}=\sqrt{ \left(\frac{\Delta r}{r}\right)^2 + \left(2\frac{\Delta v}{v}\right)^2}
$$

This is usually smaller than maximum error.

---

## 7. Jacobian

### 7.1 Jacobian Matrix

For transformation $(u,v) \mapsto (x,y)$:

$$
J = \begin{pmatrix} x_u & x_v \\ y_u & y_v \end{pmatrix}
$$

---

### 7.2 Jacobian Determinant

$$
\frac{\partial(x,y)}{\partial(u,v)} = \begin{vmatrix} x_u & x_v \\ y_u & y_v \end{vmatrix}
$$

Meaning:

- Local area scaling factor
- Used in change of variables

---

## 8. Scalar and Vector Fields

### Scalar Field

$$
\phi(x,y,z)
$$

Assigns a scalar to each point.

Examples: temperature, electric potential.

---

### Vector Field

$$
\mathbf{F}(x,y,z) = \langle F_1,F_2,F_3 \rangle
$$

Assigns a vector to each point.

Examples: velocity field, electric field.

---

## 9. Gradient

$$
\nabla f = \left\langle f_x, f_y, f_z \right\rangle
$$

Properties:

- Points in direction of **maximum increase**
- Perpendicular to level surfaces
- Magnitude = maximum directional derivative

---

## 10. Directional Derivative

For unit vector $\mathbf{u}$:

$$
D_{\mathbf{u}} f = \nabla f \cdot \mathbf{u}
$$

Maximum occurs when:

$$
\mathbf{u} \parallel \nabla f
$$

Maximum value:

$$
\max D_{\mathbf{u}} f = |\nabla f|
$$

---