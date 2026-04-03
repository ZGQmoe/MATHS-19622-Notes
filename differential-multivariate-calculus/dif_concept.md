# Multivariable Calculus — Partial Differentiation & Fields

---

## 1. Functions of Multiple Variables
A function of two variables:
$$z = f(x,y)$$
Geometric interpretation:
- Graph is a **surface** in $\mathbb{R}^3$
- Coordinates: $(x,y,z)$
- Each $(x,y)$ corresponds to a height $z$



---

## 2. Partial Differentiation
### 2.1 Definition
For $z=f(x,y)$:
$$\frac{\partial z}{\partial x}, \qquad \frac{\partial z}{\partial y}$$
Meaning:
- Differentiate with respect to one variable  
- Treat all other variables as constants  

### 2.2 Derivative vs Differential
| Concept | Single Variable | Multivariable |
| :--- | :--- | :--- |
| **Derivative** | $\frac{dy}{dx}$ | — |
| **Partial derivative** | — | $\frac{\partial z}{\partial x}$ |
| **Differential** | $dy = f'(x)dx$ | $dz = f_x dx + f_y dy$ |

---

## 3. Higher-Order Derivatives
Second-order partials: $f_{xx}, f_{yy}, f_{xy}, f_{yx}$

### 3.1 Clairaut’s Theorem (Mixed Partials)
If second partial derivatives are continuous near $(a,b)$:
$$f_{xy} = f_{yx}$$

---

## 4. Chain Rule (Multivariable)
If $z=f(x,y), x=x(u,v), y=y(u,v)$:
$$\frac{\partial z}{\partial u} = \frac{\partial z}{\partial x}\frac{\partial x}{\partial u} + \frac{\partial z}{\partial y}\frac{\partial y}{\partial u}$$
Interpretation:
- Sensitivity of $z$ to $u$ comes through both $x$ and $y$.

---

## 5. Total Differential (Small Changes)
If $z=f(x,y)$ and small changes $\Delta x, \Delta y$ occur:
$$\Delta z \approx f_x \Delta x + f_y \Delta y$$
In differential form:
$$dz = f_x dx + f_y dy$$
It gives a **linear approximation** of the surface.

---

## 6. Error Propagation
If $P = v^2/r$:
Relative error: $\frac{dP}{P} = -\frac{dr}{r} + 2\frac{dv}{v}$

- **Max Error:** $\frac{\Delta P}{P}=\left| \frac{\Delta r}{r} \right| + 2\left| \frac{\Delta v}{v} \right|$
- **RMS Error:** $\left(\frac{\Delta P}{P}\right)_{\text{RMS}}=\sqrt{ \left(\frac{\Delta r}{r}\right)^2 + \left(2\frac{\Delta v}{v}\right)^2}$

---

## 7. Jacobian
### 7.1 Jacobian Matrix & Determinant
$$J = \frac{\partial(x,y)}{\partial(u,v)} = \begin{bmatrix} \frac{\partial x}{\partial u} & \frac{\partial x}{\partial v} \\ \frac{\partial y}{\partial u} & \frac{\partial y}{\partial v} \end{bmatrix}$$
Meaning: $\text{det}(J)$ is the local area scaling factor used in coordinate transformations.

---

## 8. Scalar and Vector Fields
- **Scalar Field:** $\phi(x,y,z)$ (e.g., Temperature, Electric Potential)
- **Vector Field:** $\mathbf{F}(x,y,z) = \langle F_1,F_2,F_3 \rangle$ (e.g., Velocity, Electric Field)

---

## 9. Gradient
$$\nabla f = \left\langle f_x, f_y, f_z \right\rangle$$
- Points in direction of **maximum increase**.
- Perpendicular to level surfaces.

---

## 10. Directional Derivative
For unit vector $\mathbf{u}$:
$$D_{\mathbf{u}} f = \nabla f \cdot \mathbf{u}$$
Maximum value is $|\nabla f|$, occurring when $\mathbf{u} \parallel \nabla f$.

---

## 11. Level Curves
$f(x,y)=c$
- $\nabla f \perp$ level curve.
- Close curves → large $|\nabla f|$; Wide curves → small $|\nabla f|$.

---

## 12. Unconstrained Extrema ($x, y \in \mathbb{R}$)
- **Search:** Only Interior. Solve $\nabla f = \mathbf{0}$.
- **Classification:** Use **Hessian Test ($D$)**.
- **Global Check:** Analyze limits as $(x, y) \to \infty$. 



