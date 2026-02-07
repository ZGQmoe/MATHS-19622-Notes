# Multivariable Calculus — Partial Differentiation & Fields

---

## 1. Functions of Multiple Variables

We consider a function of two variables

$$
z = f(x, y)
$$

Geometrically, this function can be visualised as a **surface** in 3D space with coordinates

$$
(x, y, z)
$$

Each point $(x, y)$ in the plane corresponds to a height $z$.

---

## 2. Partial Differentiation

### 2.1 Definition

Partial differentiation measures how a function changes **with respect to one variable**, while **treating the other variables as constants**.

For a function $z = f(x, y)$, the partial derivatives are

$$
\frac{\partial z}{\partial x},
\quad
\frac{\partial z}{\partial y}
$$

---

### 2.2 Notation and Terminology

| Concept | One variable | Multiple variables |
|------|-------------|-------------------|
| Derivative | $\dfrac{dy}{dx}$ | — |
| Partial derivative | — | $\dfrac{\partial y}{\partial x},\; y_x$ |
| Generality | Limited | More general |

**Key distinctions**

- A **derivative** applies to single-variable functions  
- A **partial derivative** applies to multivariable functions  
- A **differential** describes small changes (used later)

---

## 3. Higher-Order Partial Derivatives

Second-order partial derivatives include

$$
\frac{\partial^2 z}{\partial x^2},
\quad
\frac{\partial^2 z}{\partial y^2},
\quad
\frac{\partial^2 z}{\partial x \partial y},
\quad
\frac{\partial^2 z}{\partial y \partial x}
$$

---

### 3.1 Mixed Partials (Clairaut’s Theorem)

If $f(x,y)$ has **continuous second-order partial derivatives** in a neighbourhood of $(a,b)$, then

$$
\frac{\partial^2 z}{\partial x \partial y} = \frac{\partial^2 z}{\partial y \partial x}
$$

---

## 4. Chain Rule (Multivariable)

Let

$$
z = f(x,y), \quad x = x(u,v), \quad y = y(u,v)
$$

Then $z$ depends on $u$ and $v$ indirectly.

The chain rule gives

$$
\frac{\partial z}{\partial u}
=
\frac{\partial z}{\partial x}\frac{\partial x}{\partial u}
+
\frac{\partial z}{\partial y}\frac{\partial y}{\partial u}
$$

and

$$
\frac{\partial z}{\partial v}
=
\frac{\partial z}{\partial x}\frac{\partial x}{\partial v}
+
\frac{\partial z}{\partial y}\frac{\partial y}{\partial v}
$$

---

## 5. Jacobian Matrix and Determinant

### 5.1 Jacobian Matrix

For a transformation $(u,v) \mapsto (x,y)$, the Jacobian matrix is

$$
J
=
\begin{pmatrix}
\dfrac{\partial x}{\partial u} & \dfrac{\partial x}{\partial v} \\
\dfrac{\partial y}{\partial u} & \dfrac{\partial y}{\partial v}
\end{pmatrix}
$$

---

### 5.2 Jacobian Determinant

The determinant of the Jacobian matrix is

$$
\det(J)
=
\frac{\partial(x,y)}{\partial(u,v)}
=
\begin{vmatrix}
\dfrac{\partial x}{\partial u} & \dfrac{\partial x}{\partial v} \\
\dfrac{\partial y}{\partial u} & \dfrac{\partial y}{\partial v}
\end{vmatrix}
$$

It represents:

- Local **area scaling**
- Orientation change
- Appears in **change of variables** for multiple integrals

---

## 6. Total Differential (Small Changes)

For small changes $dx$ and $dy$, the total differential of $z = f(x,y)$ is

$$
dz
=
\frac{\partial z}{\partial x}\,dx
+
\frac{\partial z}{\partial y}\,dy
$$

This gives a linear approximation to the change in $z$.

---

## 7. Fields

### 7.1 Scalar Field

A **scalar field** assigns a scalar value to each point in space:

$$
\phi(x,y,z)
$$

Examples include:

- Temperature distribution
- Electric potential

---

### 7.2 Vector Field

A **vector field** assigns a vector to each point:

$$
\mathbf{F}(x,y,z)
=
\langle F_1, F_2, F_3 \rangle
$$

Examples include:

- Velocity field of a fluid
- Electric field

---

## 8. Gradient

For a scalar field $f(x,y,z)$, the gradient is defined as

$$
\nabla f
=
\left\langle
\frac{\partial f}{\partial x},
\frac{\partial f}{\partial y},
\frac{\partial f}{\partial z}
\right\rangle
$$

### Geometric Interpretation

- Points in the direction of **maximum increase** of $f$
- Is **normal (perpendicular)** to level surfaces $f=\text{constant}$

---

### 8.1 Nabla Operator

The nabla operator is

$$
\nabla
=
\left\langle
\frac{\partial}{\partial x},
\frac{\partial}{\partial y},
\frac{\partial}{\partial z}
\right\rangle
$$

It is a **vector differential operator** used to define:

- Gradient
- Divergence
- Curl

---

## 9. Directional Derivative

The directional derivative of $f$ at a point in the direction of a **unit vector** $\mathbf{u}$ is

$$
D_{\mathbf{u}} f
=
\nabla f \cdot \mathbf{u}
$$

Properties:

- Measures rate of change along a specified direction  
- Maximised when $\mathbf{u}$ is parallel to $\nabla f$

---