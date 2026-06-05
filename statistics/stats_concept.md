# MATH19622-1E2 Probability & Statistics Notes

## 1. Descriptive Statistics

### 1.1 Data and Sampling

#### 1.1.1 **Population vs Sample**
- **Population**: whole set of interest
- **Sample**: subset used to estimate population properties
- **Parameter**: value describing population
- **Statistic**: value calculated from sample

#### 1.1.2 **Sampling Quality**
- **Representative sample**: reflects population fairly
- **Simple random sample**: each item has equal selection chance
- **Bias**: systematic unfairness; larger $n$ does **not** fix it
- **Sampling error**: random luck error; decreases as $n$ increases
- **Confidence interval**: range estimate for true population value

---

### 1.2 Data Types and Graphs

#### 1.2.1 **Data Types**
- **Qualitative**: categories/labels
- **Quantitative**: numerical values
  - **Discrete**: counted values
  - **Continuous**: measured values

#### 1.2.2 **Graph Choice**
- **Bar chart**: qualitative / discrete
- **Histogram**: continuous, grouped into bins

---

### 1.3 Central Tendency

#### 1.3.1 **Mean**

**Population mean**

$$
\mu=\frac{1}{N}\sum_{i=1}^{N}x_i
$$

**Sample mean**

$$
\bar{x}=\frac{1}{n}\sum_{i=1}^{n}x_i
$$

- Sensitive to **outliers**
- Best for **symmetric** data

#### 1.3.2 **Median**
- Middle value after sorting
- Robust to **outliers**
- Best for **skewed** data

#### 1.3.3 **Mode**
- Most frequent value
- Best for **categorical** data

---

### 1.4 Dispersion

#### 1.4.1 **Range**

$$
\text{Range}=x_{\max}-x_{\min}
$$

- Sensitive to **outliers**

#### 1.4.2 **Interquartile Range**

$$
IQR=Q_3-Q_1
$$

- Spread of middle 50%
- Robust to **outliers**

#### 1.4.3 **Variance**

**Population variance**

$$
\sigma^2=\frac{1}{N}\sum_{i=1}^{N}(x_i-\mu)^2
$$

**Sample variance**

$$
s^2=\frac{1}{n-1}\sum_{i=1}^{n}(x_i-\bar{x})^2
$$

- $n-1$: **Bessel's correction**

#### 1.4.4 **Standard Deviation**

$$
\sigma=\sqrt{\sigma^2}
$$

$$
s=\sqrt{s^2}
$$

- Same units as data

---

## 2. Probability Fundamentals

### 2.1 Probability Notation

- **Sample space** $S$: all possible outcomes
- **Event** $A$: subset of $S$
- **Complement** $A^c$: not $A$
- **Union** $A\cup B$: $A$ or $B$
- **Intersection** $A\cap B$: $A$ and $B$

---

### 2.2 Probability Laws

#### 2.2.1 **Addition Law**

$$
P(A\cup B)=P(A)+P(B)-P(A\cap B)
$$

If **mutually exclusive**:

$$
P(A\cap B)=0
$$

$$
P(A\cup B)=P(A)+P(B)
$$

#### 2.2.2 **Conditional Probability**

$$
P(A|B)=\frac{P(A\cap B)}{P(B)}
$$

#### 2.2.3 **Multiplication Law**

$$
P(A\cap B)=P(A|B)P(B)=P(B|A)P(A)
$$

#### 2.2.4 **Independence**

$$
P(A|B)=P(A)
$$

$$
P(B|A)=P(B)
$$

$$
P(A\cap B)=P(A)P(B)
$$

---

### 2.3 Reliability

#### 2.3.1 **Series System**
- System works iff **all** parts work

$$
P(\text{works})=P(A)P(B)P(C)\cdots
$$

#### 2.3.2 **Parallel System**
- System works iff **at least one** path works

$$
P(\text{works})=1-P(\text{all fail})
$$

For two independent parts:

$$
P(\text{works})=1-(1-P(A))(1-P(B))
$$

---

## 3. Discrete Distributions

### 3.1 Discrete Random Variables

#### 3.1.1 **PMF**

$$
P(X=x)
$$

$$
0\leq P(X=x)\leq 1
$$

$$
\sum P(X=x)=1
$$

#### 3.1.2 **Expected Value**

$$
E(X)=\sum xP(X=x)
$$

#### 3.1.3 **Variance**

