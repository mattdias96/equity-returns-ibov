# equity-returns-ibov
Evaluating all equity funds in the Brazilian Stock Exchange to look for unexpected returns

## Intro

The idea for this analysis came from a conversation with a few friends about how the Efficient Market Hypothesis (EMH) could be rejected empirically. While there is a vast literature on this topic, I wanted to devise a simple test that could show whether some equity funds were able to achieve unlikely excessive returns consistently. This is an interesting debate for personal investors like me because if the EMH holds, then passive investing by holding onto ETFs should always be preferred over buying specific investment funds and paying performance and management fees. 

## Theory

EMH postulates that consistent generation of alpha (excess return) is impossible. Here we define alpha according the Capital Pricing Model (CAPM) as the difference between the expected return of a portfolio given its risk (variance of monthly returns) and the actual observed return. The expected return of a portfolio is defined as the risk free rate added to the volatility of the stock (covariance between market returns - IBOV in this case - and the returns of the portfolio) times the difference between the returns from the market and the risk free rate. Mathematically, we have:

[Add CAPM Model image]

## Survival Bias

If EMH is true, then alpha tend to zero as the investment horizon extends. However, the data may not show this for at least two reasons. First, the time interval of the equity funds returns data we have access to is limited (2002-2022) and alpha may converge too slowly for us to see it approacing zero. Secondly, there is a clear survival bias: equity funds that perform worse tend to not last long, since investors will remove money from the fund because of its lower performance.

[Add survivor function plots]

## Hypothesis Test and Synthetic Porfolio Construction


[Add p-value plot]


## Analysis of high alpha investment funds

TBD

## Data

### Source

- [Theoretical Porfolio IBOVESPA March 2002](https://www.estadao.com.br/economia/ibovespa-nova-carteira-teorica-para-maio-a-agosto/)
- [Brazilian Equity Investment Funds larger than BRL$10M](https://www.kaggle.com/datasets/matheusdias1996/brazilian-investment-funds)


### Datasets

I made both datasets available at Kaggle
- [Theoretical Porfolio IBOVESPA March 2002](https://www.kaggle.com/datasets/matheusdias1996/carteira-teorica-ibov-mar2002)
- [Brazilian Equity Investment Funds larger than BRL$10M](https://www.kaggle.com/datasets/matheusdias1996/brazilian-investment-funds)

