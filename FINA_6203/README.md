# Computational Finance with Python

## Simple Returns (Arithmetic Returns)

Simple returns represent the percentage change in an asset’s price over a given period. They are widely used for evaluating historical performance over discrete time intervals.

### Simple Return Formula

$$
R_t = \frac{P_t - P_{t-1}}{P_{t-1}}
$$

Where:

* \$R\_t\$ = simple return at time \$t\$
* \$P\_t\$ = price at time \$t\$
* \$P\_{t-1}\$ = price at previous time \$t-1\$

---

### Interpretation

A positive \$R\_t\$ indicates a gain (price increased), while a negative \$R\_t\$ indicates a loss. Simple returns are easy to understand but do not account for compounding.

---

## Holding Period Returns (HPR)

HPR captures the total return earned over an entire holding period, including any dividends or cash flows.

### Holding Period Return Formula

$$
HPR = \frac{P_t + D - P_{t-1}}{P_{t-1}}
$$

Where:

* \$P\_t\$ = ending price of the asset
* \$P\_{t-1}\$ = beginning price
* \$D\$ = cash dividends or distributions received during the period

---

### Interpretation

A positive HPR implies the investment was profitable over the holding period. HPR is useful for investments not held exactly one year.

---

## Annualized Returns

Annualized returns express an investment’s return as a yearly rate, standardizing different time periods.

### Annualized Return Formula

$$
\text{Annualized Return} = (1 + HPR)^{\frac{1}{n}} - 1
$$

Where:

* \$HPR\$ = holding period return
* \$n\$ = number of years held

---

### Interpretation

Annualizing returns allows investors to compare different assets and time frames on a consistent basis.

---

## Log Returns (Continuously Compounded Returns)

Log returns use natural logarithms to measure returns and assume continuous compounding.

### Log Return Formula

$$
r_t = \ln\left(\frac{P_t}{P_{t-1}}\right)
$$

Where:

* \$r\_t\$ = log return at time \$t\$
* \$P\_t\$ = price at time \$t\$
* \$P\_{t-1}\$ = price at previous time \$t-1\$

---

### Interpretation

Log returns can be added across periods, simplifying multi-period return calculations. They are preferred in many statistical and risk models.

---

## Annualized Log Returns

Annualizing log returns provides a consistent measure for comparing assets.

### Annualized Log Return Formula

$$
R_a = n \times r
$$

Where:

* \$R\_a\$ = annualized log return
* \$r\$ = average log return for the period
* \$n\$ = number of periods per year (e.g., 252 for daily trading)

---

### Example

If \$r = 0.001\$ and \$n = 252\$,

$$
R_a = 252 \times 0.001 = 0.252 \ (25.2\%)
$$

---

## Adjusting Returns for Dividends

Returns should include dividends to reflect total value to shareholders.

---

### Simple Returns with Dividends

$$
r_t = \frac{P_t + D_t - P_{t-1}}{P_{t-1}}
$$

Where:

* \$D\_t\$ = dividend at time \$t\$

---

### Log Returns with Dividends

$$
r_t = \ln\left(\frac{P_t + D_t}{P_{t-1}}\right)
$$

---

### Explanation

Inclusion of dividends gives a more accurate picture of the actual performance of a stock, since dividends are a significant part of total shareholder return.

---

## Adjusting Returns for a Portfolio

For portfolios, returns depend on the weights and returns of each asset.

---

### Portfolio Simple Return

$$
r_p = \sum_{i=1}^{n} w_i r_i
$$

Where:

* \$w\_i\$ = weight of asset \$i\$ in the portfolio
* \$r\_i\$ = return of asset \$i\$

---

### Explanation

The formula reflects how each asset contributes to the portfolio return based on its weight.

---

## Excess Returns

Excess returns (or alpha) measure performance relative to a benchmark or risk-free rate.

---

### Formula

$$
\alpha = r_i - r_b
$$

Where:

* \$r\_i\$ = return of the investment
* \$r\_b\$ = benchmark or risk-free rate

---

### Interpretation

A positive alpha indicates the investment outperformed the benchmark, while a negative alpha indicates underperformance.

---

## Random Variables

Random variables represent uncertain outcomes numerically.

---

### Discrete Random Variables

Defined by a probability mass function (PMF):

$$
p(x) = P(X = x)
$$

Properties:

* \$0 \leq p(x) \leq 1\$
* \$\sum\_x p(x) = 1\$

---

### Continuous Random Variables

Defined by a probability density function (PDF):

$$
P(a \leq X \leq b) = \int_{a}^{b} f(x) \, dx
$$

CDF (Cumulative Distribution Function):

$$
F(x) = P(X \leq x)
$$

---

## Bernoulli Distribution

Models experiments with two outcomes (success/failure).

---

### PMF

$$
P(X = k) = p^k (1-p)^{1-k}
$$

Where \$k \in {0, 1}\$.

---

### Expected Value

$$
E[X] = p
$$

---

### Variance

$$
Var(X) = p(1 - p)
$$

---

## Discrete vs Continuous Random Variables

### Discrete

Values are countable (e.g., number of heads in coin tosses).

---

### Continuous

Values can take any value within a range (e.g., heights, stock returns).

---

## Uniform Distribution

All outcomes are equally likely.

---

### Continuous Uniform Distribution

PDF:

$$
f(x) = \begin{cases}
\frac{1}{b - a}, & a \leq x \leq b \\
0, & \text{otherwise}
\end{cases}
$$

Expected value:

$$
E[X] = \frac{a + b}{2}
$$

Variance:

$$
Var(X) = \frac{(b - a)^2}{12}
$$

---

### Discrete Uniform Distribution

All \$n\$ outcomes equally likely.

Expected value:

$$
E[X] = \frac{n+1}{2}
$$

Variance:

$$
Var(X) = \frac{n^2 - 1}{12}
$$

---

## Normal Distribution

A bell-shaped continuous distribution used widely in finance and statistics.

---

### PDF

$$
f(x|\mu,\sigma^2) = \frac{1}{\sigma \sqrt{2\pi}} e^{ -\frac{(x - \mu)^2}{2\sigma^2} }
$$

---

### Properties

* Symmetric about the mean.
* 68% within \$\mu \pm \sigma\$, 95% within \$\mu \pm 2\sigma\$, 99.7% within \$\mu \pm 3\sigma\$.

---

## Student’s t-distribution

Used when estimating means with small samples and unknown variance.

---

### PDF

$$
f(t|v) = \frac{\Gamma\left(\frac{v + 1}{2}\right)}{\sqrt{v\pi} \cdot \Gamma\left(\frac{v}{2}\right)} \left(1 + \frac{t^2}{v}\right)^{-\frac{v+1}{2}}
$$

---

### Properties

* Symmetric, heavier tails than normal.
* Approaches normal as \$v \to \infty\$.

---

## Expected Value

Represents the "center" of a distribution or long-run average.

---

### Discrete

$$
E(X) = \sum_i x_i p(x_i)
$$

---

### Continuous

$$
E(X) = \int x f(x) \, dx
$$

---

## Variance, Skewness, Kurtosis

---

### Variance

$$
\sigma^2 = E[(X - \mu)^2]
$$

---

### Skewness

$$
\text{Skewness} = E\left[\left(\frac{X - \mu}{\sigma}\right)^3\right]
$$

---

### Kurtosis

$$
\text{Kurtosis} = E\left[\left(\frac{X - \mu}{\sigma}\right)^4\right]
$$

---

## Covariance

Measures joint variability.

---

### Formula

$$
\text{Cov}(X,Y) = E[(X - \mu_X)(Y - \mu_Y)]
$$

---

## Variance of Sums

When adding random variables:

---

### Independent

$$
\text{Var}(X + Y) = \text{Var}(X) + \text{Var}(Y)
$$

---

### Dependent

$$
\text{Var}(X + Y) = \text{Var}(X) + \text{Var}(Y) + 2\text{Cov}(X, Y)
$$

---

### General Case

$$
\text{Var}\left(\sum_{i=1}^n X_i\right) = \sum_{i=1}^n \text{Var}(X_i) + 2 \sum_{i=1}^{n-1}\sum_{j=i+1}^n \text{Cov}(X_i, X_j)
$$


## Exponential Growth Model in Finance

In finance, **exponential growth** refers to the process by which an amount of money grows at a rate proportional to its current value. This is the fundamental concept behind **compound interest**, which explains why investments grow faster the longer they are held and why small differences in interest rates or compounding frequencies lead to large differences over time.

---

### Compound Interest Formula

$$
A = P\left(1 + \frac{r}{n}\right)^{nt}
$$