$$
Var(X)=E(X^2)-[E(X)]^2
$$

$$
E(X^2)=\sum x^2P(X=x)
$$

---

### 3.2 Binomial Distribution

#### 3.2.1 **Model**

$$
X\sim B(n,p)
$$

Use when:
- fixed $n$
- success/failure
- constant $p$
- independent trials

#### 3.2.2 **Probability Formula**

$$
P(X=k)=\binom{n}{k}p^k(1-p)^{n-k}
$$

#### 3.2.3 **Mean and Variance**

$$
E(X)=np
$$

$$
Var(X)=np(1-p)
$$

#### 3.2.4 **Shortcut**

$$
P(X\geq1)=1-P(X=0)
$$

---

### 3.3 Poisson Distribution

#### 3.3.1 **Model**

$$
X\sim Po(\lambda)
$$

Use when:
- count events in interval
- average rate $\lambda$
- random independent events

#### 3.3.2 **Probability Formula**

$$
P(X=k)=\frac{e^{-\lambda}\lambda^k}{k!}
$$

#### 3.3.3 **Mean and Variance**

$$
E(X)=\lambda
$$

$$
Var(X)=\lambda
$$

#### 3.3.4 **Shortcut**

$$
P(X\geq1)=1-P(X=0)
$$

---

## 4. Continuous Distributions

### 4.1 Continuous Random Variables

#### 4.1.1 **Key Property**

$$
P(X=a)=0
$$

Probabilities come from **area**, not height.

---

### 4.2 PDF and CDF

#### 4.2.1 **PDF**

$$
f(x)\geq0
$$

$$
\int_{-\infty}^{\infty}f(x)\,dx=1
$$

$$
P(a\leq X\leq b)=\int_a^b f(x)\,dx
$$

#### 4.2.2 **CDF**

$$
F(x)=P(X\leq x)
$$

$$
F(x)=\int_{-\infty}^{x}f(t)\,dt
$$

$$
f(x)=\frac{dF(x)}{dx}
$$

#### 4.2.3 **CDF Rules**

$$
P(X\leq a)=F(a)
$$

$$
P(X>a)=1-F(a)
$$

$$
P(a<X<b)=F(b)-F(a)
$$

---

### 4.3 Expected Value and Variance

#### 4.3.1 **Expected Value**

$$
E(X)=\int_{-\infty}^{\infty}xf(x)\,dx
$$

#### 4.3.2 **Variance**

$$
Var(X)=E(X^2)-[E(X)]^2
$$

$$
E(X^2)=\int_{-\infty}^{\infty}x^2f(x)\,dx
$$

---

### 4.4 Uniform Distribution

#### 4.4.1 **Model**

$$
X\sim U(a,b)
$$

$$
f(x)=\frac{1}{b-a},\quad a\leq x\leq b
$$

#### 4.4.2 **Mean and Variance**

$$
E(X)=\frac{a+b}{2}
$$

$$
Var(X)=\frac{(b-a)^2}{12}
$$

---

### 4.5 Normal Distribution

#### 4.5.1 **Model**

$$
X\sim N(\mu,\sigma^2)
$$

- **Symmetric**
- **Bell-shaped**
- mean = median = mode

#### 4.5.2 **Standard Normal**

$$
Z\sim N(0,1)
$$

$$
Z=\frac{X-\mu}{\sigma}
$$

#### 4.5.3 **Z-table Rules**

$$
P(Z>z)=1-P(Z<z)
$$

$$
P(a<Z<b)=P(Z<b)-P(Z<a)
$$

$$
P(Z<-a)=P(Z>a)
$$

#### 4.5.4 **Empirical Rule**

$$
\mu\pm1\sigma\approx68\%
$$

$$
\mu\pm2\sigma\approx95\%
$$

$$
\mu\pm3\sigma\approx99.7\%
$$

---

### 4.6 Exponential Distribution

#### 4.6.1 **Model**

$$
X\sim Exp(\lambda)
$$

$$
f(x)=\lambda e^{-\lambda x},\quad x\geq0
$$

$$
F(x)=1-e^{-\lambda x}
$$

#### 4.6.2 **Mean and Variance**

$$
E(X)=\frac{1}{\lambda}
$$

$$
Var(X)=\frac{1}{\lambda^2}
$$

#### 4.6.3 **Memoryless Property**

$$
P(X>s+t|X>s)=P(X>t)
$$

---

### 4.7 Distribution Approximations

