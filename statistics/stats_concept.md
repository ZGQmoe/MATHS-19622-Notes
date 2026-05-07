# MATH19622-1E2: Introduction to Probability and Statistics

### 1. Descriptive Statistics
#### 1.1 Central Tendency
* **Mean ($\bar{x}$):** Average value; sensitive to outliers.
* **Median:** Middle value; **robust** (ignores outliers).
* **Mode:** Most frequent value.

#### 1.2 Dispersion
* **Variance ($s^2$):** Measure of spread. Use $n-1$ for samples.
* **Standard Deviation ($s$):** $\sqrt{\text{Variance}}$; same units as data.
* **IQR:** $Q_3 - Q_1$; covers middle 50%.

---

### 2. Probability Laws
#### 2.1 Basic Rules
* **Addition:** $P(A \cup B) = P(A) + P(B) - P(A \cap B)$.
* **Multiplication:** $P(A \cap B) = P(A) \times P(B|A)$.
#### 2.2 Independence
* **Condition:** $P(B|A) = P(B)$.

---

### 3. Discrete Distributions
#### 3.1 Expected Value
* **Definition:** $E(X) = \sum x_i P(x_i)$.
#### 3.2 Binomial Distribution ($X \sim \text{B}(n, p)$)
* **Usage:** $n$ trials, $p$ probability of success.
* **Params:** $\mu = np$, $\sigma^2 = np(1-p)$.
#### 3.3 Poisson Distribution ($X \sim \text{Po}(\lambda)$)
* **Usage:** Events per interval (time/space).
* **Params:** $\mu = \sigma^2 = \lambda$.

---

### 4. Continuous Distributions
#### 4.1 Probability Density Function (PDF)
* **4.1.1 Definition:** $f(x)$ represents relative likelihood. Area equals probability.
* **4.1.2 Total Area:** Must equal 1: $\int_{-\infty}^{\infty} f(x) dx = 1$.
* **4.1.3 Interval Probability:** $P(a \leq X \leq b) = \int_{a}^{b} f(x) dx$.
* **4.1.4 Application:** Use definite integration from lower bound to target value.

#### 4.2 Cumulative Distribution Function (CDF)
* **4.2.1 Definition:** $F(x) = P(X \leq x)$, probability variable is $\leq x$.
* **4.2.2 Relation:** $f(x) = \frac{d}{dx} F(x)$.
* **4.2.3 Derivation:** Integrate PDF with variable upper limit: $F(x) = \int_{-\infty}^{x} f(t) dt$.

#### 4.3 Uniform Distribution ($X \sim \text{U}(a, b)$)
* **4.3.1 Definition:** Equal likelihood across interval $[a, b]$.
* **4.3.2 Mean and Variance:** $\mu = \frac{a+b}{2}$ and $\sigma^2 = \frac{(b-a)^2}{12}$.

#### 4.4 Normal Distribution ($X \sim \text{N}(\mu, \sigma^2)$)
* **4.4.1 Characteristics:** Symmetric, bell-shaped distribution.
* **4.4.2 Standard Normal ($Z$):** Case where $\mu = 0$ and $\sigma = 1$.
* **4.4.3 Z-Score:** $Z = \frac{x - \mu}{\sigma}$.
* **4.4.4 Empirical Rule:** 68% ($1\sigma$), 95% ($2\sigma$), 99.7% ($3\sigma$).

#### 4.5 Exponential Distribution ($X \sim \text{Exp}(\lambda)$)
* **4.5.1 Application:** Time/distance between Poisson events.
* **4.5.2 Memoryless:** Future probability independent of elapsed time.
* **4.5.3 Parameters:** $\mu = \frac{1}{\lambda}$ and $\sigma^2 = \frac{1}{\lambda^2}$.

#### 4.6 General Calculation Logic
* **4.6.1 Expected Value:** Integrate $x \cdot f(x)$ over full valid range: $E(X) = \int x f(x) dx$.
* **4.6.2 Interval Constraints:** Only calculate within specified ranges; PDF is 0 elsewhere.
### 4.7 Distribution Approximations
#### 4.7.1 Normal Approximation to Binomial
* **Usage:** Used when $n$ is large and $p$ is close to 0.5 (Conditions: $np > 5$ and $n(1-p) > 5$).
* **Parameters:** Mean $\mu = np$, Variance $\sigma^2 = np(1-p)$.
* **Continuity Correction (Point Estimate):** To calculate the probability for a discrete point $P(X = k)$ using a continuous distribution, you must integrate over the interval $[k - 0.5, k + 0.5]$.
    * $P(X = k) \approx P(k - 0.5 < Y < k + 0.5)$
#### 4.7 Distribution Approximations
* **4.7.1 Normal Approximation to Binomial:** Used when $np > 5$ and $n(1-p) > 5$.
* **4.7.2 Continuity Correction (Point):** For discrete $P(X = k)$, use interval $P(k - 0.5 < Y < k + 0.5)$ in the continuous model.

---

### 5. Linear Regression
#### 5.1 Correlation Analysis
* **5.1.1 Pearson Correlation Coefficient ($r$):** Measures strength/direction of linear relationship. Range: $[-1, 1]$.
* **5.1.2 Statistical Sums:**
    * $S_{xx} = \sum (x_i - \bar{x})^2$
    * $S_{yy} = \sum (y_i - \bar{y})^2$
    * $S_{xy} = \sum (x_i - \bar{x})(y_i - \bar{y})$
* **5.1.3 Calculation Formula:** $r = \frac{S_{xy}}{\sqrt{S_{xx} \cdot S_{yy}}}$.

#### 5.2 Simple Linear Regression Model
* **5.2.1 Least-Squares Line:** $\hat{y} = mx + c$.
* **5.2.2 Gradient ($m$):** $m = \frac{S_{xy}}{S_{xx}}$.
* **5.2.3 Intercept ($c$):** $c = \bar{y} - m\bar{x}$.
* **5.2.4 Coefficient of Determination ($R^2$):** Square of $r$. Represents proportion of variance in $y$ explained by $x$.