Where:

* **$A$**: Future value of the investment or loan, including interest.
* **$P$**: Principal or initial amount.
* **$r$**: Annual interest rate (as a decimal).
* **$n$**: Number of times interest is compounded per year.
* **$t$**: Number of years the money is invested or borrowed for.

The formula shows how compound interest accumulates when interest is reinvested or added to the principal at regular intervals.

---

### Continuous Compounding

When interest is compounded continuously, the formula becomes:

$$
A = Pe^{rt}
$$

Where:

* **$e$** is Euler’s number (approximately 2.71828).
* Continuous compounding is the theoretical limit where interest is constantly being added.

---

### Interpretation

These formulas highlight how **time and compounding frequency** significantly influence final outcomes. Even small increases in rates or longer time horizons can result in exponentially higher final values due to the compounding effect.

---

## Log Prices in Finance

In finance, **log prices** refer to taking the natural logarithm of an asset’s price. This approach simplifies the mathematics of returns and risk calculations, especially for continuously compounded returns.

---

### Formula

$$
L = \ln(P)
$$

Where:

* **$P$**: Asset price.
* **$L$**: Log price.

---

### Advantages of Using Log Prices

1. **Returns Calculation**

   Using log prices, the return between two periods is:

   $$
   r = \ln(P_t) - \ln(P_{t-1})
   $$

   This gives the continuously compounded return, which is more accurate for modeling over long periods.

2. **Additivity**

   Log returns are additive over time:

   $$
   r_{\text{total}} = \ln(P_t) - \ln(P_0) = \sum_{i=1}^{t} r_i
   $$

   This makes cumulative return calculations easier.

3. **Statistical Properties**

   Log returns tend to be more normally distributed, which simplifies risk modeling and statistical inference.

---

### Example

If a stock’s price increases from \$100 to \$110:

$$
r = \ln(110) - \ln(100)
$$

This yields the continuous return over that period.

---

### Log Returns

Log returns are formally expressed as:

$$
r_t = \ln\left(\frac{P_t}{P_{t-1}}\right)
$$

These are widely used in quantitative finance and risk models.

---

## Dividend Discount Model

The **Dividend Discount Model (DDM)** values a stock based on the present value of expected future dividends.

---

### Basic Formula

$$
P_0 = \frac{D_1}{r - g}
$$

Where:

* **$P_0$**: Current stock price.
* **$D_1$**: Expected dividend in the next period.
* **$r$**: Required rate of return (discount rate).
* **$g$**: Constant dividend growth rate.

---

### Zero Growth Version

When dividends are expected to remain constant (zero growth):

$$
P_0 = \frac{D}{r}
$$

Where:

* **$D$**: Constant dividend.

This is also called the perpetuity formula.

---

### Current Yield (CY)

For bonds or dividend-paying stocks, the **current yield** is:

$$
\text{CY} = \frac{\text{Annual Coupon Payment}}{\text{Current Bond Price}}
$$

This indicates the income yield without considering price changes.

---

## Leptokurtosis in Financial Distributions

**Leptokurtosis** refers to distributions with **fat tails**, meaning they have more extreme values than a normal distribution.

---

### Kurtosis

$$
\text{Kurtosis} = E\left[\left(\frac{X - \mu}{\sigma}\right)^4\right]
$$

Where:

* $X$: Random variable.
* $\mu$: Mean.
* $\sigma$: Standard deviation.

---

### Excess Kurtosis

$$
\text{Excess Kurtosis} = \text{Kurtosis} - 3
$$

* If **Excess Kurtosis > 0**, the distribution is leptokurtic (fat tails).
* If **= 0**, it is mesokurtic (normal).
* If **< 0**, it is platykurtic (thin tails).

Fat tails imply higher risk of extreme losses or gains.

---

## Summary Statistics in Finance

These are key metrics to describe a dataset (e.g., asset returns).

---

### Mean

$$
\mu = \frac{1}{n}\sum_{i=1}^{n}x_i
$$

The average of all values.

---

### Variance

$$
\sigma^2 = \frac{1}{n}\sum_{i=1}^{n}(x_i - \mu)^2
$$

Measures how data points spread around the mean.

---

### Standard Deviation

$$
\sigma = \sqrt{\sigma^2}
$$

Describes volatility (how much returns deviate from the mean).

---

### Skewness