#### 4.7.1 **Binomial to Normal**

$$
X\sim B(n,p)
$$

$$
X\approx N(np,\ np(1-p))
$$

Condition:

$$
np>5,\quad n(1-p)>5
$$

#### 4.7.2 **Poisson to Normal**

$$
X\sim Po(\lambda)
$$

$$
X\approx N(\lambda,\lambda)
$$

Condition:

$$
\lambda \text{ large}
$$

#### 4.7.3 **Continuity Correction**

For discrete $X$ and continuous approximation $Y$:

$$
P(X=k)\approx P(k-0.5<Y<k+0.5)
$$

$$
P(X\leq k)\approx P(Y<k+0.5)
$$

$$
P(X<k)\approx P(Y<k-0.5)
$$

$$
P(X\geq k)\approx P(Y>k-0.5)
$$

$$
P(X>k)\approx P(Y>k+0.5)
$$

---

### 4.8 Central Limit Theorem

$$
\bar{X}\approx N\left(\mu,\frac{\sigma^2}{n}\right)
$$

$$
SE=\frac{\sigma}{\sqrt n}
$$

- Large $n$ → $\bar{X}$ approximately normal
- Larger $n$ → smaller **standard error**

---

## 5. Linear Regression

### 5.1 Correlation

#### 5.1.1 **Statistical Sums**

$$
S_{xx}=\sum(x_i-\bar{x})^2
$$

$$
S_{yy}=\sum(y_i-\bar{y})^2
$$

$$
S_{xy}=\sum(x_i-\bar{x})(y_i-\bar{y})
$$

#### 5.1.2 **Pearson Correlation**

$$
r=\frac{S_{xy}}{\sqrt{S_{xx}S_{yy}}}
$$

$$
-1\leq r\leq1
$$

#### 5.1.3 **Interpretation**
- $r>0$: positive linear relationship
- $r<0$: negative linear relationship
- $|r|\approx1$: strong
- $|r|\approx0$: weak/no linear relationship
- **Correlation $\neq$ causation**
- Possible **lurking variable**

---

### 5.2 Simple Linear Regression

#### 5.2.1 **Model**

$$
\hat{y}=mx+c
$$

#### 5.2.2 **Least-Squares Formula**

$$
m=\frac{S_{xy}}{S_{xx}}
$$

$$
c=\bar{y}-m\bar{x}
$$

#### 5.2.3 **Residuals**

$$
e_i=y_i-\hat{y}_i
$$

Least squares minimises:

$$
\sum e_i^2
$$

#### 5.2.4 **Coefficient of Determination**

$$
R^2=r^2
$$

- proportion of variation in $y$ explained by $x$

---

### 5.3 Non-Linear Mapping

#### 5.3.1 **Exponential Model**

$$
y=Ae^{Bx}
$$

Take log:

$$
\ln y=\ln A+Bx
$$

Linear form:

$$
Y=c+mx
$$

Mappings:

$$
Y=\ln y,\quad c=\ln A,\quad m=B,\quad A=e^c
$$

#### 5.3.2 **Power Law Model**

$$
y=Ax^B
$$

Take log:

$$
\ln y=\ln A+B\ln x
$$

Linear form:

$$
Y=c+mX
$$

Mappings:

$$
Y=\ln y,\quad X=\ln x,\quad c=\ln A,\quad m=B,\quad A=e^c
$$

---

# Method Selection

## A. Descriptive Statistics
- **Mean**: symmetric data
- **Median**: skewed / outliers
- **Mode**: categorical
- **Bar chart**: categorical / discrete
- **Histogram**: continuous

## B. Probability
- **Addition law**: "A or B"
- **Multiplication law**: "A and B"
- **Conditional probability**: "given"
- **Independence**: event does not affect probability
- **Series reliability**: all must work
- **Parallel reliability**: at least one works

## C. Distributions
- **Binomial**: fixed trials + success/failure
- **Poisson**: count events in interval
- **Uniform**: equal likelihood on interval
- **Normal**: symmetric bell curve
- **Exponential**: waiting time between Poisson events

## D. Approximation
- **Binomial → Normal**: large $np$ and $n(1-p)$
- **Poisson → Normal**: large $\lambda$
- **Continuity correction**: always use for discrete-to-continuous

## E. Regression
- **Correlation**: strength/direction
- **Regression**: prediction
- **Residual**: prediction error
- **$R^2$**: explained variation
- **Log transform**: curved model → linear model