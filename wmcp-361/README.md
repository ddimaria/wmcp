# WMCP361: Efficient Investment Portfolios

- [WMCP361: Efficient Investment Portfolios](#wmcp361-efficient-investment-portfolios)
  - [Statistical Concepts](#statistical-concepts)
    - [Calculating Returns](#calculating-returns)
      - [Types of Returns](#types-of-returns)
    - [Returns Distributions](#returns-distributions)
      - [Measuring Risk](#measuring-risk)
      - [Normal Distributions](#normal-distributions)
      - [Standard Deviation](#standard-deviation)
      - [Asset Distributions](#asset-distributions)
      - [Non-Normal Investments](#non-normal-investments)
      - [Forecasting Future Growth of Client Assets](#forecasting-future-growth-of-client-assets)
    - [Covariance](#covariance)
      - [Measuring Covariance](#measuring-covariance)
    - [Correlation](#correlation)
      - [Calculating the Correlation Coefficient](#calculating-the-correlation-coefficient)
      - [Asset Class Returns and Correlation](#asset-class-returns-and-correlation)
  - [Modern Investment Theory](#modern-investment-theory)
    - [Modern Portfolio Theory](#modern-portfolio-theory)
    - [Capital Asset Pricing Model](#capital-asset-pricing-model)
      - [Market Portfolio and Risk](#market-portfolio-and-risk)
    - [Market Efficiency](#market-efficiency)
    - [Portfolio Risk-Adjusted Returns](#portfolio-risk-adjusted-returns)
    - [Asset Pricing](#asset-pricing)
    - [Evaluating Alpha](#evaluating-alpha)
  - [Efficient Household Portfolios](#efficient-household-portfolios)
    - [Return Predictors](#return-predictors)
      - [Ordinary Least Squares (OLS) Regressions](#ordinary-least-squares-ols-regressions)
      - [Survivorship Bias](#survivorship-bias)
    - [Liquid Investments](#liquid-investments)
      - [Short-Term Investment Options](#short-term-investment-options)
      - [How Much Should a Household Hold in Liquid Assets](#how-much-should-a-household-hold-in-liquid-assets)
      - [Building a Cash Reserve in a Portfolio](#building-a-cash-reserve-in-a-portfolio)
    - [Home Equity](#home-equity)
    - [Human Capital](#human-capital)
  - [Portfolio Strategies](#portfolio-strategies)
    - [Rebalancing](#rebalancing)
    - [Liability-Driven Investing (LDI)](#liability-driven-investing-ldi)
      - [Liability-Driven Optimization (aka Surplus Optimization)](#liability-driven-optimization-aka-surplus-optimization)
  - [Fixed-Income Instruments](#fixed-income-instruments)
    - [Bond Features](#bond-features)
    - [Bond Pricing](#bond-pricing)
    - [Federal Bonds](#federal-bonds)
    - [Municipal Bonds](#municipal-bonds)
    - [Corporate Bonds](#corporate-bonds)
    - [Bond Credit Risk Premium](#bond-credit-risk-premium)
    - [Bond Investments](#bond-investments)
  - [Equity Instruments](#equity-instruments)
    - [Equity Financing](#equity-financing)
    - [Microstructure](#microstructure)
    - [Corporate Payout](#corporate-payout)
    - [Dividend Stocks](#dividend-stocks)
    - [Firm Valuation](#firm-valuation)
    - [Firm Characteristics](#firm-characteristics)
      - [Grouping Companies/Stocks](#grouping-companiesstocks)
      - [Three Factor Regression Coefficients](#three-factor-regression-coefficients)
      - [The Sector Rotation Strategy](#the-sector-rotation-strategy)
  - [Diversified Securities](#diversified-securities)
    - [Market Indices](#market-indices)
      - [Stock Indices](#stock-indices)
      - [Bond Indices](#bond-indices)
      - [Performance Bemchmarks](#performance-bemchmarks)
    - [Mutual Funds and ETFs](#mutual-funds-and-etfs)
      - [Load Charges and 12b-1 Fees](#load-charges-and-12b-1-fees)
      - [Expense Ratios and Shares](#expense-ratios-and-shares)
      - [Closed-End Funds](#closed-end-funds)
      - [ETFs](#etfs)
    - [Fund Features](#fund-features)
      - [Fund Taxation](#fund-taxation)
      - [Capital Gains for Estates](#capital-gains-for-estates)
      - [Mutual Fund Shares](#mutual-fund-shares)
      - [Unit Investment Trusts (UIT)](#unit-investment-trusts-uit)
      - [Analyzing Mutual Funds](#analyzing-mutual-funds)
    - [Global Investing](#global-investing)
      - [The Role of the U.S. Market and International Allocation](#the-role-of-the-us-market-and-international-allocation)
    - [Emerging Market Funds](#emerging-market-funds)
    - [Life-Cycle Funds](#life-cycle-funds)
    - [REITs](#reits)
    - [Responsible Investing](#responsible-investing)
  - [Other Financial Instruments](#other-financial-instruments)
    - [Real Estate Investing](#real-estate-investing)
    - [Annuities](#annuities)
      - [Annuity Riders](#annuity-riders)
      - [Annuity Payout Example](#annuity-payout-example)
    - [Permanent Life Insurance](#permanent-life-insurance)
      - [Whole Life Insurance](#whole-life-insurance)
    - [Universal Life (UL) Insurance](#universal-life-ul-insurance)
    - [Alternative Investments](#alternative-investments)
      - [Private Equities](#private-equities)
      - [Commodities](#commodities)
      - [Cryptocurrency](#cryptocurrency)
      - [Hedge Funds](#hedge-funds)
      - [Derivatives](#derivatives)
      - [Short Selling](#short-selling)
      - [Structured Products](#structured-products)
      - [Option Protected Products](#option-protected-products)


## Statistical Concepts

### Calculating Returns

* **Basis**: The price you pay for a financial asset today.  The basis is relevant for tax calcuations.
* **Payout**: The price you receive for selling an asset.
* **Capital Loss**: When the payout is less than the basis price.
* **Capital Gain**: When the payout is greater than the basis price.
* **Holding Period Return**: Capital gains plus any revenue that the asset generates (e.g. dividends).  Dividends (and reinvested dividents) trigger a new basis for the portion of the asset purchased and can trigger a taxable event.
* **Net Returns**: Payout - Basis - other expenses (e.g. cost of selling the asset, taxes, ...etc.)

#### Types of Returns

* **Arithmatic Returns**: Takes the number of years into account => arithmatic mean return = total return/number of years
* **Geometric Returns**: Takes compounding into account => geometric mean return = (1 + holding period return)<sup>1/n</sup> - 1.  These returns are the most accurate calcuation of how money grows over time.  For each year: [(1 + returns<sub>1</sub>) * (1 + returns<sub>2</sub>)]<sup>1/n</sup> - 1 ...n is the number of years
* **Dollar-Weighted Returns**: AKA Investor Returns. Incorporates cash flows, it's estimated using an Internal Rate of Return (IRR) calculation.
* **Time-Weighted Returns**: AKA Total Returns. Independent of cash flows, it's estimated by geometrically linking the return for sub-periods (e.g. monthly). Mutual funds report time-weighte returns.  Total returns can mask individual performance in investors purcahsed the asset after it fully grew.
* **Real Returns**: The rate of return that subtracts inflation. real retrns = ((1 + nominal rate)(1 + inflation rate)) - 1.  For each year, the *geometric mean real return* is: [(real returns<sub>1</sub>) * (real returns<sub>2</sub>)]<sup>1/n</sup> - 1 ...n is the number of years.

### Returns Distributions

#### Measuring Risk

* **Quantifying Risk**: helps advisors and clients analyze the risk-based implications of their portfolios
* **Probabilities and Outcomes**: use historical data to analyze statistical probabilities and project future outcomes
* **Expected Return**: the average (aka central tendency) expected returns
* **Measuring Distribution of Outcomes**: we typically assume a normal distribution of outcomes (aka bell curve)

#### Normal Distributions

Returns follow a normal distribution (aka bell curve).  Cash (liquid investments), least look like a bell curve with most returns clustering around 1 standard deviation below the mean (-.06% - 1.35%).

* **Moments**: the shape of the bell curve
* **Average**: average - the 1st central moment of return distribution
* **Variance**: volatility - the 2nd central moment of return distribution 
* **Skewness**: lack of symmetry - the 3rd central moment of return distribution
* **Median**: the 50th percentile (this middle, not the same as average)
* **Mode**: the most frequent observations

Median is often more valuable b/c outliers skew the average 


#### Standard Deviation

The Standard Deviation is the square root of the average deviation (variance).

* 1 standard deviation: 68%
* 3 standard deviation: 95%
* 2 standard deviation: 99.7%

An asset that has an expected return of 10% with a 20% standard deviation:

* 1 standard deviation: 68% of the time returns will be -10% - 30%
* 3 standard deviation: 95% of the time returns will be -30% - 50%
* 2 standard deviation: 99.7% of the time returns will be -50% - 80%

**Tail Risk**: the risk of a negative, unlikely, or extreme event

#### Asset Distributions

* **Positive Skewness**: there are more extreme numbers to the right of the median than the left.  Example: Venture Capitalists.
* **Positive Skewness**: there are more extreme numbers to the left of the median than the right. Example: Catastrophe Bonds.
* **Kurtosis/Fat Tails**:  extreme events (e.g. black swans) that affect the size of the tails on either side of the bell curve.
* **Leptokurtic Distribution**: more peaked with fatter tails (Positive Kurtosis)
* **Mesokurtic Distribution**: a normal distribution
* **Platykurtic Distribution**: less peaked with thinner tails (Negative Kurtosis)

Skewness affects the mean, median, and mode of normal distributions (where they are the same).

Most asset classes have had negative skewness with positive kurtosis.  High yeild bonds are an extreme example of this.

#### Non-Normal Investments

Standard deviantion is **not** used for non-normal distributions.  Products with guaranteed returns cannot be negative and are non-normal.

**Downside risk** is the risk that an asset will perform below some minimal acceptal return (MAR).

#### Forecasting Future Growth of Client Assets

Retirees get most of their growth before they retire, so can take less risk once they retire.  Early in retirement, the **sequence of returns** risk has a greater impace than later in retirement.

Deterministic & Stochastic models help adjust for sequence risk.
**Deterministic**: assumes that asset returns are known ahead of time (e.g. 7% annual returns, or a target date fund).  It's relatively straightforward and simple.  However, they don't respond well to changes.
**Stochastic**: (aka random or monte carlo simulation), assumes a variation in asset returns over time. Monte carolo typically varies returns on a single projection path (called **runs**).  There are typically 500+ runs done in a single simulation.  The simulations can provide context into the range of possible outcomes, hence assist in goal estimations (probability of success).  Not necessarily a normal distribtion with a Monte carlo.

Model Assumptions:
* Should be as accurate as possible (don't use optimisic assumptions)
* Should include investment fees and expenses
* Should take goal flexibility into account
* For Determinisitc, inputs should be the expected geometric (compounded) returns.  It's geometric b/c there is no randomness.  US stocks average 7% geometric returns.
* For a Monte Carlo simulation should be the expected arigthmetic (simple average) returns.  It's arithmetic b/c of the randomness embedded in the forecast.  US stocks average 9% arithmetic returns.
* Assumptions/projections should be used to create reasonable expecatations of outcomes, and should be revised on a regular basis.

### Covariance

Individual asset risk is expressed as **volatility** (the average deviation from the arithmetic mean, or simply the standard deviation).

Covariance explains investment risks across different assets.  It measures the combined risk of assets against their respective means at any given time.  In a **positive covariance**, assets tend to have above average gains at the same time. In a **negative covariance**, one asset will have higher average gains while the other asset wih have lower average gains at the same time.  An asset that has a consistent negative covariance is known as a **hedge** (e.g. life insurance or any contingent claim).  A hedging financial product is known as a **financial derivative**.

Variance is the average annual distance from the average over a period of time.  High variance means returns will be well above OR below the average.  Low variance is very close to the mean return.

Return can be independent in the same asset class (e.g. equities).  Even though they are indepedent, they have some correlation as they are affected by the same market forces.

The **Black-Scholes Model** shows that the expected return of 2 assets that have a perfect negative covariance should not be greater than the risk-free rate of return (e.g T-Bills).  In other words, having perfect negative covariance will reduce risk, but will also reduce returns, which may OR may not match the client's goals.

#### Measuring Covariance

|         | Stock A | Stock B |
| ------- | ------- | ------- |
| Year 1  | 14%     | 10%     |
| Year 2  | 10%     | 2%      |
| Average | 12%     | 6%      |

First, calcuate the average:  Stock A is 12%, Stock B is 6%.  Now calcuate the deviation from the mean and the product

**Deviation from the mean and Product**

|        | Stock A           | Stock B            | Product            |
| ------ | ----------------- | ------------------ | ------------------ |
| Year 1 | (.14 - .12)   .02 | (.10 - .06)    .04 | (.02 * .04) .008   |
| Year 2 | (.10 - .12)  -.02 | (.02 - .06)   -.04 | (-.02 * -.04) .008 |

The covariance is the sum of the products for all years: 

> Covariance = (Sum of Products)/(Number of Years - 1)

> Sum of Products: .008 + .008 = .0016 
> Covariance = .0016/(2 - 1) = .0016 = Positive Covariance

### Correlation

The **correlation coefficient** shows the relationship between the returns of 2 assets.  Correlation ranges from -1 to +1.  -1 represents a high negative correlation (they move in opposite directions).  +1 represents a high positive correlation (they move in the same direction).  At zero, the assets are uncorrelated (they don't move together).

Combining assets with a correlation less than zero is called **diversification**.

#### Calculating the Correlation Coefficient

|         | Stock A | Stock B |
| ------- | ------- | ------- |
| Year 1  | 0%      | 3%      |
| Year 2  | 5%      | 5%      |
| Year 3  | 10%     | 7%      |
| Average | 5%      | 5%      |

To calcuation correlation, we first need to calculate the covariance:

|        | Stock A          | Stock B            | Product            |
| ------ | ---------------- | ------------------ | ------------------ |
| Year 1 | (.0 - .05)  -.05 | (.03 - .05)   -.02 | (-.05 * -.02) .001 |
| Year 2 | (.05 - .05)  .0  | (.05 - .05)    .0  | (.0 * .0)     .0   |
| Year 3 | (.10 - .05)  .05 | (.07 - .05)    .02 | (.05 * .02)   .001 |

> Covariance = (Sum of Products)/(Number of Years - 1)

> Sum of Products: .001 + 0.0 + .001 = .002 
> Covariance = .0012/(3 - 1) = .001 = Positive Covariance

> Correlation Coefficient = Covariance/(Product of Standard Deviations)
**NOTE**: Product of Standard Deviations is complicated and can't be expressed in markdown

#### Asset Class Returns and Correlation

**Availability Bias**: overweighing recent information.  This bias can lead to diverging to a financial plan.

The **Periodic Table of Investment Returns** shows annual performance of different asset classes.  The trend is that different asset classes perform better at different times (reinforcing diversification and "staying the course").  Emerging markets are the most volatile, though has relatively high returns.

Since diversification is important, it's best to hold asset classes that aren't well correlated (< 1, e.g. stocks and high-yield bonds).

Correlation is not constant over time.  Declining markets tends to bring correlations to 1.

## Modern Investment Theory

### Modern Portfolio Theory

**Modern Portfolio Theory (MPT)** combines utility theory and diversification by containing risky and risk-free assets to lower overall portfolio risk and volatility, while maximizing returns.  Created in 1952 by Harry Markowitz.  Risk should be matched to the investor.  Investors need to accept variance in order to achieve higher returns.

The **Efficient Frontier** (aka the Merkowitz Bullet) strives to maximize returns and minimize risks. On a graph, it's shaped like a concave hyperbola (like the letter `C`) and is the line that shows the combination of assets to give the highest return for each level of standard deviation.  At a point on the frontier, more volatility is needed for smaller increments of gains.

The **Market Portfolio** is a hypothetical asset that is a mix of all competitively priced investments with the highest possible return for a given risk level.

Market Portfolio Assumptions:
* Markets are efficient: price is based on risk
* Sharpe Ratio: combining efficiently priced assets decrease risk over a given return rate
* Mutual Fund Theorem: optimal portfolio is owning a high yielding fund and a risk-free fund
* Allocating risky and risk-free assets: allocation is a based on an investor's risk tolerance (related to flexibility of goals)

Modern Portfolio Theory informs Life Cycle Theory by showing investing tradeoffs between risk and return.

### Capital Asset Pricing Model

#### Market Portfolio and Risk

The market portfolio is as risky as the market (the max Sharpe ratio).

**Systematic Risk** is the risk inherent in the market portfolio.  The risk that all risky assets will rise and fall randomly.

**Unsystematic Risk (aka Idiosyncratic Risk)** is the risk that can be diversified away by combining assets.  Systematic risks still exist after unsystematic risks are removed.

Combining assets with a low correlation is more efficient and avoids idiosyncratic risk.

If the portfolio Beta is greater than 1, the portfolio is more volatile than the whole market.
If the portfolio Beta is less than 1, the portfolio is less volatile than the whole market.
Beta (the amount of systematic risk) is calculated by measuring the correlation of the market portfolio vs an investment/asset.

The **CAPM (Capital Asset Pricing Model)** states that the expected return of an asset is a function of the amout of systemic risk it has.  It's related to the (1) expected rate of return today (risk-free rate) in exchange for a higher payout in the future and (2) taking on risk (risk premium).

Risk averse investors require a higher risk premium.  Risk premium can be estimate by looking at historical risk of equity premiums vs risk-free investments.  In the US in the 19th century, the equity premium (geometric return) was 2.3%, and it was 4.8% (3.8% globally) in the 20th century.  Risk premium = Average Stock Returns - Average Bond Returns.  The equity risk premium has decreased in the last few decades (less than the 4.8% historical).

> Mutual fund has a beta of 1.4.  The risk free rate is 2% and the equity risk premium is 3%.
>
> The expected return = .02 + (1.4 * .03) = 0.062 = 6.2%

Beta is calculated using regression analysis, which uses the independent variables to predict the dependent variables.

The portfolio beta = the beta of sum of each asset multiplied by the percentage of the asset in the portfolio.

> 60% with beta = 2, and 40% of beta = 1, portfolio beta = (0.6 * 2) + (.4 * 1) = 1.6

Beta does not give enough information about the fundamentals of a company and is of limited value when making stock selections. Beta is probably a better indicator of short-term rather than long-term risk. To avoid problems with beta, avoid IPOs, assets in bankruptcy, penny stocks, small cap growth stocks with low profitability + high investment. 

### Market Efficiency

Returns above CAPM have a positive **alpha**, though most funds have a negative alpha, where the alpha is equivalent to the investment fees.

An **Event Study** assesses stock prices change in response to new information.  An example is the use of a private company jet by the CEO in a study by Yermak (market fell by 1.1% the day it was reported).  This shows that markets are efficient because they react immediately to new information.

The **Efficient Market Hypothesis (EMH)** has 3 forms:
* **Weak-Form**: Stock prices are random (aka "ramdom walk") and not related to public information. The existence of weak-form markets allow for analysts to benefit from research.
* **Semi-Strong-Form**: All publicly available info is instantly incorporated into stock prices.  The Yermak jet study exemplifies this market.  Acting on private information in semi-strong markets is illegal, but allows for extra returns abouve the market.
* **Strong-Form**: All Public and Private info is instantly incorporated into stock prices.

| EMH         | Technical Analysis | Fund Analysis | Insider Info |
| ----------- | ------------------ | ------------- | ------------ |
| Strong      | X                  | X             | X            |
| Semo-Strong | X                  | X             | ✓            |
| Weak        | X                  | ✓             |              |

Stock prices can be random, but human nature is to attempt to find patterns even when they do not exist.

Financial gurus should be ignored.  Stay the course and don't change course when hearing predictions.

### Portfolio Risk-Adjusted Returns

Adding assets to an existing portfolio that correlate less than 1 (0 is best), the portfolio risk is reduced.

In the US, stocks average a 12% return with a 20% standard deviation.  Safe assets (short term gov't bonds) average 3.5% with a 3% standard deviation.

What is the expected return of a 50% stocks/50% bonds portfolio?  The sum of the weights times the average returns:

> (.5 * .12) + (.5 * .035) = 7.75%

What is the standard deviation of a 50/50 portfolio? Since they are uncorrelated (covariance of zero), the sum of the weights times the standard deviation divided by the risk reduction (1/2):

> (.5 * .2/2) + (.5 * .03/2) = 11.5% // this is wrong???

The **Sharpe Ratio** is the amount of return expected for a given risk level.

> sharpe ratio = (expected return - risk-free return)/standard deviation

Expected return is 5%, risk-free rate is 2%, standard deviation is 10%

> sharpe ratio = (.05 - .02)/.1 = 0.3 

Standard deviations aren't as helpful for estimating risk in rare, worst-case events.  For these rare events, **Value-At-Risk (VaR)** is used (by JP Morgan in 1990s).  It shows the potential loss at a given probability level.  A one day 5% VaR of $100,000 means there is a 5% probability that the portfolio will experience a 1 day decrease of $100,000.  VaRs are rough estimates, whose effecacy varies with assumption effecacy.  VaR is trying to project the one day loss within a given confidence interval.

**Conditional Value-At-Rish (CVaR)** is similar to VaR, but reports the **average potential loss** (vs loss in VaR). 

### Asset Pricing

Asset pricing is done via the Capital Asset Pricing Model (CAPM).  For efficient markets, asset prices can be determined via systemic risk (i.e. beta) by estimating the covariance of the market.  The *cost of capital* is also important in asset pricing and it easily determined by bond rates.  The cost of equity/stock financing is harder to determine b/c it's stochastic (random), but can be estimate in standard deviation intervals via statistics.

**The Pricing Kernel**: this is used to estimate pricing years into the future.

> The Pricing Kernel = (1/1 + Discount Rate)<sup>Num Years</sup>

**The Discount Rate**: has 2 components: (1) the time value of money and (2) asset riskiness.

> The Discount Rate = Opportunity Cost + Riskiness

The CAPM can be used to estimate the discount rate in efficient markets.  The Opportunity Cost component is comprised of the risk-free rate.  The riskiness component is comprised of the risk premium of the asset (the bets of the asset times the market risk premium).

The **law of one price** states that all financial assets are priced via the CAPM and the price reflects the systemic risk of the asset.

For a risk-free assset, the beta is zero (no risk premium).  To calculate the price using a risk-free rate of 3% with a payout of $1 in in 1 year:

> The Pricing Kernel = (1/1 + Risk-Free Rate)<sup>Num Years</sup>
> 
> = (1/1.03)<sup>1</sup> = 0.971<sup>1</sup> = 0.971
>
> If the payout is $1 in 1 year, then the price should be $0.97
>
> In 2 years, 0.971<sup>2</sup> = 0.943
>
> If the payout is $1 in 2 years, then the price should be $0.94

For a risky assset with a beta of 1.  To calculate the price using a risk-free rate of 3% and a market risk premium of 4% with a payout of $1 in 1 year:

> The Pricing Kernel = (1/1 + Risk-Free Rate + (Beta * Market Risk Premium))<sup>Num Years</sup>
> 
> = (1/1 + 0.03 + (1 * .04))<sup>1</sup> = 0.93<sup>1</sup> = 0.93
>
> If the payout is $1 in 1 year, then the price should be $0.93
>
> In 2 years, 0.973<sup>2</sup> = 0.867
>
> If the payout is $1 in 2 years, then the price should be $0.87

.072

For a beta of 0.5 and all other values the same:

> = (1/1 + 0.03 + (0.5 * .04))<sup>1</sup> = 0.93<sup>1</sup> = 0.952

If the risk-free rate is 2% and the market risk premium is 4%, what is the fair price of an investment with a beta of 1.3 that is expected to pay $1,000 in 3 years?

> the required return = 2% + 1.3 x 4% = 7.2%
> 1/(1 + .072)<sup>3</sup> = 0.933<sup>3</sup> = 0.8117, this times 1000 = $812

### Evaluating Alpha

Alpha (aka Jenson's Alpha) is calculated through the beta regression.  Alpha is the excess return above and beyond expected returns base on the asset's market risk.

Positive alpha means the fund has an excess return beyond it's beta (systematic risk).

Alpha is the y intercept.   Markets have an alpha of zero and a beta of 1.  The alpha of a fund is usually negative and equal to the fees of the fund.

**R-Squared** explains the amount of excess return of an asset is from alpha and from beta.  Ranges b/w 0 - 1 (0% - 100%).  It's also know as te **goodness of fit**.

With a risk-free rate of 2%, a risk premium of 3%, a beta of 2 and an alpha of 0, R-squared is:

> R<sub>p</sub> = alpha + (beta * risk premium) + risk-free rate
>
> = 0 + (2 * .03) + .02 = .08 or 8%

R-squared is low or zero when there is significant deviation from what we'd expect returns to be (a lot of unsystematic risk).   If the actual is the same as the predicted return, then R-squared is 1 (very little unsystematic risk).

On average, managed funds have an alpha (gross of fees) of zero.  When accounted for fees (net of fees), managed funds tend to have negative alpha.  In a CAPM regression, fees are the strongest predictor of alpha.

Persistence is the consistency of returns over time.  There is little evidence that fund managers can achieve persistence.  This is largely due to markets being efficient.

**Active** fund management involves actively researching and selecting investments in persuit of positive alpha.  **Passive** fund management involves selecting a market index (e.g. index fund).

> Expected Returns = risk-free rate + (beta * market risk premium)

Average beta = 1.2, equity premium = 5%, risk-free rate = 3% 

> Expected Returns = 0.03 + (1.2 * 0.05) = 0.09 = 9%

If a fund manager can achieve 12%, then the alpha is 12% - 9% = 3%.

The average alpha of actively managed funds is -1.1%.

The Carhart model is a 4-factor model that controls for size, value, momentum and beta.

CAPM isn't enough, wealth managers need to select the "right" factors when creating portfolios.

**Gamma** is the benefit that an advisor can add by helping investors accomplish goals (e.g. advising on tax optimization, behavioral finance, ...etc).

## Efficient Household Portfolios

Determining an investors risk level is the first step in creating a portfolio.  A **risk tolerance questionnaire (RTQ)** is used to estimate investor risk tolerance (risk level is expressed as an equity target).

**Mean Variance Optimization (MVO)** is the most common form of portfolio optimizatio (created by Harry Markowitz).  It has 3 major inputs: (1) return (2) standard deviation (3) correlation between asset classes.  The goal is to optimize the returns for a given level of risk.  Complex portfolios add diversification and are more efficient than basic portfolios.  This is consistent with modern portfolio theory.  This complexity can be reduced if picking a single fund that holds all of the diversified assets.

### Return Predictors

Most factors don't hold up the empirical analysis in most cases, but a few are reliable at gauging return.  The **Fama-French 3 Factor Model** finds higher performance in smaller companies as well as in under-valued companies.  This 3 Factor Model has become the standard way to model expected performance: company size, value orientation (book value), market excess return.

**The Momentum Effect** states that winning stocks are more likely to continue winning and losing stocks are more likely to continue losing.  Barber and Odeen found investors tend to hold onto losing stocks and sell winning stocks due to loss aversion.  The Momentum Fffect has been combined with the Fama-French 3 Factor Model to become the **4 Factor Model**.

Growth companies (high book values) perform worse during bear markets than smaller or value-priced companies.  This is why stocks recommended on TV tend to underperform the market.

Low volatility stocks perform better in the past than CAPM would predict.  Also, less liquid (and less traded) stocks tend to outperform the market over time.  The same holds for highly profitable companies (low profit companies are harder to value).

> Profitability Ratio = (Revenue - Costs) / Book Value

Evidenced-based portfolios take all of these factors into account, which deviates from the market portfolio.  Factors might present risks that are baked into the market that may make them more resemble the market portfolio.

#### Ordinary Least Squares (OLS) Regressions

Regressions are use to test if a phenomenon depends on characteristics (age, turnover, expenses, ...etc.).

The dependent variable in OLS is mutual fund returns (the 3 year performance beginning on December).  

The independent variables are the mutual fund characteristics.  They include:
* Historical 5-year performance
* Historical 5-year standard deviation
* Expense ratio
* Turnover
* Age of the fund
* Average manager tenure
* Fund size
* Fund status (is it an index fund?)

After monitoring regressions, it was found that only 2 variables actually predicted returns:
* Expense ratios (a 1% increase in expense results in a 1.16% reduction in performance)
* Fund size (not nearly as relevant as the expense ratio, larger funds outperform the smaller ones on average)

#### Survivorship Bias

Funds that underperform at closed and outperforming ones stay open.  This results in a **survivorship bias**.  Investment managers should be aware of survivorship bias when recommending funds as any presented alpha will likely disappear when combined with losing funds, leaving only the expense ratio as the relevant metric.

Smart Beta (or Strategic Beta) is just another form of active management, with the same pitfalls.

### Liquid Investments

#### Short-Term Investment Options

Liquid assets are cash or cash equivalents (not necessarily held in currency).  Cash acts as a buffer to cover expenses in order to avoid pulling out of other invested assets.

The cost of holding liquid assets is the lower return of safe assets.  Liquid assets can be converted into cash and doesn't fluctuate much in changing markets, which makes the suited for short-term, inflexible goals or unforeseen expenses.

#### How Much Should a Household Hold in Liquid Assets

If there are planned near-term expenses, then households should home more in liquid assets.  Homeowners should hold more in liquid assets since home expenses are **lumpy**.

Liquidity costs include the absense of the illiquidy premium (less liquid assets demand a premium).  They also miss out on the term/duration preimum, which gives a preimium for holding onto the asset.

Liquid assets should not be held in a tax sheltered/advantaged account due to lower premiums and early withdrawl penalties.

Since liquid assets are expensive (via opportunity cost), other semi-liquid assets should also be considered for an emergency fund (cash-value life insurance, home equity, taxable bonds, stocks w/o capital gains).

#### Building a Cash Reserve in a Portfolio

* Checking Account: good for regular expenses, they have fees and pay low/no interest, FDIC or NCUA insured up to $250,000 per account.
* Savings Account: slightly less liquid than checking accounts, but slightly higher interest rates, FDIC/NCUA insured, can be electronically transferred into a checking account for spending needs
* Money Market Account: slightly less liquid than savings accounts (has restrictions), but slightly higher interest rates, FDIC insured
* Money Market Mutual Funds: open-end investment companies that invest in short-term investments (60 days), four types: treasure, government, prime, and municipal, they also invest in corporate bonds (commercial paper), NOT FDIC insured, net asset value (NAV) of $1 per share, brokerage accounts typically send money to these funds when assets are sold or when dividends pay out, funds must maintain **weekly liquid assets**
* Certificates of Deposit (COD): FDIC insured timed deposits, matures from 3 months up to 5 years, less liquid than other bank accounts, can pay similar to a safe corporate bond
* Short-Term Bonds: short-duration bonds, typically matures in 1 to 3.5 years, NOT FDIC insured
* Stable Value Funds: offered in defined-contribution plans (e.g 401k plans), returns similar to intermediate-bond funds, stability and liquidty similar to money market mutual funds, they have guarantees regarding fluctuations, but can still experience a loss

Ultrashort Bond Funds have experiences higher losses than one would expect (up to 27% in 2008)

### Home Equity

2/3 of Americans own homes (increases at higher income levels).  Houses have both systematic and indiosyncratic risks, and fluctuate more than expected (30% reduction in 2008).  The standard deviation of individual homes is around 12%, similar to a 50/50 portfolio.  Higher lown-to-value homes are more risky, as well as homes in locations with low economic diversification. Homes only have a 0.2 correlation with corporate REITS.

Home equity should be added as an asset to the balance sheet. Home equity can be invested to create more diversification.

The historical average return on homes has been about 1% higher than inflation.  Denver and Portland have enjoyed a high return with low risk.  Las Vegas has experienced high risk with low returns.  The standard deviation of a home increases over time.  Additional costs can reduce the average 1% return (insurance, taxes, maintenance, improvements).

The longer someone lives in a home, the better of an investment it is.  Homeowners have higher networth than renters since a mortgage payment acts as an automated investment.  People tend to say in homes abou 1/2 as long as they think.

The mortgage cost should be considered a liability on the balance sheet.

Even though it may not make sense, it can make a client feel better to pay down/off their mortgage.

> Net Return = Mortgage Rate / (1 - Marginal Tax Rate)

4% mortgage, 33% tax rate:

> 0.04 / (1 - 0.33) = 6% net return by paying off your mortgage


### Human Capital

Human capital is worth 4x more than stock, bonds, and housing in a household.  It is the total economic value of an individuals set of skills and talents.  Since you can't trade your human capital asset, it's hard to price it.  It is typically estimated via the net present value of future earnings, which takes wage growth into account.  Human capital risks vary by individual.

Human capital is largest early in the lifecycle.  The relative value in a portfolio changes over time as other investments start to accumulate and grow.  It's a relatively safe asset that is similar to a risky bond.  It's similar to a 30/70 portfolio (30% stocks, 70% bonds).

Retirement can be thought of as the life cycle stage in which human capital drops to zero.  Converting human capital into invested assets is done in order so smooth consumption late in life.

Loss of a job is a risk of human capital, which varies by industry/occupation.  Government, healthcare and professional service jobs are considered safe.  Mining, construction and manufacturing jobs are risky. Commision jobs are more risky than salaried jobs.

Human capital risk should be considered as part of the whole portfolio (including idiosyncratic risk and it's covariance with other assets).  Riskier human capital shoud be paired with lower risky investments, and vice versa (risky jobs should have more in their emergency fund).  Investing in assets that differ from the industry of human capital adds diversification.

As human capital decreases with age, bond allocations should increase in order to maintain the same asset ratios (since human capital is a 30/70 portfolio).  Human capital isn't on a portfolio statement, but should be discussed with the client.

## Portfolio Strategies

### Rebalancing

Rebalancing helps maintain the level of risk as asset allocations change over time.  Risky assets have more random returns.  Changing performance of risky assets changed the portfolio mix.

Rebalancing involves transaction and tax costs in certain accounts/funds.  Rebalancing doesn't maximize wealth, it minimizes risk in order to stay within an investor's risk tolerance.

In bull markets, stocks are usually sold to buy bonds, and vice versa in a bear market.  These are opposite our tendencies associated with risk aversion, so automated or periodic reblancing can help overcome this.

Rebalancing approaches:
* Using a date or time interval (doesn't consider how much the portfolio is out of alignment)
* Tolerance Bands: Set deviation levels to trigger (e.g. if desired allocation changes by more than 2%) (doesn't apply the same risk impact)

A mix of the above may be optimal, and can vary per client.  Rebalancing should be done *at least* once a year or after a major market shift.  Quarterly rebalancing doesn't have advantages over annually.

To reduce transaction/tax costs, rebalancing can happen by way of directing new contributions to the regain balance.

Rebalancing should happen across ALL accounts, not just within individual accounts.  Tax sheltered/advantaged accounts should be used to rebalance over taxable accounts to avoid additional tax.

### Liability-Driven Investing (LDI)

Future expenses can be viewed as liabilities.  Investing can be tailored to meet the liability at some point in the future.

The risk of an investment for meeting a future goal isn't the volatility before the goal, but the variation in payout at the time the investment is needed.  Additionally, future goals may get more expensive over time.

LDI is the asset allocation approach that focuses on liabilities over short-term volatility.  Not considering liability is know as an **asset-only approach**.

3 common types of LDI:
* **Cash-Flow Matching** most conservative, it matches the payout with the time horizon and cost/size of the liability, this is most appropriate when the future expense is known ahead of time and are not flexible or affected by inflation.
* **Duration Matching** matches the interest rate sensitivity on the asset portfolio to the interest rate sensitivity on the liability, popular in defined-benefit (pension) plans, pays regardless of performance, affected by interest rates.
* **Liability-Driven Optimization (aka Surplus Optimization)** least conservative, focuses on liabilities as an after-inflation, flexible spending goal, the surplus is the difference in the risk of the investment minus the risk of the liability, allows for riskier assets.

Increased interest rates make future expenses cheaper and vice versa.

#### Liability-Driven Optimization (aka Surplus Optimization)

> Assets - Liabilities = Surplus

A positive surplus is good and a negative surplus is bad.  

This allows for the addition of riskier assets in portfolio optimization by directly selecting the amount of surplus risk in a portfolio.  They address the risk of meeting a future goal.

In a goal-based investing framework, the downside of investing in risky assets could have a lower probability of meeting goals if returns are lower than expected.  The optimal portfolio for some is to accept some risk in order to meet or exceed their goal.  Evaluate the goal over time.

## Fixed-Income Instruments

### Bond Features

A **bond** is a form of debt-financing where there is an obligation to pay back money plus interest to investors.  The initial amount paid for the bond is called the **par value** (or face value).  Each repayment from the bond is called a **coupon**.  An **indenture** is the bond contract that includes the interest rate and is paid semi-annually.  The **maturity date** is the date when the bond issuer must pay back the bond's par value.  **Zero coupon bonds** don't pay coupons, but rather offer the par value at a discount and pay the face value at maturity.

**Credit quality** is determined by a 3rd party (Moody's, Standard and Poor's) to estimate the ability of the entity to repay the debt.  Ranking from highest to lowest: AAA, AA, A, BBB, BB, B, CCC, CC, C.  A-rated bonds (and some high B-rated bonds) are considered investment grade, while C-rated bonds are called **junk bonds**, which pay a premium.

Entities that issue bonds:
* Government: governments and municipalities issue bonds to pay for projects.  US Dept of Treasury bonds are called **treasuries**.  **T-Bills** (or Treasury Bills) mature in 1 year or less.  **Treasury Notes** last 1 - 10 years and **Treasury Bonds** last 10 years or more.
* Corporate: corporations issue bonds, the quality of the bonds vary per corporation.  **Short-term corporate bonds** mature within 5 years, **intermediat-term bonds** mature between 5 - 10 years.  **Long-term** bonds mature in 10 or more years.

In the marketplace, a bond value will rise if newer bonds are offered at a lower coupon rate (aka **yield**), and decrease in value if subsequent bonds pay at a higher rate.

> Current Yield = Annual Coupon Payments / Current Market Price

A rise in interest rates or a reduction in credit quality can cause bonds to be sold at a discount.  They are sold at a premium if interest rates fall or credit quality increases.

In general, the return on bonds is higher the further out into the future the bond maturity is.  Additionally, longer-term bonds are riskier in terms of defaults and interest rates.  

The **term strucutre of interest rates** is the differentiation in yield by different maturity dates.  The **yield curve** generally slopes up, but can be flat or inverted before or during a recession.

Long-term government bonds pay 70% more than short-term government bonds.  High-yield bonds earn 25% more than long-term government bonds.  Both high-yield and long-term government bonds have a higher volatility.

Re-investing short-term bonds involves reinvestment risk, which increases the range of possible payouts over time.

Riskier bonds pay a higher interest rates.  Highly-traded bonds are more liquid and have lower interest rates.  Municipal bonds offer a tax benefit, so also have a lower interest rate.  Corporate and some government bonds have a higher default risk, so they pay a higher interest rate.

**Callable bonds** contain give the bond issuer the option to repay the bond before maturity if interest rates are lower.  These bonds pay a higher interest rate.

THe **Macaulay Duration** is the average amount of time it takes to receive the present value of the expected cash flows from a bond.

> Bond Duration = (Present Value of Each Payment / Current Value of the Bond) * Time Period

A duration of 8.44 means that the price of the bond will fall by 8.44% when interest rates increase by 1%.  Because of this, bonds with a longer duration are more sensitive to interest rates.  For zero-coupon bonds, the duration is equal to the maturity date, which makes them more sensitive to interest rates.  Higher coupon bonds have a lower interest rate risk.  Duration will fall as interest rates rise.

### Bond Pricing

10 year semi-annual (payment) bond with a par value of $1,000 and a 3% coupon rate.

> Annual Coupon Payment = ($1,000 * .03) / 2 = $30/2

You pay $1,000 for the bond today, and the payment is the interest received.  You get the $1,000 back in 10 years.

If interest rates rise to 3.5%, then investors would only be willing to pay $958.42 for the bond.  If the interest rate dropped to 2.5%, then the price of the bond would be $1,043.76.

The **yield to maturity** is the interest rate an investor earns if the bond is held until maturity.

The **current yield** is the annual yield (cash flows) to an investor, relative to its current price.  An increase in interest rates leads to an increase in the current yield.

A decrease in bond term length is less sensitive to interest rate changes and vice versa.

### Federal Bonds

US Government bonds are considered free of default risk, and may have state and federal tax benefits (they're OK in a taxable account).  They're safe because the government makes money via taxation, and can print money as needed.  64% of all bonds held are US government bonds ($20.9 trillion in US Treasury bonds).

Types of US Treasuries:
* **Nominal Treasuries**: Fixed payments (not inflation adjusted)
* **Real Treasuries**: TIPS (Treasury Infaltion-Protected Securities) coupons and principal linked to CPI-U.
* **Floating Rate Notes**: 2-year bonds that pay quarterly interest payments.  They rise and fall based on the discount rates for 13-week U.S. Treasuries. They provide investors with a form of insurance against an unexpected rise in interest rates.
* **Savings Bonds**: 2 types: Series EE and Series I. Both are issued for 30 years. You can cash them in one year after purchase, but if you cash them in before 5 years, you lose the last three months of interest.  The Series I Bonds are the most attractive for funding less flexible goals (interest calcuated every 6 months, limited to $10,000 per person, protected from inflation).

**Government agency bonds** are issued by a government agency that is technically separate from the US Government.  They are not as safe as US Treaduries.

**Government sponsored entities** (GSEs) financing entities created by the US Government to fund loans to students, farmers, and homeowners.  FNMA (Fannie Mae) and GNMA (Ginnie Mae) loan money for mortgages.  Mortgages backed by GSEs are packaged into Mortgage Backed Securities (MBS), which have prepayment risk and where the principal is paid back over time (rather than at maturity).  GSEs are subject to state and city taxes (should be held in a tax sheltered account).

The primary driver of risk in Federal Bonds is **duration**.  Bonds consistently outperform Notes and Bills over the past 35 years due to the decline in interest rates since the 1980s.

Treasurydirect.com is where you buy securities directly.

### Municipal Bonds

Municipal Bonds are bonds issued from states and local governments (called Munis) that are exempt from Federal taxation.  They are a good fit for a taxable account and are best for high income individuals.

Types of Municipal Bonds:

* **General Obligation Bonds**: Funded by local taxation, they have a lower risk over other Munis.  Defaults are rare and investors have typically received much of their money back when they default.
* **Revenue Bonds**:  Funded by the revenue of a specific project.  If the revenue is lower than expected, the bond can default.  They have a higher yield because they have higher default risk.  A **private activity bond** is a municipal bond that is issued by a private corporation (in connection with a joint local government project) and carry the same risk as corporate bonds.

If the return on a muni bond is higher than the expected after-tax return on a taxable corporate or federal bond, it may make sense to invest in them.

The **tax equivalent yield** is the yield necessary for the taxable bond to be equivalent to a tax-exempt yield on a muni bond.

> Tax Equivalent Yield = tax exempt yield / (1 - marginal tax rate)

The tax equivalent yield of a muni bond with a 3% yield for an investor in the 35% tax bracket:

> .03 / (1 - .35) = .0462 or 4.62%

So, a 4.62% taxable corporate bond is equivalent to a 3% muni bond (assume risk in the same for comparision).

Individual bonds suffer from idiosyncratic risk.  Munis can be a hedge against tax increases, and are more attractive to higher income investors.  When states offer income tax excemption, that needs to be added to the tax-equivalent yield equation.

Mutual funds or ETF that hold munis diversify away part of the idiosyncratic risk, though some remains because they are still localized to the investor's state of residence.  Munis are most attractive to investors whose state provides tax exemptions.

The Tax Cuts and Jobs Act eliminated the tax-exemption of advance refunding municipal bonds, adding more idiosyncratic risk to munis.

### Corporate Bonds

Corporate bonds are a form of corporate debt and gives companies a tax deduction.  Corporate bonds are less restrictive than bank loans, though bank loans can be renegotiated in the company experiences financial troubles.  Corporate bond risk is typically lower that company stock risk.

**Credit risk** is the type of default risk that a company will not generate enough profits to cover repayments.  The lower the financial stability of a company, the higher the default risk and the higher bond yield.  The **yield spread** is the measure of the return of a corporate bond based on default risk.

> Yield Spread = Corporate Bond Yield - Treasury Bond Yield

The default risk of a corporate bond is expressed as a **bond rating**.  Higher credit ratings = lower risk, lower coupon rate, lower yield spread.  The highest rating is AAA, and only held by 2 companies (Microsofe and Johnson & Johnson).  BB+ and lower bonds are called junk bonds.

All corporate bonds carry an interest rate risk.  The longer the maturity, the higher the interest rate risk.

A **bond indenture** is the legal contract between the issuing firm and the bond holders.  It specifies all of the characteristics of the bond.  It is summarized in the prospectus filed with the SEC.  THe prospectus contains information about the maturity date, the coupon rate, coupon repayment durations, bond covenants/restrictions, the trustee bank, the bonds "callable" status, the issuing company, and it's sources of risk.

* **Callable bonds**: can be recalled if interest rates fall.
* **Zero-Coupon Bonds**: do not pay a coupon, but pay a higher maturity price.
* **Floating-Rate Bonds**: changes with inflation or a specific short-term rate.
* **Convertable Bonds**: bondholders can convert bonds to shares at a later date.
* **Income Bonds**: only pays coupons if the company income doesn't drop below a level

Corporate bonds are ideal to lessen the volatility of stocks in retirement portfolios (especially as a client approaches retirement age).  They are best in tax-sheltered accounts.  Risky bonds act like stocks but are less diversified.

The yield spread of high-yield bonds often spikes in recessions.

### Bond Credit Risk Premium

The **credit risk premium** is the premium associated with accepting more credit risk.  It is typically positive, but the premium size has varied.

Corporate bonds have not outperformed similar Treasury bonds despite having a higher yield.  

Future returns on corporate bonds are higher when spreads are greater and lower when spreads are smaller.   There is a significant relationship between spreads and subsequent returns.  The decision to choose corporate bonds when spreads are narrow is a risky bet with a small expected payout and high volatility.  Wider spreads make corporate bonds more attractive.  

Negative sentiment in financial markets leads to investors requiring greater reward for accepting the risk of corporate bonds.  High-yield, lower-quaility corporate bonds underperform over time. Because of this, advisors shouldn't use corporate bond yields to estimate expected future returns.

### Bond Investments

Investors who purchase individual bonds have more control over the timing of the cash flows.  Individual bonds are subject to reinvestment risk as well as interest rate risk.  It's difficulat and expensive to have a diversified bond portfolio.  Individual bonds are less liquid and have higher transaction costs than bond funds.

Bond funds are more diversified than individual bonds.  Bond funds don't have a specific maturity date, so repayments can vary.  Expense ratios vary greatly across bond funds.  **Defined Maturity Funds (DMFs)** have a known payout at maturity and are useful for fixed future expenses. 

* **Ultra short-term bonds** have a maturity date less than 1 year.  aka Cash Funds since they aren't affected by interest rates.
* **Short-term bonds** have a maturity date less than 4 years.
* **Intermediate-term bonds** have a maturity date between 4 - 10 years.
* **Long-term bonds** have a maturity date greater than 10 years.
* **Aggregate bond indexes** hold bonds of varying maturities, though most similar to intermediate-term bonds.

Maturity diversification reduce interest rate risk.
Credit Rating diversification reduces default risk.
Geographical diversification reduces both interest rate risk and default risk.
ETF offer the same benefits as bond funds but with lower management fees and transaction costs, but don't have tax benefits.

## Equity Instruments

### Equity Financing

Private company founders may chooose to diversify their portfolio or raise capital for growth by going public.  Public companies separate investors/owners from management.  Consortiums of private investors are called **venture capitalists**.  In order to go public, private companies work with banks to sell shares of stock with an IPO in the **primary market** (institutional investors).  Individual investors may be initial shares in a **secondary market exchange** (e.g. NYSE), which often increases the price of the stock.  In the secondary market, IPO typically underperform other stocks.  The big winners are the institutional investors.  Companies with a higher operating risk typically have less debt and more equity financing.

Stock ownership limits an investor's liability to just their investment amount.

* **Firm Governance**: the oversight that the board of directors provides over the CEO.
* **Voting Rights**: shareholders vote for board members and for corporate policy.  Different types of stock have different voting rights.
* **Shareholder Rights**: [no info given] shareholders have rights.
* **Mergers and Acquisitis**: underperforming companies may be sold to outside investors.  aka **M&A**.
* **Ex-Dividend Date**: the latest date a dividend can be paid to a shareholder.  Stocks fall in price by the amount of dividends they pay.
* **Dividend Policy**: policy regarding whether to pay a dividend and how much to pay.
* **Share Repurchase**: if management believes their shares are undervalued OR if they don't have capital investments to make, they can repurchase their stocks.

### Microstructure

The main difference b/w primary and secondary markets is that traders set the price in the secondary market.

Primary Market:

* **Money to Invest**: companies raise money to invest in projects through the primary market (e.g IPO)
* **Financial Intermediary**: an investment bank acts as a financial intermediary between the company and the institutional investors in an effort to evaluate the value of the shares and the viability of selling them (via a road show).
* **Leaving Money on the Table**: from the perspective of the company, the rise in the stock price in the secondary market that leads to a devaluing of the company's stock share value.  Investment banks take a 7% cut of all primary market sales.
  
A majority of transactions take place in the secondary market (NYSE, NASDAQ).  A **specialist/market-maker** brings together buyers and sells and makes profits on the differece between the bid price and the asking price (the **bid-ask spread**).  The S&P 500 has a low bid-ask spread. Less-liquid assets have higher bid-ask spreads.  Because of electronic trading, the spread has decreased from $.12 per share in the 1990s to about $.03 per share today.  This fee reduction makes rebalancing less costly.

The **market depth** is the number of buy and sell orders issues during the day.  Sellers and buyers can issue a **market order** (current price of the asset) or a **price contingent offer** (specify a target price).  A **stop loss order** (set floor stock price to automatically sell at) is used to limit potential losses.  Stop loss orders are blamed for the flash crash of 2010 and other market anomolies.

**Dark pools** are private markets for large insitutional investors who can transaction privately.  Companies listed in the secondary market must file with the SEC and provide all financial information to investors.  The bond market is less liquid that stocks b/c of the difficulty of matching buyers and selles due to the variability of bond attributes (creating a larger bid-ask spread).

In 1975, brokerage commissions were deregulated (called **Mayday**), resulting in reduced transaction costs via the emergence of discount brokerage houses.  Since commission costs are lower with larger trades, transaction costs can be reduced bigger, more infrequent trades.

### Corporate Payout

Sometimes offering a dividend can signal that a company is becoming a mature, lower-growth company, which can have downward pressure on the stock price.  A company's profits are referred to as **earnings**.  Earnings are either reinvested or paid out as dividends.  The **dividend payout ratio** is the dividends divided by the earnings.

A company has $2 million in profits, has 4 million shares, and pays $.25 per share:

> Dividend Payout Ratio = (4,000,000 X .25)/2,000,000 = 0.5  (50% paid in dividends)

Volatile earnings make companies less likely to pay or increase divdends.  Established dividends are typically maintained (aka **sticky**) b/c a dividend cut can be a signal to company health, resulting in downward pressure on the stock price.

An alternative to paying dividends is stock repurchasing, which increase the company's stock price and offers tax advantages over dividends to share holders (dividends are taxed at the marginal tax rate, while equity value increases are taxed as capital gains).  Shareholder may also prefer capital gains b/c they control the timing of the taxable events.

The **dividend yield** is the annual dividend paid divided by the price of the stock (aka **dividend yield of a portfolio**).  Stocks with a high dividend yield are called **income stocks**, which are typically older, more established companies that generate consistent profits.  Dividend yield are not guaranteed.

### Dividend Stocks

The average compound return on stocks have been about 10%, and 6% of that has been from dividends.  Value stocks typically pay higher dividends than growth stocks (as well as higher returns).  Dividend yields have decreased over the past 25 years.  Divident stocks haven't performed better than non-dividend paying stocks, and may be detrimental due to their tax treatment.

Preferred stocks often pay perpetual dividends, but they can be "called" in a low interest environment.  Preferred stock dividents are considered **qualified** dividends and get taxed like long-term capital gains, which makes the good for taxable accounts.  Preferred stocks have the same Sharpe ratio as high-yield bonds or large-cap stocks, but is less risky and thus have lower returns.

A **dividend clientele** is a group of investors that prefer dividends.

The upsides of dividends:

* Companies are not tempted to invest in less efficient investments
* 50% of the return on stocks are from dividends
* They provide income to investors to fund spending

The **dividend irrelevance theorem** states that the stock price is reduced by the amount of the dividend, making them irrelevant.

**Narrow Framing** (or just Framing) is viewing the income characteristics of an investment in isolation from the overall portfolio.  Dividend investors sometimes narrowly frame dividend stocks, often ignoring the systematic risk and total returns.

Investing in dividends can also have idiosyncratic risks is the stocks are purchased individually.

### Firm Valuation

A few stocks perform really well while most stocks underperform, making a strong case for diversification.

The **dividend discount model** is the discounting of the net present value of dividends in stock valuations.  You can use the stock's beta to calculate the dividend discount rate using the CAPM.

The **Gordon Growth Model** estimates the value of a stock using the expected dividend, the discount rate, and the expected rate of dividend growth.

> Value of a Stock = (next annual divident payment) / (required return from CAPM - constant growth rate of the dividend)

Ford pays $.60 per share per year in dividends, has a beta of 1.36, the current risk-free rate is 2%, the market-risk premium is 4%, and investors expect **no growth** in future dividends.

> Required Return = .02 + 1.36 * .04 = .0744
> Value of Ford = .6 / (.0744 - 0) = $8.06

If the current price of Ford is $11.12, which could mean the risk premium is actually lower than 4% or the market is expecting dividend growth.  Many of the inputs to the Gordon Growth Model are unknown.

Because of idiosyncratic risk, the discount rate should be increased for individual stocks.

### Firm Characteristics

#### Grouping Companies/Stocks

Stocks can be classified into different **sectors**, which are a part of the economy that shares a related product or service.  11 main sectors: Basic Materials, Communication Services, Consumer Cyclical, Consumer Defensive, Energy, Financial Services, Healthcare, Industrials, Real Estate, Technology, and Utilities.

**Hot Sectors** are sectors that have recently performed well.  The tend to become overvalued and underperform as they become less hot.  Clients tend to want to invest in hot sectors during their overvaluation period, but that usually results in underperformance and less diversification.

Sectors should be invested in to balance a portfolio, but not to generate excess performance.

**Super Sectors** are aggregations of sectors to capture broader industry exposure.  Super Sectors:
* **Defense**: Consumer Defensive, Healthcare, and Utilities.  Defensive is defined as products whose demand exists in both recessions and expansions.  Examples: Food, Tobacco, Personal Care Products.
* **Cyclical**: Basic Materials, Consumer Cyclical, Financial Services, and Real Estate.  They are sensitive to business cycle peaks and troughs, with greater demands in expansions and declines in recessions.  They have a larger beta than Defense Super Sectors. Examples: Housing Starts (new homes starting to construct).
* **Sensitive**:  Communication Services, Energy, Industrials, and Technology.  Has a modest correlation with business cycles.  Examples: Gasoline.

Companies can grouped into industries and sub-industries as well, which are more specific than sectors.

Weights are used to to show the percentage of the sector within the US market capitalization.  The largest sectors are been Technology (19.7%), Financial Services (15.3%), and Healthcare (13.3%), while the smallest sectors are Real Estate (2.9%), Basic Materials (3.0%), and Utilities (3.2%).

Market valuations of firms vary within an industry.  **Tobin's Q** (or **Q Ratio**) is the total market value of a company divided by the total value of a company's balance sheet (book value), or the amount an investor would be willing to pay for $1 of the copanies hard assets.  A high Q Value company is a growth company.

#### Three Factor Regression Coefficients

The Three Factor Regression Coefficients tells us the historical beta of the sector and the extent to which it loads to size and value factors. The 3 factors are beta, growth, and value.

Value stocks are more sensitive to a recession.

#### The Sector Rotation Strategy

The **Sector Rotation Strategy** is investing in different sectors based on the state of the economy.  Cycles begin with a rebound from a recession with high stock returns (Cyclical and Super Senstive Super Sectors do well here).  In the middle of the cycle, growth is still positive but not a strong as in the beginning of the cycle.  At the end of a cycle when the economy over heats, growth rates decline and the economy contracts (lower stock returns, Defense Super Cycle does well here).  The inconsistency of performance among stock stock sectors during receissions makes it hard to accurately pick sectors to invest in.  Additionally, it's hard to know when a recession is starting.

**Valuation-Baed Portfolio Allocation** strategy identifies overvalued and undervalued companies, selling overvalued companies and buying undervalued ones.  It's difficult to really tell if a company is over or under valued.  These strategies don't typically outperform the market portfolio.

## Diversified Securities

### Market Indices

#### Stock Indices

In 1884, Charles Dow compiled a list of 14 transportation companies and averaged their stock prices, creating the first stock market index.  In 1896, Charles Dow and Edward Jones create the Dow Industrial Average, a broad index of large cap companies. Indexes are use to gauge/benchmark the return of a stock market or stock market segment, and is a useful proxy for market risk and return.  The DOW is **price-weighted** (stock prices are added up and divided by number of stocks in the index), so higher priced stocks (UnitedHealth Group) carry more weight than lower priced ones (Intel).

Some passive mutual funds and ETFs often try to mimic indicies, which diversify away idiosyncratic risk and only take on systematic risk of the funds.

The S&P 500 tracks the top 500 **value-weighted** companies (by cap weght: num of shares X share price) and is used to benchmark asset manager's performance.  Some lower cap sized companies are included to keep the index spread across industries.  A company's stock price tends to jump when they are added to this index.

A third type of index is the **equal weight index** (e.g. Russell 1000 Equal Weight Index and the NASDAQ 100 Equal Weighted Index), where each stock is weighted equally and doens't care about price or market cap.  A 10% rise in one company and a 10% fall in one company results in zero change.

The **NASDAQ** is a value-weighted, composite index of stocks sold on the NASDAQ exchange.  Many of these stocks are in the tech sector (Apple, Google, Microsoft).

The **Russell 1000** is a value-weighted index of the 1000 largest US companies.  The performance is similar to the S&P 500.  The **Russell 3000** is similar, but looks at the top 3000 US companies, which is very similar to the Market Portfolio.  The bottom 2000 of the Russell 3000 is called the **Russell 2000**, which monitors the performance of small cap stocks.

The **Wilshire 5000** covers every US traded stock.  The **Nikkei 225** is a price-weighted index of Japanese stocks.  The **DAX** is the German equivalent of the Nikkei.  The **MSCI EAFE** is a cap-weighted index of 21 companies in Europe, Australasia, and the Far East.

#### Bond Indices

Since bonds aren't typically sold on an exchange, they can be less liquid than stocks.  A company's cap-weighted index is different from it's weight on a stock index.  Bonds create turnover when they mature, resulting in purchased of different bonds that change the mix of the index.

Bond indicies vary greatly.  The bond index space is dominated by the **Bloomberg Barclays Indices Group**, making up 68% of fixed income bond mutual funds.  

The **Bloomberg Barclays Aggregate Bond Index** is the second most popular primary prospectus benchmark for equity funds, consisting of over 10,000 bonds.  To qualify, the bond must:
1. In US currency
1. Investment grade or higher
1. Have a fixed-rate coupon
1. Meet various size, maturity and market requirements

The **iShares Core U.S. Aggregate Bond ETF (AGG)** is the most popular bond fund that tracks the Bloomberg Barclays Aggregate Bond Index.  The duration is 6.27 years and a weighted average maturity of 8.61 years, with an expense ration of 3 basis points.

The Bloomberg Barclays U.S. Aggregate Bond Index is a high-quality, intermediate-term bond index that is a benchmark for the entire fixed income portion (or intermediate-term bond fund) of a portfolio.

#### Performance Bemchmarks

**Benchmarking** is the process used to judge the value of an investment by comparing it with an investment that is similar in risk and investment factors.  The DOW and S&P 500 are good equity benchmarks, but they don't cover the entire portfolio.  Benchmarks should be chosen before the benchmark period to avoid cherry picking comparisons, leading to inaccurate results.  Because no single benchmark covers an entire portfolio, benchmarks for individual holdings are used.  Since indexes don't include fees, they need to be fee-adjusted prior to comparison.

Benchmarking should occur over long periods (3, 5, or 10 year periods).

Different types of benchmarks:

* **Objective Driven**: aka goal-based matches the return with the required return of the goal.  The problem with this is that the return is based on the random performance of the market, which doen't give signal that the investment was efficient.  This benchmark is mostly used for determing if a client's portfolio is on track.  Objective-driven benchmarking is a good way to identify whether markets are performing as expected when an investment plan is first created.
* **Granular**: matches each component of the portfolio with an appropriate benchmark (e.g. small cap, large cap, ...etc.).  While this benchmarks performance, it doesn't provide insights into efficiency.
* **Broad**: matches general stock and bond allocations, but doesn't match the risk. Beneficial for measuring returns.
* **Strategic**: slightly more refined than a broad benchmark, but not as much as a granular benchmark.  They don't include factor tilts, which gives an asset manager to identify the factors to beat the benchmark.

|                    | Objective Driven | Granular | Broad | Strategic |
| ------------------ | ---------------- | -------- | ----- | --------- |
| **Broad**          | Yes              | No       | Yes   | Yes       |
| **Neutral**        | Yes              | No       | Yes   | Yes       |
| **Investible**     | No               | Yes      | Yes   | Yes       |
| **Representative** | No               | Yes      | ?     | Yes       |

Mutual funds look at small vs large cap, and value vs growth.

### Mutual Funds and ETFs

A **mutual fund** is similar to an insurance product in that they allow investors to pool assets together. A mutual fund is created by an **investment company**, which aggregates investor funds to buy a portfolio, then issues shares in the portfolio (mutual fund) to investors.  Mutual funds are attractive for retirement accounts because investors can buy fractional shares.  Active investment fund managers prefer a mutal fund structure becasue holdings don't need to be disclosed on a daily basis.

A **mutual fund family** is the parent organization of multiple mutual funds that shares marketing and management resources.

Most mutual funds are **open-ended investment companies**, where they aren't fixed on the number of shares they can issue.  In cntrast, there are also **closed-ended investment companies**, but they are relatively uncommon.

Mutual funds are sold on the primary market, and are redeemed directly with the mutual fund (funds hold cash to easily liquidate).  **Redemption fees** are sometimes levied from mutal funds to discourage short-term investing.  The purchase price and the redemption price are based on the net asset value (NAV).

The **Net Asset Value** measures the value of a mutual fund and is calculating by:

> NAV = (assets - liabilities) / number of outstanding shares

Values are based on the market close value.  If trades are executed after the end of the day, they are values at the end of the next trading day. 

The **Investmet Objective** of a mutual fund varies by fund and is found in the fund's perspectus (long-form and summary). The **Principal Investment Strategies** section provides details about what the fund hopes to accomplish.  Actively managed mutual funds will include an **investment style**, where the fund can be benchmarked against the **style benchmark**. 

#### Load Charges and 12b-1 Fees

The **load** of a mutual fund represens the fund's commissions (fees).  Mutual funds can be load (broker sold) or no-load (self-directed) funds.

A fund with a load charge of 5% and a net asset value of $50:

> Price per share = NAV / (1 - load charge)= $50/(1 - 0.05) = $52.63 per share

> Total load per share = 52.63 - $50 = $2.63 

**12b-1** fees were created by the SEC in 1980 and are on-going fees based on the percentage of assets.  Under FINRA rules, 12b-1 fees for marketing and distribution expenses cannot exceel 0.75% (75 basis points) of a fund's net assets per annum.  12b-1 fees above 0.25% are classasified as load funds.

#### Expense Ratios and Shares

The **Expense Ratio** aggregates fees and expenses related with managing a fund.  These fees must be subtracting from gross returns to calculate the net investor return. A fund with an annual gross return of 11% and an expense ratio of 1%, has a net investor return of 10%.  12b-1 fees are included in the expense ratio.  Expense ratios are the strongest predictor of mutual fund performance.

A **basis point** is one-onehundredth of a percent.  1% expense ratio = 100 basis points.

To calculate the number of shares one can purchase for $975 using the $50 price and 5% load fee:

> Number of Shares = Investment Amount / Gross Price per Share = $975/52.63 = 18.5256 shares

The number of decimal places differs by funds, but they have at least 2 decimal places.

#### Closed-End Funds

**Closed-End Funds** are collections of securities that are bundled in a portfolio and sold to investors.  The share price is the NAV at the time of the sale.  Unlike open-end funds, closed-end shares cannot be sold back to the investment company, but are instead traded on the secondary market.  Closed-end funds typically have greater fees than a similar ETF.  The emergence and popularity of ETFs have made closed-end funds less popular.

#### ETFs

In 1993, the American Stock Exchange created the **S&P 500 Depository Receipt (SPDR)** (aka spider) that had the diversification of a mutual fund but was traded on the secondary market like stocks.  The SRDR was the first ETF.

An **Exchange Traded Fund (ETF)** is an investment company that pools investor money to create a portfolio, and investors hold shares on that portfolio (much like mutual funds).  Before 2008, all ETFs were index funds, but since then a very small percentage (1%) are actively traded.

**Authorized Participants** are the organizations that create the ETFs.  The exchanges are treated as in-kind and are not subject to taxes.  ETFs have lower transaction fees because the trade funds instad of buying/selling them.

A **creation unit** is equivalent to a fixed number of shares of the ETF, which drives the values of the shares.  The most common number for creation units is 50,000 shares.  Once an investor has 50,000 shares, they can trade their shares for the underlying portfolio (stocks and bonds) and vice versa.

ETFs are more liquid than mutual funds.  It's less expensive to buy or sell mutual fund shares, but the difference is minimal.  ETFs are more tax efficient in taxable accounts because they defer capital gains untils the ETFs are sold while mutual funds distribute capital gains once a year.  ETFs are more transparent b/c they have to discolse their holdings on a daily basis whild mutual funds disclose quarterly with up to a 30 day lag.

Mutual funds can be aquired by another company, trading shares in the new fund for the old one.  ETFs liquidate by distributing the proceeds to investors.

Investors looking for the least expensive way to invest in a passive portfolio should consider the added liquidity of the ETF as the primary advantage over a low-cost mutual fund.  The espense ratio (both) and bid-ask spread (ETFs) is the most import thing to consider when comparing ETFs and similar mutual funds.

Bond ETFs (not including treasuries) and small market ETFs should be avoided due to liquidity issues in a crissis.

### Fund Features

#### Fund Taxation

Mutual funds are treated as pass through entities.  2 ways to be taxed:
1. Personal: when the investor sells shares that gained value
1. Fund: if the fund manager creates taxable events that realize gains

The **basis** is the amount paid for the shares. If the investor sells the shares above the basis, taxes must be paid.  The **average cost basis method** uses the average price paid for all the shares to calculate the basis.  Shares held for a year or less are taxed at ordinary income tax rates, which longer than a year are taxed at long term capital gains rates.  Capital gains can be offset by capital losses.  **Tax-loss harvesting** involves selling shares at a loss to offset capital gains.  Capital losses are limited to $3,000 per year, though the balance can be carried forward.

The **per-share distribution amount** is the gains per-share that the investor must claim when a fund liquidates assets.  When distributions are made, the value of the fund declines by the same amount.  New share holders have to pay the taxes even if they bought the shared after the distributions occurred. **Tax overhang** is the unrealized capital gains in a fund.  Only net capital gains (vs losses) are distributed to shareholders.  Actively managed funds are best suited for tax-sheltered accounts.

Distributions in a 401(k) are deffered until withdrawn.  In Roth, they are tax-free.

#### Capital Gains for Estates

Within a taxable brokerage account, mututal funds beneficiarias receive a step-up in basis (they don't pay capital gains).  The new basis is the price of the shares at the time of transfer.  Because of this, older investors may not want to liquidate highly appreciated funds if they intend to pass the funds to their heirs. Investors can also avoid capital gains by donating the shares to charity (they can also get a tax deduction). 

#### Mutual Fund Shares

The most common mutual fund share classes are Class A, B, C, D, and Class I (Institutional Class).  The **load** is commission recieved by brokers.  The **12b-1 fee** is the marketing or distribution fee.

* **A-Shares**: aka **front-load funds**, initial fees are charged when the shares are purchased. They are best suited for medium to long-term time horizons since the fee is paid up front.  There are **breakpoints** where fees are reduced based on the amount invested.  Some funds will apply the breakpoints once enough shares are purchased in the future.
* **B-Shares**: aka **back-load funds** and aka **contingent deferred sales charge or CDSC**, fees are paid when funds are withdrawn.  The CDSC decreases over time and disappears when B-Shares are converted to A-Shares in 5-6 years.  B-Shares don't have breakpoints.
* **C-Shares**: don't have back or front-load fees, but charge fees at other times (annually, usually 1%).  C-Shares are most suitable for short-term investors.
* **D-Shares** and **F-Shares**: no-load funds, but charge fees at other times.
* **I-Shares**: institutional share classes that are used in retirement and group investment portfolios that have a high investment amount (typically $1 million).  They are no-load with low expense ratios.  They are appropriate for any time horizon.  Similar to **R-Shares**, which are exclusively held in retirement accounts.

**Mutual Fund Families** have low or no sales fees.  An **exchange privilege** is the privilege of a mutual fund shareholder to exchange their investment in a fund for another within the same fund family and share class at no cost.  This creates a taxable event.

**Share conversions** are the converting to a different fund class within the same fund.  These conversions can happen automatically.  This is common with B-Shares, that convert to A-Shares after a period of time.  Shareholders can manually convert if they qualify for a better class via fund growth and additional investments (e.g Vanguard Admiral Class conversion, no-load). This conversion does **NOT** create a taxable event.

FINRA develeoped the **Fund Analyzer** in 2008 to assist in comparing fund expenses and fees.  They also developed the **Breakpoints Checklist and Worksheet Tools**.

High initial sales loads reduce the returns of investors who frequently trade.

#### Unit Investment Trusts (UIT)

Investment companies can be split into 4 categories: open-end funds (aka mutual funds),  unit investment trusts (UITs),  exchange-traded funds (ETFs), and closed-end funds.

The main difference between UITs and other investment companies is that they have a termination date.  After the termination date, the funds are paid to the investors (causing a taxable event).  They also have the option to terminate early.  For bonds, the termination date is the maturity date of the bond. For stocks, they can be liquidated at any time.  Sometimes the distributions can be in-kind or rolled into another UIT (defers taxation).

Advantages:
* No trading within the portfolio
* No trading expenses
* Little or no management expenses

UITs are best suited for assets that are illiquid, which typicall have higher returns.

UITs issue **units** rather than shares.  Portfolios are typically fixed for the lift of the trust (from issue date to termination date), and are typically much less diversified (fewer than 20 positions).  UITs are unmanaged, so have no board of directors.

UIT similarities to other investment companies:
* NAV tracking
* No secondary trading market 
* Includes a transacion fee
* Low annual supervision fees
* Minimum initial investment
* No capital gains are distributed

#### Analyzing Mutual Funds

* Investments Process: the strategy for investments (e.g. small cap, ...etc)
* Fund Performance: assess how well it's doing
* Team Assesment: well resourced and experience leves
* Parent Company or Asset Management Firm: do they have a good history
* Price Tag: analyze the price of the investment

Portfolio Analysis:
* Number of securities
* Frequency of trades (turnover ratio): low turnover can be more volatile, high turnover is expensive and creates taxable events.  Turnover can affect the expense ratio.
* Expense ratio
* Portfolio Manager's experience level
* Level that the Portfolio Manager is invested in the fund (higher level is a good signal): they are required to disclose this

### Global Investing

#### The Role of the U.S. Market and International Allocation

**Home bias** is over-allocating in one's home country.  Adding not-perfectly-correlated stocks and bonds from around the globe adds diversification and reduces risk (higher risk-adjusted performance).  The diversification benefit declines over time as US and internations stocks are highly correltated over time.

The US had 60% of the global equity market in 1975, but that has dropped to 45% in 2018 (35% in bonds in 2018).

Financial theory says that investors should hold the **global market portfolio**, though this may not be the case since international stocks may have higher costs, or less regulated (e.g. insider trading).

Since US companies can operate abroad, the geographic revenue sources are a better indicator of "international" than the home origin of the company (called **domicile**).

The **Exchange Rate Risk** (aka currency risk) is the added risk of exchange rate fluctuations when investing in foreign currency.  This risk can be reduced by holding assets in multiple currencies.

### Emerging Market Funds

**Emerging markets** are developing countries or regions that have less economic output than develped countries, but more than **frontier markets**.

The performance of emerging market funds have outpaced the performance of developed country funds recently.  Emerging markets have more risk, but that can be reduced by exposure to many different emerging countries.  Emerging markets represent 1/4 of global market capitalization. 

It can be difficult and expensive to hedge against emerging markets.  Types of risks associated with emerging markets:
* Currency Risk: highest in developing countries
* Information Risk: weak account proceedures and poor checks and balances
* Liquidity Risk: harder to sell shares
* Political Risk: unstable governments, wars, unstable policies

Emerging markets had the highest average returns (11% per year), but also the highest risk (annual standard deviation of 22%).  The risk adjusted return in emerging markets is similar to that of other asset classes.  Emerging markets don't perfectly correlate with other risky markets.

Characteristics to consider:
* Geographic concentration: larger weights to larger developing countries
* Issuer concentration: big companies in smaller countries can dominate the index
* Industry concentration: public companies in emerging markets can have similar industries (low diversification)
* Investment fees: emerging markets have higher expense ratios

80% of assets in emerging market mutual funds passive.  Since emerging markets aren't as efficient as developed ones, active management stratigies might be beneficial.

### Life-Cycle Funds

In 2007, the US Department of Labor allowed retirement plans to use **life-cycle funds** as a qualified default investment.  Life-cycle funds account for the largest category in retirement accounts.

AKA Target-Date Funds, Life-Cycle Funds base portfolio allocation on life-cycle theory.  Since human capital decreases as investors approach retirement, these funds automatically adjust to safer assets over time.

The **glide path** is the decline in equity allocation in the fund over time. The glide path will be set a specific stock allocation at retirement. Equity allocations for life-cycle funds ranged from 8% to 58%.

Life-cycle funds don't take into account the risk-level of individual human capital (which can vary greatly).

While life-cycle funds are simple, advisors can create a more custom portfolio and glide path that's more aligned with the investor's goals and risk profile.  Knobs that advisors can pull:
* Custom Asset Allocation: tailor performance and tax efficiency to the investor's unique circumstances
* Bond and Equity Exposure: reduce expense ratios and improve diversification
* Adjusting Glide Paths

Many life-cycle funds only include funds from their holdings, though they perform just as well as life-cycle funds that hold other firms holdings.

### REITs

REITs are a unit investment trust that directly focus on real estate.  REITs allow investors to have exposure to diversified real estate holdings and get some of the advantages of owning real estate without direct ownership.

At least 75% of REITs have their assets must be real estate, cash, or government securities (cash and government securities are held short-term). 75% of income must come from rents, mortgage interest, or other real estate investments. 90% of a REIT’s taxable income must be distributed as annual shareholder dividends. REITs can be publicly traded or non-listed public or private.

2 categories of REITs:
* **Equity REITs**: commercial or residential properties that generate income from rent and cover various sectors.
* **Mortgate REITs**: commercial or residential properties that generate income from interest from mortgage and mortgage securities

While investors can invest directly in REITs, they can also purchase mutual funts or ETFs.  These offer diversification with a low minimum entry cost, and are more liquid than directly invested REITs.  REITs have a lower beta than the overall market and a slight correlation with equities, which can increase risk-adjusted performance.

Disadvantages of REITs:
* 70% of the payout is a dividend: not tax efficient and should't be in a taxable account
* Volatile Sensitivies to Market Risk: sensitive to market and interest rate risk
* Similar Risks to Equities and Bonds: 0.74 correlation with equities and 0.49 correlation with bonds, they fall during a recession, higher interest rates lead to lower property values and higher expenses

### Responsible Investing

**The  Warm Glow Effect**: Investing in funds aligned with an investor's values increases the amount of satisfaction received from the investment.  Maximizing satisfaction more important than maximizing wealth, so it's the wealth manager's role to determin this.  Investors in socially responsible companies are more patient when the investment looses money and is more loyal to the advisor who helps their client increase their sense of purpose.

Impact investing (aka sustainable investments) started in the 1700s by groups like the Religious Society of Friends (Quakers) and John Wesley.  These excluded mis-aligned investments, which is known as **socially responsible investing (SRI)**.

**ESGs (environmental, social, and governance)** is a form of responsible investing focused on the environment (global warming, pollution, deforestation), social factors (health, working conditions, safety), and governance policies (executive pay, lobbying, board diversity and structure).  ESGs don't solely take an exclusionary approach as they seek out companies with aligned attributes.


Funds that pay attention to socially responsible corporate policies do **not** underperform over time.  ESGs attributes (like govenance, which has 8.5% higher returns) can improve performance over time. Since 1983, the socially responsible indicies have performed nearly identically to the market as a whole (no loss in portfolio efficiency).  4 out of 5 S&P 500 firms issue sustainability reports relating the the firm's sustainable practices.

Some ESGs exclusionary policy may reduce diversification and some have higher fees.

Since ESGs have compariable gains to the market portfolio, they can be offered to clients who highly value maximum financial return.  SRIs balance financial returns and social outcomes.  Impact investing focuses on social outcomes followed by financial returns. Philantropy maximizes social outcomes.

Responsible investments can exist in passivly managed indexed funds with low expense ratios.  Some funds may take an **activist role** and actively screen their portfolio for alignment.

**Sustainalytics** provides analytics about companies relating to their sustainability practices. 

## Other Financial Instruments

### Real Estate Investing

Cons of direct real estate investing:
* Illiquid: not quick to sell, pay fees to sell
* Hassle: collecting rent, evicting
* Liability: tennants can sue, esp since lenders require the title in an indivudual's name, LLC is an option

**Commercial real estate**: office buildings, industrial warehouses, shopping malls, golf courses, hotels, ..etc.
**Residential real estate**: apartment buildings, multifamily buildings, single-family homes, and retirement living facilities.

For commercial real estate, **vacancy rates** are the leading indicator of the overall market.  For residental real estate, vacancy rates are a lagging indicator. Historical returns on private real estate lie somewhere between stocks and bonds.

The pandemic affected commercial real estate more than residental because people were spending more time at home and mortgage rates were low.

**Information risk in real estate**: investors with more experience in tax rules and selling real estate will get higher returns than less experienced investors.  Because of this risk, less experienced real estate investors are better off with a real estate fund or REIT.

The IRS treats real estate as a **passive activity** unless you are a real estate professional.  If expenses are greater than rent collect, then net income results in a **net loss**.  Some of this loss may be tax deductible.  Investors should periodically evaluate the benefit of a real estate investment and have a sound **exit strategy** for when to sell it.

Investors who sell real estate can defer capital gains tax by using a 1031 exchange (since 2018, the like-kind rule only applies to businesses/investments/trade).  Investors have 45 days to swap properties, and the replaced property must be settled within 180 days after the exchange.  UPREIT (Umbrella Partnership REIT).  To avoid tax, an investor can trade their propery with a UPREIT and receive units in it (IRS Section 721).  The investor can convert these units to cash or REIT shares.

Qualified Opportunity Zones are an economic development tool that allows people to invest in distressed areas in the United States.  Their purpose is to spur economic growth and job creation in low-income communities while providing tax benefits to investors.  They are relatively new, so we don't know a lot about their performance, it may not be worth it solely for the purpuse of a tax deduction (tax tail wagging the dog).

### Annuities

**Income annuities** are insurance products that trade a lump sum payment for a guaranteed lifetime payment.  Annuities can be used to manage retirement risk.  Insurance companies utilize pooling and mortality credits, and uses mortality tables to predict how long members will live and how much they'll have to pay out. Pooling reduces costs to just slightly more than funding a bond ladder.

Bond problems that annuities solve:
* The probability of running out of money
* Wasting money by overshooting bond maturity dates

Income annuities are like a coupon bond with payments for an uncertain length of time, and does not repay the principal value at death.  Income annuities mitigate **longevity risk**.  Investors who die early subsidize the payments to those who live longer. Income annuities also mitigiate **sequenc risk**. Income annuities are a form of insurance against outliving one’s assets.

One could make the case that annuities have more downside protection over bonds, and the annuities should replace bonds in a retirement portfolio.  Income annuities issue subsidies, or mortality credits, as a third way to pay annuiants (in addition to principal and interest).  Income annuities can also be better than **self-annuitizing** (via a bond ladder), as well as stocks (less risk).

Annuities are really 2 things:
* Tax deferral during accumulation: tax deferral benefits, can liquidate anytime before annuitizing or convert to another type of annuity
* Guaranteed lifetime income: once the contract is annuitized, the annuity pays for life

**Deferred annuities** are just investment vehicles early on, but then can be annuitized later. Unlike 401(k)s, deferred annuities have no income limits.  Disadvantage to a deferred annuities are access restrictions that limit withdrawl ammounts (e.g. surrender fee/charge) and the tax penalties if money is withdrawn before 59 1/2.  The general withdraw rule is to compare the income the investor can receive from annuitizing the deferred annuity to the income that could be gained by taking the money out of the contract and purchasing the same income annuity from another insurance company.  The tax benefit is less than of a traditional tax-deferred account because the initial investment is made with taxable dollars.  Withdrawing money without annuitizing results in a less-favorable tax treatment.

A **Single-Premium Deferred Annuity (SPDA)** guarantees interest rates for a period of time. Longer contracts typically provide higher interest rates.  SPDAs can offer bonus intersest for the first few years of a contract and can incur surrender fees if liquidated early.  This surrender charge is called a market value adjustment or MVA and it varies depending on how interest rates change.

A **Multi-Year Guaranteed Annuity (MYGA)** is a single-premium deferred annuity that is similar to a CD, but is not FDIC insured (protected by state insurance guarantee funds) that provides a guaranteed interest rate for a fixed period of time (typically 3 - 7 years).  Gains are taxed as ordinary income upon liquidation, though a 1035 exchange can be used to defer the taxable event.  They have penalties if money is withdrawn before 59 1/2.

A **Fixed indexed annuity (FIA)** is a type of deferred annuity used to accumulate assets for retirement, where the insurance company guarantees **no loss in principal** (not incuding subtractions from fees and dividends).  Annuity owners pick an index for the annuity to follow (e.g. S&P).  Penalties and taxes could be incurred it money is pulled out in the first few years or before 59 1/2 (unless a lifetime annuity is purchased with the proceeds).  FIAs to not take dividends into account, and they reduce the index by the amout of the dividend.  FIAs as basically a safe asset with potential tax advantages in a portfolio.  It may make sense to place investments into a FIA rather than in bonds in a taxable account to ovoid interest rate risk and possible higher returns.

FIA cons:
* Limitations on credited interest through caps, spreads, and participation rates (have guaranteed minimums)
  * Cap: limited to the amount of the increase in the index
  * Spread: only applies to annual point-to-point policies and is subtracted from the computed value
  * Participation rates: a percentage (typically from 50% to 100%) that is multiplied by the computed value, which can greatly reduce the calculated index gain
* Does not includ the benefit of dividends, so the potential gain is less than that of risky assets.

3 ways to compute the increase in the index:
* Annual point-to-point: the increase is the percentage increase of the index using the end of year value.
* Monthly sum: the percentage monthly gains and losses are added together.  Can provide gains over the year if the index is volatile.  Monthly caps are applied each monthly, then each month is added up and cannot be higher than the yearly cap.
* Monthly average: the increase of the average monthly index value divided by the initial index value.  Can provide gains over the year if the index is volatile.  Sum the monthly index values and divide by 12.  Yearly caps are applied, but they don't have a spread.  Participation rates are multiplied by the end number.

Calculation of FIA using annual point-to-point where the index increase by 7%, has a cap of 5%, a spread of 1%, and a participation rate of 75% (if end increase is greater than the cap, reduce to the cap.  Then subtract the spread.  Then multiply by the participation rate):

> 7% > 5%, so that leaves 5%.  5% - 1% spread = 4%.  4% * 0.75 = 3% computed index gain

**Variable Annuities** are a type of deferred annuity that are purchased with after tax dollars and all earnings are tax deductible (like a non-deductible IRA).  Hold tax inefficient and high returning assets in a variable annuity. Fees for variable annuities vary widely. All gains are taxed as ordinary income. When the owner of a variable annuity dies, and the annuity transfers to someone other than a surviving spouse, the savings held within the annuity needs to be distributed over the next 5 years. Typical variable annuity investors have already exhausted their tax-deferred accounts and those who like the liquidity.  Once the annuity payments are turned on, the selection of invests narrows greatly.

The **Guaranteed Lifetime Withdrawal Benefit (GLWB)** is a type of variable annuity that has riders where the annuity pays income for life, even if you receive more than you paid in.  If needed, the investor can withdraw the entire amount, though there are fees associated with over-withdrawing. At death, any remaining contract value is paid to a designated beneficiary.  The owner as access to the contract value with this annuity. 

  Benefits of a GLWB:
  * Access to annuitized income
  * Potential for future increases
  
  Cons:
  * Payouts are lower than other guaranteed income (e.g immediate annuities) 

  Contract values in a GLWB can go down if:
  * Owner takes withdrawals
  * Investments in the accounts lose value
  * Fees are accessed for the rider (1% - 1.5%, viewed as an insurance premium)

  The **benefit base** of a GLWB is equal to the initial deposit.  In high water mark or rachet, the benefit base increases if the contract value is higher than the benefit base at the anniversary.

  The **distribution factor** of a GLWB is the yield on the annuity that is set the first time income is taken from the annuity.  The distribution factor is higer in older owners.



A **Single Premium Immediate Annuity** is an instant transfer, where the investor pays for the premuim up front and the insurance company pays a fixed amount for the rest of your life.  This differs from a variable annuity in that a variable annuity holder can access the basis and well as enjoy the growth.

**Qualified Lifetime Annuity Contract (QLAC)** is a type of deferred income annuity that allow distributions beyong the RMD age thresholds.  They are most appropriate for mitigating longevity risk.  The disadvantages are the limits and you're locked in for the rest of your life....unless the investor decides to annuitize the contract.

#### Annuity Riders

3 types of riders: 
* **Guaranteed Minimum Accumulation Benefit (GMAB)**: Provides guarantees that the account value will equal a specified value at the end of a specified period.  Most GMAB riders allow owners to reset (or ratchet or step-up benefit) the amount of the guarantee if the account value increases in the future.  This reset restarts another guarantee period.
  * Pros:
    * Guaranteed account value is available immediately
  * Cons:
    * Guarantee amounts are modest
    * Restrictions on how the value can be invested
    * Does NOT guarantee lifetime income
* **Guaranteed Minimum Withdrawal Benefit (GMWB)**: Provides guaranteed income in the form of fixed-percentage withdrawals (4% - 7%, depending on age) over the owner's lifetime.  The **benefit base** is used to calcluate the percentage withdraws (has no surrender value, is equal to the initial deposit at first and can increase on anniversary dates if the value is increasing).  Benefit is called a rachet, reset, or a high water mark benefit.  A **roll-up** or **annual interest guarantee** is the guaranteed annual increase amount that has a maximum/cap.
  * Pros:
    * Have the flexibility to offer withdrawals when the income is needed
    * The account value can be surrendered at any time
  * Cons:
    * Early withdrawals are small, and decrease the benefit base and income guarantee
    * Withdrawals larger than the allowed amount will eliminate the income guarantee  
* **Guaranteed Minimum Income Benefit (GMIB)**: Similar to the GMWB except that the income can only be taken out as an income annuity
  * Pros:
    * Lower rider charges
    * More generous rol-up benefits
  * Cons:
    * After annuitization, there is no longer access to the account balance

Many riders paid out during the recent recession, so they are now less favorable than they used to be.  The way to determine the value of a lifetime income rider is to compare it against a SPIA that pays the same guaranteed lifetime income.  It may make sense to purchase an income annuity rather than starting GMWB withdrawals or GMIB annuitization.


#### Annuity Payout Example

If a variable annuity with a benefit base of $100,000 and guaranteed income of $5,000 is invested in a portfolio that increases by 10%, the new benefit base moves to $110,000 and the new guaranteed income moves to $5,500.  This new base is locked in and can't decrease in the future if the portfolio decreases.  Once $5,500 is withdrawn, the contract value decreases by $5,500 to $104,500.

Withdrawals decrease the contract value by the amount of the withdrawal.

### Permanent Life Insurance

**Cash-value life insurance** is a life insurance policy that lasts the entire lifetime of the insured and acts like a life-cycle savings plan that smooths the cost of a death benefit.  A whole life policy is a cash-value life insurance.

The death benefit to a beneficiary is **not** a taxable event.

**Permanent insurance** remains in effect for the insurer's entire lifetime.  These have a larger premium, which pays for the funds in the policy called an **account value**.  The account value can be accessed by the policy holder, which sometimes has a surrender charge early in the policy (policy holder may have to repay).  In **traditional life insurance policies**, interest is paid in the form of dividends.  Policy holders of permanent insurance may have to pay an additional premium if the estimated interest rate is more than the earned interest rate.

Comparing Permanent Insurance Policies:
* Should have the same insurance amount and same assumed premiums and frequency paid into them
* Remove riders to just compare the insurance (riders can be compared separately)
* The earned or dividend interest rate should be the same
* Each external index should assume the same interest rate
* The policy with the largest account value is the best
* If low or no account value, permanent can be compared with term

**Term insurance** remains in effect for a specified time period. Younger people will pay less for term insurance than for permanent insurance.  Term insurance has a guaranteed premium.  Term is not ideal if the insurance is needed over the lifetime of the policy holder or if one's insurance needs might change in the future.  A 30 year term is much more expensive than a 15 year term because of the increased probability of death over the longer term in the later years.  Pricing for term insurance is competitive, with a very low insurance load (profit).

As we get older, life insurance gets more expensive.

#### Whole Life Insurance

A portion of the whole life premium is invested in bonds in a tax-deferred account and can be viewed as an alternative to a taxable bond investment since some can be withdrawn by the policy holder.  Insurance company returns can outpace individual bond investing since they can take on more risk, can invest in illiquid assets, and can have a long-term view.  Their general account is regulated, keeping assets in reserve relative to their liability.  Whole life is less sensitive to interest rate risk.

**Variable universal life insurance** allows the account value to be invested in mutual fund (aka subaccounts). **Indexed universal life insurance** allows the policy to earn interest credits based on how a stock index performs.  In both funds, the policy holder takes on investment risk that is similar to goal-based investing.

***Traditional whole life** and **basic universal life** have a more stable death benefit due to less investment risk.

**Universal life insurance** has variations in premiums each year, while **traditional life insurance** has regularly scheduled premiums.  Universal life insurance premiums are estimated (aka target or scheduled premiums).  Universal premiums can be paid in a single payment (aka single pay), ten premium payments (akd ten pay), or with a constant premium over the policy holder's life (level premium).  The deposits needed are determined using a **policy illustration**, which projects account value's growth over time (just a hypothetical estimate).

Life insurance only makes sense if the policy holder sees value in the death benefit since they pay a yearly **mortality charge** based on the percentage of insurers that are expected to die each year.  This mortality charge increases as the policy holder gets older.

Cash Value Life Insurance:
* The main benefit is life insurance protection
* Not necessarily a good savings strategy due to high fees
* Some policies require surrendering the death benefit to access the cash value and pay taxes on the growth
* Policy loans are loads on the cash value of a policy.  Repayment issues could trigger a surrender.
* Partial surrenders involve taking some cash value out, which reduces the overall death benefit and can cause premium increases

### Universal Life (UL) Insurance

Universal life is a type of permanent life insurance with a flexible premium with explicit interest credit and charges.

* **Target Premium**: keeps the policy in force using interest credit and charge assumptions, though not a guarantee and may involve additional premiums
* **Shadow Account Value**: Universal Life with a Secondary Guarantee (ULSG) will stay in force as long as a fixed premium is paid and only guarantees the shadow account value, which is computed using guarantees in the policy terms.  As long as the shadow account value is greater than zero, the policy is still in force (even if the actual value is negative).  The policy holder **cannot** access the shadow account value.
* **Stock Index and Hybrid UL Policy**: Variable UL used a mutual fund whil Indexed UL (IUL) utilizes an index.  There is also a Hybrid UL policy that includes life insurance and long-term care insurance.

Indexed Universal Life (IUL) policies account for 50% of UL policies.  These policies don't invest in the index, but rather mimic the index with a combination of bonds (for the guarantee portion) and derivatives.  Because of this, insurance companies have the right to limit the amount credited using caps, spreads, and participation rates, which can reduce the interest in a policy.  IUL indexes don't include dividend payments (averages 2.5% of the value each year).

> Net Amount of Risk = Death Benfit - Account Value
> Cost of Insurance = Net Amount of Risk * Insurance Protection Charge

A middle aged person with a UL policy having a $1,000,000 death benefit with a 1% insurance protection charge (based on age) and a $800,000 account value

> Net Amount of Risk = $1,000,000 - $800,000 = $200,000
> Cost of Insurance = $200,000 * .01 = $2,000

If the account value were only $50,000, then the Net Amount of Risk is $950,000 and the Cost of Insurance is $9,500.  Therefore, a smaller Net Amount of Risk decreases the impact of higher mortality rates for older policy holders.

The cost of insurance increases as the probability of death increases.  In the example above, if the policy holder is older, then the insurance company may charge a 10% Insurance Protection Charge.

> Net Amount of Risk = $1,000,000 - $800,000 = $200,000
> Cost of Insurance = $200,000 * .10 = $20,000

If the account value were only $50,000, then the Cost of Insurance is $95,000.

If the account value grows beyond the death benefit, the policy gets automatically converted into a **Modified Endowment Contract (MEC)** due to compliance reasons, though the policy holder can increase the death benefit or decrease the account value (withdrawls) to avoid this.  MEC interest is taxed as ordinary income when withdrawn.

If interest credits are less than expected or if interest charges are higher than expected, then additional deposits/premiums must be made to meet the target premium.  Policy growth should be evaluated regularly (e.g every 2 years) to pay for shortfalls early and avoid large premiums at a later date.  Smaller account values -> Larger net amount at risk -> Increased insurance charges.  If the policy holder cannot pay for the larger premium, they can ask for a new illustration to updated the target premium.

Partial withdrawls are **not** taxed if they are less than the basis of the policy.

> Basis = Sum of Premiums - Previous Withdrawls

Once the account value is reduced, the policy holder and elect to reduce the death benefit.

A policy loan is not a taxable event, but can become taxable if the policy is surrendered.  These loans don't have to be repaid if it's repaid by a surrender or death.  The loan value has an interest charge, which increases the loan amount over time.  If the policy loan ammount equals the account value, the policy will lapse.

Reasons why a policy holder may want to fully or partially monetize their UL policy:
* Need cash for personal or business reasons.  Here, they can get a policy loan or partial surrender.  If they want to life insurance to be covered in the orignal amount, there will be premiums accessed. Otherwise, they'll get a reduced benefit from the monetization.
* No longer needs the death benefit.  In this case, they get a life settlement, which may be more than the cash value.
* Diagnosed with a terminal illness.  May be able to convert some or all of the death benefit into cash, or get a special life settlement called a viatical settlement.
  
Tax basis of a UL is the total premium ammounts paid, minus any withdrawls.  Amounts withdrawn in excess of the bases are taxed as ordinary income upon policy surrender or lapse.

Taxation strategies:
* Withdrawls from a Policy: Unless a MEC, withrawls up to the basis amount aren't taxed, but any amount over the basis are taxed as ordinary income.
* Surrender of a Policy: For this one-time payment, any amount over the income tax basis are taxed as ordinary income.
* Exceptions: Withdrawls within the first 15 years of a policy, the gain portion (cash value - income tax basis) are taxed as ordinary income and the remaining balance is considered a return of basis (tax-free).
* Policy Loans: Not taxed unless a MEC.  If not repaid, the death benefit will cover the loan before paying out a reduced amount.
* Lapse of Policy: Similar to the above, but may include a "phanton income tax" (tax without getting a payment).
* Life Settlements: Settlement proceeds in excess of the gain in the cash surrender value are taxed as long-term capital gains.
* Viatical Settlements: Possibility of zero income tax assessed if the policy holder is expected to die within the next 24 months.  Chronically ill patients can get a life settlement, but not a viatical settlement.
  
### Alternative Investments

An alternative investment is an investment other than the traditional asset classes of cash, bonds, or stocks.  These can include commodities, real estate, private equity, hedge funds, art, wine, or stamps. Alternative investments became popular in the 1990s.

**Liquid Alternatives (Liquid Alts)** offer daily liquidity (and can be in mutual funds) and are invested in alternative investments similar to hedge funds.  Returns among different liquid alts are very different and are not considered an asset class.  Their portfolio benefit has been modest.

**Managed futures** invests in futures contracts in currency, energy, and interest rate markets and are based on a model.  They are constructed to have a low correlation with equities.

Key considerations when investing in Alternative Investments:
* Low Market Correlation: while this can be a good hedge, the increased risk can make it a detriment.
* Illiquidity: aka Lockup Provisions, they have minimum investment periods and limits on withdrawls.
* Fees: Fess are typiclaly higher in alternative investments
* Leverage: This can magnifiy the returns, either up or down.  A risk-parity strategy uses leverage to buy bonds that have higher than average bond interest rate risk.
* Lack of Historical Data: Makes it difficult to understand risk
* Benchmarking: Alternatives are difficult to benchmark.  Even common alternatives (e.g. commodities) can have different risks and returns.

#### Private Equities

**Private equity** is the private investment in the equity or debt of non-publicly traded companies.  This effectively allows investors to bypass traditional securities markets, but also have less investor protections. Private equity investments requires lots of due dilligence, high fees, low liquidity and are typically only available for larger investors.  It's important to consider **why** companies are giving up some ownership to private investors before investing.  It's generally difficult for wealth managers to analyze non-publicly traded assets.

Types of private equities:
* Leveraged Buyout (LEO): Buying a company to make it bigger and better, then selling after a holding period.  Middle-level risk.
* Venture Capital: Invest in startups that can be disruptive.  High risk.
* Distressed Equities: Buying distressed and underperforming private companies in the secondary market. Lower risk.
* Mezzanine Debt: Making debt investments in private companies in the secondary market
* Secondary Fund: Buying interest in other private equity funds in the secondary market

Private equity fund managers first create investment guidelines that outlines duration, number of companies, company size, markets, ...etc before selling shares to investors.  Most private equity investors are institutional investors and some high net worth investors.  These funds have a minimum investment size of $1 million or more, and require some diversification over multiple funds.  Most institutions allocate 5% - 20% to private equity.  Private equity funds typically last about 12 years.  The first 4 - 6 years (the "call period"), the funds collect the capital and fees, then they disperse the returns over the rest of the period ("realization period").

**Private equity fund-of-funds** are a package of many private equity funds that typically have a higher minimum investment amount.

Non-Traded REITS are a type of private equity that pool investor dollars and purchase real estate for a fixed period of time.

#### Commodities

Commodities are inputs into the production of good and are an important part of the market portfolio, but have a small presence in international markets.  The prices of commodities affect stock and bond prices.  Their use in a portfolio is controversial.

Commodities include agricultural products, metals and natural resources.

Ways to invest in Commodities:
* Buying Physical Commodities: Usually through a broker and includes transaction fees, shipping, insurance, and storage which affect the returns, which don't typically exceed the rate of inflation.
* Buying Shares of an ETF: More efficient than direct ownership, where the price is close to the NAV (e.g. SPDR gold ETF, where gains are treated as a collectible and does not qualify for long-term capital gains).
* Commodity Futures: Can be purchased directly or through an ETF and have similar performance of other commodity ETFs.
* The Purchase of Jewelry:  Commodity value is not as much as the retail price and the market is illiquid.  The risk-adjusted return is lower than other commodity ETFs.
* Investing in Companies and the Ownership of Commodities: Investing in companies that own commodities
  
Fully collateralized commodity futures have the same returns and Sharpe ratios as U.S. equities, and are negatively correlated with stocks and bonds.  Individual investors cannot practically invest in diversified commodity futures, and the available options aren't very diversified.  Direct holdings in commodities have higer fees, higher taxes and a lower risk premium.

Commodity funds have a positive correlation with inflation, though only 1/3 of commodities were able to keep up with inflation in the last 50 years.  There are better investment products for hedging inflation.

#### Cryptocurrency

Cryptocurrencies were created to give an alternative to fiat currencies. Their primary advantage is that they aren't controlled by governments (i.e. decentralized), so governments can't just print more when they want more (inflationary).  They are also free from political influence and can be held anonymously. Crypto can be used for illegal purchases and to avoid taxation.  Crypto is purely speculative, and can have big swings in value.

Satoshi Nakamoto wrote the white paper for bitcoin, which is an online, permanent ledger that are managed by multiple entities (miners).  Crypto is stored in wallets, which are cryptography secure via a key (password).  20% of all bitcoin is tied up in lost keys (passwords).  Bitcoin has a baked-in scarcity of 21 million coin.  Bitcoin uses Proof of Work, which miners must solve increasingly complex problems, using a lot of compute, to receive bitcoin.  Bitcoin transactions use more electricity than Argentina each year.

Bitcoin was valued at $550 billion in 2023, and Ethereum had a market cap of $220 billion.  CBDCs(central bank digital currencies) may eventually make cryptocurrency obsolete.  Since they aren't backed by governments, cryptos can lose all of their value.

In 2020, the correlation coefficient of the S&P was 0.36. In 2022, the correlation coefficient was 0.56.  There is no agreement on an optimal allocation of crypto in a diversified portfolio. 

#### Hedge Funds

Hedge funds are privately organized investments that actively manages a portfolio in a range of investments including stocks, bonds, and complex instruments (e.g. such as financial derivatives).  Hedge funds can take long and short positions, so can make money when an investment rises or falls in value. Hedge funds use leverage to magnify the risk and returns of the investments.  Only accredited investors ($200,000 in income, or $1 million in assets) can invest in hedgt funds.  They can have high fees.  A common fee structure is "2 and 20", where the hedge fund manager charges 2% AUM receives 20% of the profits. Because of the high fees and difficulty in due dilligence, hedge funds may not be great investments for individual investors. 

**Hedge fund-of-funds** are a package of many hedge funds that have been thoroughly analyzed (due dilligence). 

#### Derivatives

Derivatives are financial products that derive their value from other financial product(s).  **Options** are derivatives that provide the right (but not the obligation) to buy or sell another financial product.  A **hedge** is a derivative that pays out when the target assets loses value.

Options characteristics
* Zero-Sum Game: For every winner, there is a loser.
* Black Scholes Model: A perfectly hedged investment in a risky asset **has no risk**, and the expected return of a perfectly hedged investment is the risk-free rate.  Very similar to insurance contracts.
* Increasing Allocation to Safe Assets: For individual investors, it's best to invest in safe assets than invest in options due to higher transaction costs of options.
* Utlity: Options are useful for investors with an undiversified portfolio (e.g. high idiosyncratic risk).
  
Options are a contract between 2 parties, where one party writes an option that they make available for sale for a premium (e.g. the price) and the other party purchases the option to buy or sell the share of the underlying asset at a pre-determined price (aka strike price, or exercise price).  Options can exist on stocks as well as indexes.  The contract has an expiration date and could be either exercised before (American Option) or on the expiration date (European Option), depending on the type of option.

A **call option** gives the right to **buy** a share of stock at a given price.  If the current price of a stock is $50 and the premium is $2 and strike price is $55 on a three month contract, the investor only pays $2 if the stock never reaches $55 (called "out of the money").  If it does reach $60 (above $55, called "in the money"), then the $2 call option is worth $5 ($60 - $55) and can be immediately sold ($3 profit).  The call option can be sold by (1) selling the option to someone else or (2) buying the underlying asset for $55 and selling for $60. 

A **put option** gives the right to **sell** a share of stock at a given price. A put option increases in value when the price of the underlying stock drops below the strike price.  If the current price of a stock is $50 and the premium is $2 and strike price is $45 on a three month contract, the investor only pays $2 if the stock never goes below $45 (called "out of the money").  If it does reach $40 (below $45, called "in the money"), then the $2 call option is worth $5 ($60 - $55) and can be immediately sold ($3 profit).  Put options may be a good fit for investors that have a concentrated position in a single stock, which will result in lower expected wealth over time but provide an insurance-like benefit for the idiosyncratic risk of the single stock.

The Black-Scholes model states that options based on more volatile stocks should be more expensive than options on less volatile stocks.  If a 3 month call option with a strike price of $55 costs $2 for Stock A and $1 for Stock B, then the implied volatility of Stock A is higher than the implied volatility of Stock B. The **Volatility Index (VIX)** shows the change in implied volatility of US stocks over time.  The VIX is a good indicator of how panicked investors react to stock prices, but not a good predictor of how volatile stocks will be in the future.  While the VIX isn’t useful to wealth manager, it is a good reflection of the general mood of investors.

#### Short Selling

**Short selling** is selling a asset short in order to profit from a fall in price, without actually owning the asset.  A short seller borrows shares of stock from someone in a long position, sells the shares, then agrees to replace the shares at a later date.  Short sellers are motivated to promote bad news about a company.  Short selling is riskier than put options because a short seller needs to replace the shares by a certain date.   If the stock price goes up, a put option will expire, but a short seller must come up with the difference (a loss).  Short selling is an indication that many traders think the stock is overpriced.

Returns on the long-short strategy mutual funds are below the efficient frontier. The average standard deviation is about the same as an 80/20 portfolio. The average return is the same as a 35/65 portfolio. A long-short strategy (on average) provides more risk and lower returns than a balanced portfolio of long assets.

To get a higher return for a given level of risk, a fund would need to have assets with a higher Sharpe ratio than the market (e.g. bonds). Another strategy is to use leverage to increase the risk on a portfolio of safe assetswhich increases the standard deviation of bonds by borrowing funds at the risk-free rate and investing in a long bond portfolio. This is known as a risk parity strategy.  This strategy is suseptible to interst rate risk (increased rates lead to decreased bond prices, which creates a loss).

#### Structured Products

A **structured product** is an investment that bundles together traditional investment securities and derivatives into a single product.  They provide investors with an opportunity to have a return distribution that is different from a traditional investment portfolio.  It does this by keeping some investment risk, with the potential to capture part of the equity risk premium, while still providing protection against a loss below the risk-free rate. Basically, it can provide some upside potential while limiting an extreme downside event.

It's not practicaly for an individual investor to create a structured product, so they rely on structured products from institutions.  Because of the complexit, it's hard for wealth managers to analyze the product.

**Convertible bonds** are similar to structured products and can be converted into shares of stock if the stock price is above a predetermined conversion price, offering characteristics of bonds and stocks. They provide a base return lower than a regular bond, but with an upside potential if the stock price rises. 

Both convertible bonds and structurued products may generate capital gains or ordinary income, making it hard to determine the proper asset location.  It's also difficult to understand the return distribution and risk profile.

Structured Products are typically from one year to five years (or more). They have a principal guarantee and an upside potential due to the return of an underlying asset. 

A **zero-coupon bond** pays out the original investment amount at maturity. When buying this bond below the original investment price, the difference is used to purchase a call option that correlates with an index.

Cons of structured products include the credit risk of the issuer, illiquidity, increased complexity, and unique tax considerations. 

A **market-linked CD** has low credit risk and are FDIC insured.

FINRA requires advisors to perform due diligence to ensure the product is suitable for a client.  Structured products can't be traded in the primary or secondary market, and banks that issue them levy fees if liquidated early.

Equity-linked notes create interest income even if the Note does not pay a coupon, so investors might pay taxes from other accounts. If the structured product has some form of principal protection, all gains will be taxed at ordinary income rates. Without principal protection, all gains are taxed at capital gains rates if the product is held for more than one year.

#### Option Protected Products

**Option Protected Products** are financial instruments that use financial options to change the distribution of returns (instead of the normal bell curve), creating a buffer or a floor, which may be suitable for loss-averse investors and investors close to a financial goal (e.g. retirement).  Call options can sold to provide funding for put options to protect against a loss.  These products have a high expense, and their buffer/floor limits the upside potential (called a **cap**).  A buffer will shift much of the downside returns to 0%, resulting in a spike in the percentage of outcomes at exactly 0%.

**Buffered ETFs** and **Registered Index-Linked Annuities (RILA)** have a graduated floor with a stopping point.

A variable annuity with a a guaranteed minimum accumulation benefit rider behaves similar to a RILA.  For both, fees shift the bell curve to the left by reducing all returns above the floor by the amount of the fee.