$$
\text{Skewness} = E\left[\left(\frac{x - \mu}{\sigma}\right)^3\right]
$$

Indicates asymmetry of distribution:

* Positive: Tail on the right.
* Negative: Tail on the left.

---

### Kurtosis

$$
\text{Kurtosis} = E\left[\left(\frac{x - \mu}{\sigma}\right)^4\right]
$$

Shows tail thickness and peak sharpness.

---

### Range

$$
\text{Range} = \text{Max} - \text{Min}
$$

Difference between highest and lowest value.

---

### Interpretation

Together, these statistics help investors understand the **central tendency, risk, shape, and extremes** of returns. They form the foundation of portfolio risk assessment and performance analysis.


## Value-at-Risk (VaR)

Value-at-Risk estimates the potential loss in value of a risky asset or portfolio over a specific time period at a given confidence level.

### Parametric VaR (Variance-Covariance)

When returns are normally distributed:

$$
\text{VaR}_\alpha = \mu - Z_\alpha \sigma
$$

Where:

* $\mu$ is the expected return.
* $\sigma$ is standard deviation.
* $Z_\alpha$ is the critical value from the standard normal distribution corresponding to confidence level $\alpha$.

---

### Historical Simulation

This method uses empirical historical returns to estimate the quantile at $(1 - \alpha)$.

---

### Monte Carlo Simulation

Simulate many possible future price paths, then take the $(1 - \alpha)$ quantile of simulated losses.

---

### Alternate VaR Formula for Time Horizon

For multi-period horizon $t$:

$$
\text{VaR}_\alpha = \mu \times t + Z_\alpha \times \sigma \times \sqrt{t}
$$

---

## Autocorrelation

Autocorrelation measures the correlation of a time series with its own lagged values:

$$
\rho_k = \frac{\sum_{t=k+1}^{T}(r_t - \bar{r})(r_{t-k} - \bar{r})}{\sum_{t=1}^{T}(r_t - \bar{r})^2}
$$

Where $k$ is the lag.

---

## Variance Ratio

The variance ratio test checks if a time series follows a random walk:

$$
VR(k) = \frac{\text{Var}[k \cdot r_t]}{k \cdot \text{Var}[r_t]}
$$

Where $k$ is the number of periods.

* $VR(k) = 1$: random walk.
* $VR(k) > 1$: positive serial correlation.
* $VR(k) < 1$: negative serial correlation.

---

## Capital Asset Pricing Model (CAPM)

Describes the relationship between expected return and risk (beta):

$$
E(R_i) = R_f + \beta_i(E(R_m) - R_f)
$$

Where:

* $E(R_i)$: Expected return on asset $i$.
* $R_f$: Risk-free rate.
* $\beta_i$: Sensitivity to market.
* $E(R_m)$: Expected return on market.

---

## Risk Decomposition

Breaks total risk into systematic and unsystematic parts.

### Total Risk

$$
\sigma^2(Total) = \sigma^2(Systematic) + \sigma^2(Unsystematic)
$$

---

### Systematic Risk

Market-related risk that cannot be diversified away:

$$
\sigma^2(Systematic) = \beta^2 \times \sigma^2(Market)
$$

---

### Unsystematic Risk

Asset-specific risk that can be reduced through diversification:

$$
\sigma^2(Unsystematic) = \sigma^2(Total) - \sigma^2(Systematic)
$$

---

## Multifactor CAPM

Generalizes CAPM by including multiple risk factors:

$$
R_i - R_f = \alpha_i + \beta_{iM}(R_M - R_f) + \beta_{i1}F_1 + \dots + \beta_{ik}F_k + \epsilon_i
$$

Where:

* $\alpha_i$: Asset-specific intercept (alpha).
* $F_j$: Additional factors (e.g., size, value).

---

## Coefficient of Determination ($R^2$)

Explains how much variability in $Y$ is explained by $X$:

$$
R^2 = 1 - \frac{SS_{res}}{SS_{tot}}
$$

Where:

* $SS_{res}$: Sum of squared residuals.
* $SS_{tot}$: Total sum of squares.

---

## Adjusted $R^2$

Adjusts $R^2$ for number of predictors:

$$
R^2_{adj} = 1 - \left(\frac{1 - R^2}{n - k - 1}\right)
$$

Where:

* $n$: Number of observations.
* $k$: Number of predictors.