---

## 13. Tangent Plane
At $(x_0,y_0,z_0)$:
$$z-z_0=f_x(x_0,y_0)(x-x_0)+f_y(x_0,y_0)(y-y_0)$$

---

## 14. Second-Order Taylor Expansion
$$f(x,y)\approx f(a,b)+f_x(a,b)\Delta x+f_y(a,b)\Delta y+\frac{1}{2}\left[f_{xx}\Delta x^2+2f_{xy}\Delta x\Delta y+f_{yy}\Delta y^2\right]$$

---

## 15. Global Extrema (Closed Region)
### 15.1 Region vs. Boundary Search
- **Constraint ($g = 0$):** Equality. Search boundary via Lagrange Multipliers ($\nabla f = \lambda \nabla g$).
- **Region ($g \le 0$):** Inequality. Search Interior ($\nabla f = 0$) AND Boundary ($\nabla f = \lambda \nabla g$).

### 15.2 Domain Comparison Table
| Domain Type | Search Area | Classification |
| :--- | :--- | :--- |
| **Open** ($x, y \in \mathbb{R}$) | $\nabla f = \mathbf{0}$ | Hessian ($D$) + Limits at $\infty$ |
| **Closed** ($g \le 0$) | $\nabla f = \mathbf{0}$ **&** $\nabla f = \lambda \nabla g$ | Compare all $f(x,y)$ values |

---

## 16. Hessian Test
$D=f_{xx}f_{yy}-(f_{xy})^2$
- $D>0, f_{xx}>0 \to$ min
- $D>0, f_{xx}<0 \to$ max
- $D<0 \to$ saddle point

---

## 17. Multi-Constrained Optimisation
$$\nabla f = \lambda \nabla g_1 + \mu \nabla g_2$$
At constrained extremum, $\nabla f$ lies in the plane spanned by the constraint gradients.

---

## 18. Lagrange Multipliers Logic
### 18.1 Logic of $\nabla f = \lambda \nabla g$
On the Curve ($g=0$): Any move is tangent to the curve and perpendicular to $\nabla g$.
At Extremum: $f$ does not change along the tangent; thus $\nabla f$ is also perpendicular to all tangents.
Parallelism: Since both $\nabla f$ and $\nabla g$ are perpendicular to the same tangent, they are parallel: $\nabla f = \lambda \nabla g$.



---

## 19. Vector Differential Operators
### 19.1 Physical Interpretation
Divergence ($\nabla \cdot \mathbf{v}$): Net outward flux per unit volume (Positive = source/expansion, Negative = sink/compression).
Curl ($\nabla \times \mathbf{v}$): Local rotation or circulation (e.g., vorticity in fluid flow).



### 19.2 Conceptual Summary
- **Divergence:** "Does the fluid density change here?"
- **Curl:** "If I drop a leaf here, does it spin?"

---

## 20. Key Null Identities
1. **Curl of a Gradient:** $\nabla \times (\nabla f) = \mathbf{0}$
2. **Divergence of a Curl:** $\nabla \cdot (\nabla \times \mathbf{F}) = 0$

---

## 21. Conservative Fields & Potential
### 21.1 Identity: $\mathbf{E} = -\nabla \Phi$
**Logic: Why $\nabla \times \mathbf{E} = \mathbf{0}$**

Hill Analogy: $\Phi = \text{Height}$, $\nabla \Phi = \text{Slope}$. 
Returning to a starting point via a **closed loop** results in zero net height change. 
If $\nabla \times \mathbf{E} \neq 0$, you could walk in a circle and end up "higher" than you started, which is physically impossible for a fixed potential.


Path Independence: In gradient fields, work depends only on **start and end points**. 
Line integral (work) around any closed loop is always **zero**: $\oint \mathbf{E} \cdot d\mathbf{r} = 0$.
Stokes' Theorem: Work around a loop equals the flux of the **curl**. Since work is zero for every possible loop, the **curl itself must be zero**.



### 21.2 Properties
- **Irrotational:** $\nabla \times \mathbf{F} = \mathbf{0}$ (Curl of a gradient is always zero).
- **Energy Logic:** Curl must be zero; otherwise, ends up "higher" than started.
- **Path Independence:** Work depends only on start/end points; work around any closed loop is zero.