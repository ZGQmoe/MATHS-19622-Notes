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
f_{xx} \quad f_{yy} \quad f_{xy} \quad f_{yx}
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
J = \frac{\partial(x,y)}{\partial(u,v)} =
\begin{bmatrix}
\frac{\partial x}{\partial u} & \frac{\partial x}{\partial v} \\
\frac{\partial y}{\partial u} & \frac{\partial y}{\partial v}
\end{bmatrix}
$$

---

### 7.2 Jacobian Determinant

$$
det(J)
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

## 11. Level Curves

Level curve:

$$
f(x,y)=c
$$

Tangent direction $\mathbf{t}$:

$$
D_{\mathbf{t}}f=\nabla f\cdot \mathbf{t}=0
$$

Therefore:

$$
\nabla f \perp \text{level curve}
$$

Spacing:

- Close curves → large $|\nabla f|$
- Wide curves → small $|\nabla f|$

---

## 12. Stationary Points

At local extremum:

$$
f_x(a,b)=0, \quad f_y(a,b)=0
$$

Equivalently:

$$
\nabla f(a,b)=\mathbf{0}
$$

Necessary, not sufficient.

---

## 13. Tangent Plane

For $z=f(x,y)$ at $(x_0,y_0)$:

$$
z_0=f(x_0,y_0)
$$

$$
z-z_0=f_x(x_0,y_0)(x-x_0)+f_y(x_0,y_0)(y-y_0)
$$

Linear (first-order) approximation.

---

## 14. Second-Order Taylor Expansion

$$
f(x,y)\approx f(a,b)+f_x(a,b)(x-a)+f_y(a,b)(y-b)+\frac{1}{2}\left[f_{xx}(a,b)(x-a)^2+2f_{xy}(a,b)(x-a)(y-b)+f_{yy}(a,b)(y-b)^2\right]
$$

Quadratic terms determine curvature.

---

## 15. Global Extrema (Closed Region)

1. Solve $\nabla f=0$ (interior)
2. Evaluate boundary
3. Check corner points
4. Compare all values

---

## 16. Hessian Test

Let $(a,b)$ be stationary.

$$
A=f_{xx}(a,b), \quad B=f_{xy}(a,b), \quad C=f_{yy}(a,b)
$$

$$
D=AC-B^2
$$

Classification:

- $D>0$, $A>0$ → local min  
- $D>0$, $A<0$ → local max  
- $D<0$ → saddle  
- $D=0$ → inconclusive  

---

## 17. Geometric Interpretation

- $\nabla f=0$ → flat tangent plane  
- $D>0$ → same curvature sign  
- $D<0$ → opposite curvature (saddle)  

---

# Vector Calculus & Optimization Reference

## 18. Multi-Constrained Optimisation (Lagrange Multipliers)

Let $f = f(x,y,z)$ be a function subject to two constraints:
$$g_1(x,y,z) = 0, \quad g_2(x,y,z) = 0$$

At a constrained extremum, assuming $\nabla g_1$ and $\nabla g_2$ are **linearly independent**, the gradient of $f$ must lie in the plane spanned by the constraint gradients:

$$\nabla f = \lambda \nabla g_1 + \mu \nabla g_2$$

Together with the constraints:
1. $\nabla f(x,y,z) = \lambda \nabla g_1(x,y,z) + \mu \nabla g_2(x,y,z)$
2. $g_1(x,y,z) = 0$
3. $g_2(x,y,z) = 0$

---

### 18.1 Geometric Interpretation
* **Span:** $\nabla f \in \text{span}\{\nabla g_1, \nabla g_2\}$.
* **Orthogonality:** The directional derivative of $f$ is zero along the intersection curve of the two constraints.
* **Tangent Vector:** $\nabla f \cdot \mathbf{t} = 0$ for any vector $\mathbf{t}$ tangent to the constraint intersection.

---

## 19. Vector Differential Operators

### 19.1 Nabla Operator ($\nabla$)
The foundational vector differential operator:
$$\nabla = \mathbf{i}\frac{\partial}{\partial x} + \mathbf{j}\frac{\partial}{\partial y} + \mathbf{k}\frac{\partial}{\partial z}$$

In **2D**: $\nabla = \left(\frac{\partial}{\partial x}, \frac{\partial}{\partial y}\right)$