---

## F-test

Tests joint significance of regression coefficients:

$$
F = \frac{(R^2 / k)}{(1 - R^2)/(n - k - 1)}
$$

Where:

* $k$: Number of predictors.
* $n$: Sample size.

---

## Disturbance Diagnostics

### Durbin-Watson Test

Tests for autocorrelation in residuals:

$$
DW = \frac{\sum_{t=2}^{n}(e_t - e_{t-1})^2}{\sum_{t=1}^{n}e_t^2}
$$

---

### Variance Inflation Factor (VIF)

Checks for multicollinearity:

$$
VIF_j = \frac{1}{1 - R^2_j}
$$

Where $R^2_j$ is the $R^2$ from regressing $X_j$ on other predictors.

---

## ARCH Model

Used to model time-varying volatility in time series.

### Mean Equation

$$
r_t = \mu + \epsilon_t
$$

---

### Variance Equation

$$
\epsilon_t = \sigma_t z_t
$$

$$
\sigma_t^2 = \alpha_0 + \alpha_1 \epsilon_{t-1}^2
$$

Where:

* $\sigma_t$: Conditional standard deviation.
* $z_t$: Standardized residual (white noise).

---

### ARCH(q) Model

Generalized version:

$$
\sigma_t^2 = \alpha_0 + \alpha_1 \epsilon_{t-1}^2 + \dots + \alpha_q \epsilon_{t-q}^2
$$


## Nonstationarity

A time series is said to be **stationary** if it has constant mean, variance, and autocorrelation over time. **Nonstationarity** implies that one or more of these properties change over time.

The most common form of nonstationarity is the **unit root**. For a time series $Y_t$:

$$
Y_t = Y_{t-1} + \epsilon_t
$$

where $\epsilon_t$ is a white noise error term, implies $Y_t$ has a unit root and is nonstationary.

---

### General Representation

$$
\Delta Y_t = \alpha + \beta t + \rho Y_{t-1} + \epsilon_t
$$

If $|\rho| = 1$, then $Y_t$ is nonstationary.

---

## Testing for Nonstationarity

The **Dickey-Fuller** test is used to detect unit roots. The Augmented Dickey-Fuller (ADF) test extends this to handle autocorrelated residuals and tests the null hypothesis that a unit root is present.

---

## Dickey-Fuller Tests

### 1. Basic Dickey-Fuller Test

Regression equation:

$$
\Delta Y_t = \alpha + \beta t + \gamma Y_{t-1} + \epsilon_t
$$

Where:

* $\Delta Y_t$: Difference in the series at time $t$.
* $\alpha$: Constant.
* $\beta t$: Trend term.
* $\gamma Y_{t-1}$: Lagged level.
* $\epsilon_t$: Error term.

Null hypothesis: $\gamma = 0$, indicating nonstationarity.

---

### 2. Augmented Dickey-Fuller (ADF) Test

Regression equation:

$$
\Delta Y_t = \alpha + \beta t + \gamma Y_{t-1} + \delta_1 \Delta Y_{t-1} + \delta_2 \Delta Y_{t-2} + \dots + \delta_p \Delta Y_{t-p} + \epsilon_t
$$

Where:

* $\delta_1, \delta_2, \dots$: Coefficients for lagged differences.

Null hypothesis: $\gamma = 0$.

---

## KPSS Test

Used to test for **stationarity**.

### 1. Level Stationarity

Model:

$$
Y_t = \mu + u_t
$$

Where:

$$
u_t = \rho u_{t-1} + \epsilon_t
$$

And:

$$
\epsilon_t \sim WN(0, \sigma^2)
$$

Test Statistic:

$$
LM_{level} = \frac{\sum_{t=1}^{T} S_t^2}{\sigma^2}
$$

Where:

$$
S_t = \sum_{i=1}^{t} u_i
$$

---

### 2. Trend Stationarity

Model:

$$
Y_t = \mu + \lambda t + u_t
$$

Test Statistic:

$$
LM_{trend} = \frac{\sum_{t=1}^{T} S_t^2}{\sigma^2}
$$

If the LM statistic exceeds the critical value, the null hypothesis of stationarity is rejected.

---

## Equity Shock

Refers to a sudden, significant event impacting stock values.

Model:

$$
r_t = \alpha + \beta s_t + \epsilon_t
$$

Where:

* $r_t$: Return at time $t$.
* $s_t$: Shock at time $t$.
* $\beta$: Sensitivity to shock.

If $\beta$ is significantly different from zero, it suggests the stock return is affected by the shock.

---

## Dividend Shock

Pertains to unexpected changes in a company’s dividend payout.

Model:

$$
P_t = \alpha + \beta D_t + \gamma DS_t + \epsilon_t
$$

Where:

* $P_t$: Stock price at time $t$.
* $D_t$: Dividend payout at time $t$.
* $DS_t$: Dividend shock at time $t$.
* $\beta$: Sensitivity to dividends.
* $\gamma$: Sensitivity to dividend shocks.

If $\gamma$ is significant, the stock price reacts notably to dividend shocks.

---

## Variance Decomposition

Assesses how individual assets contribute to overall portfolio variance.

### Two-Asset Portfolio

$$
\sigma^2_{\text{portfolio}} = w_1^2 \sigma_1^2 + w_2^2 \sigma_2^2 + 2 w_1 w_2 \sigma_{1,2}
$$

Where:

* $w_1, w_2$: Weights of assets.
* $\sigma_1^2, \sigma_2^2$: Variances.
* $\sigma_{1,2}$: Covariance.

---

## Brownian Motion (Wiener Process)

Fundamental in option pricing.

**Properties**:

1. Starts at zero: $W_0 = 0$.
2. Increments are normally distributed: $W_t - W_s \sim N(0, t - s)$.
3. Increments are independent.

Differential form:

$$
dW_t \sim N(0, dt)
$$

---

## Geometric Brownian Motion (GBM)

Used for modeling stock prices.

**Stochastic Differential Equation**:

$$
dS_t = \mu S_t dt + \sigma S_t dW_t
$$

Solution:

$$
S_t = S_0 e^{(\mu - \frac{\sigma^2}{2})t + \sigma W_t}
$$

Where:

* $S_0$: Initial price.
* $\mu$: Drift.
* $\sigma$: Volatility.
* $W_t$: Wiener process.

---

## Binomial Model

Used for American option valuation.

**One-step model**:

* Possible stock prices:

  $$
  S_u = S \times u
  $$

  $$
  S_d = S \times d
  $$

* Present value of option:

  $$
  C = \frac{1}{1+r}\left( p C_u + (1-p) C_d \right)
  $$

* Risk-neutral probability:

  $$
  p = \frac{e^{r \Delta t} - d}{u - d}
  $$

---

## Granger Causality

Determines if one time series can predict another.

### Steps

1. Compare a model predicting $Y$ using only past $Y$ with a model using past $Y$ and $X$.
2. If including $X$ improves prediction, $X$ "Granger-causes" $Y$.

**Key Points**:

* Not true causality, just predictive.
* Can be bi-directional.
* Sensitive to lag selection and linearity assumptions.


### Basic Breakdown:

1. **Two Time Series**: Granger causality typically deals with two time series, \(X\) and \(Y\).
2. **Prediction**: The fundamental question Granger causality asks is whether past values of \(X\) provide information that helps predict \(Y\), above and beyond the information provided by past values of \(Y\) itself.
3. **Lagged Values**: To determine this, a statistical model is used that includes lagged (i.e., past) values of \(X\) and \(Y\).
4. **Comparison**: The predictive power of a model that uses lagged values of both \(X\) and \(Y\) to predict \(Y\) is compared to a model that uses only lagged values of \(Y\).
5. **Result**: If the inclusion of lagged values of \(X\) significantly improves the prediction of \(Y\), then \(X\) is said to "Granger-cause" \(Y\).

### Key Points:

- **Not Causal in Traditional Sense**: Just because \(X\) Granger-causes \(Y\) doesn't mean \(X\) is the underlying cause of changes in \(Y\). It simply means there's a consistent pattern where changes in \(X\) precede changes in \(Y\).
- **Bi-directionality**: It's possible for \(X\) to Granger-cause \(Y\) and for \(Y\) to Granger-cause \(X\). This would indicate a bi-directional predictive relationship.
- **Limitations**: The concept is based on linear models, and the results might not hold in non-linear systems. Also, if the lag structure or model is misspecified, it could lead to incorrect conclusions.

Granger causality tests are widely used in econometrics, neuroscience, and other fields where time series data are available, and researchers are interested in understanding potential predictive relationships between variables.