---

### 19.2 Divergence ($\text{div} \mathbf{v}$)
A scalar field representing the quantity of "flux" leaving a point.
$$\nabla \cdot \mathbf{v} = \frac{\partial v_1}{\partial x} + \frac{\partial v_2}{\partial y} + \frac{\partial v_3}{\partial z}$$

| Value | Physical Meaning |
| :--- | :--- |
| **$\nabla \cdot \mathbf{v} > 0$** | **Source**: Local expansion |
| **$\nabla \cdot \mathbf{v} < 0$** | **Sink**: Local compression |
| **$\nabla \cdot \mathbf{v} = 0$** | **Solenoidal**: Incompressible flow |

**Electrostatics (Gauss's Law):**
$$\nabla \cdot \mathbf{E} = \frac{\rho}{\varepsilon_0}$$

---

### 19.3 Curl ($\text{curl} \mathbf{v}$)
A vector field representing the local rotation or "vorticity."
$$\nabla \times \mathbf{v} = \begin{vmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ \partial_x & \partial_y & \partial_z \\ v_1 & v_2 & v_3 \end{vmatrix}$$

* **Direction:** The axis of rotation (via right-hand rule).
* **Magnitude:** Proportional to the circulation density; $|\nabla \times \mathbf{v}|/2$ is the local angular velocity.

**Electrostatics:**
Since $\mathbf{E} = -\nabla \Phi$, it follows that:
$$\nabla \times \mathbf{E} = \mathbf{0}$$

---

### 19.4 Laplacian ($\nabla^2$)
The divergence of the gradient; represents the "average" value of a function relative to its neighbors.
$$\nabla^2 f = \nabla \cdot (\nabla f) = \frac{\partial^2 f}{\partial x^2} + \frac{\partial^2 f}{\partial y^2} + \frac{\partial^2 f}{\partial z^2}$$

---

### 19.5 Common PDE Applications

| Name | Equation | Context |
| :--- | :--- | :--- |
| **Laplace** | $\nabla^2 \Phi = 0$ | Equilibrium/Steady-state |
| **Poisson** | $\nabla^2 \Phi = -\frac{\rho}{\varepsilon_0}$ | Electrostatics with charge |
| **Heat** | $\frac{\partial u}{\partial t} = \kappa \nabla^2 u$ | Thermal conduction |
| **Diffusion**| $\frac{\partial c}{\partial t} = D \nabla^2 c$ | Particle spread |
| **Wave** | $\frac{\partial^2 u}{\partial t^2} = c^2 \nabla^2 u$ | Propagation (sound, light) |

---

### 19.6 Operational Identities

**Linearity**
* $\nabla(f+g) = \nabla f + \nabla g$
* $\nabla \cdot (\mathbf{F}+\mathbf{G}) = \nabla \cdot \mathbf{F} + \nabla \cdot \mathbf{G}$
* $\nabla \times (\mathbf{F}+\mathbf{G}) = \nabla \times \mathbf{F} + \nabla \times \mathbf{G}$
* $\nabla(kf) = k\nabla f$
* $\nabla \cdot (k\mathbf{F}) = k \nabla \cdot \mathbf{F}$

**Product & Chain Rules**
* **Scalar Product:** $\nabla(fg) = f\nabla g + g\nabla f$
* **Vector Product:** $\nabla \cdot (f\mathbf{F}) = f(\nabla \cdot \mathbf{F}) + (\nabla f) \cdot \mathbf{F}$
* **Curl Product:** $\nabla \times (f\mathbf{F}) = f(\nabla \times \mathbf{F}) + (\nabla f) \times \mathbf{F}$
* **Chain Rule:** $\nabla[h(f)] = h'(f)\nabla f$

---

### 19.7 Key Null Identities
These are fundamental to vector field theory:
1. **Curl of a Gradient:** $\nabla \times (\nabla f) = \mathbf{0}$ (Conservative fields are irrotational)
2. **Divergence of a Curl:** $\nabla \cdot (\nabla \times \mathbf{F}) = 0$

---

### 19.8 Electrostatic Potential
The Electric field $\mathbf{E}$ is the negative gradient of the potential $\Phi$:
$$\mathbf{E} = -\nabla \Phi$$