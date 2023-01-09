# equity-returns-ibov
Evaluating equity funds in the Brazilian Stock Exchange to look for unexpected returns

## Intro

The idea for this analysis came from a conversation with a few friends about how the Efficient Market Hypothesis (EMH) could be rejected empirically. While there is a vast literature on this topic, I wanted to devise a simple test that could show whether some equity funds were able to achieve unlikely excessive returns consistently. This is an interesting debate for personal investors like me because if the EMH holds, then passive investing by holding onto ETFs should always be preferred over buying specific investment funds and paying performance and management fees. 

## Theory

EMH postulates that consistent generation of alpha (excess return) is impossible. Here we define alpha according the Capital Pricing Model (CAPM) as the difference between the expected return of a portfolio given its risk (variance of monthly returns) and the actual observed return. The expected return of a portfolio is defined as the risk free rate added to the volatility of the stock (covariance between market returns - IBOV in this case - and the returns of the portfolio) times the difference between the returns from the market and the risk free rate. Mathematically, we have:

[Add CAPM Model image]

## Survival Bias

If EMH is true, then alpha tend to zero as the investment horizon extends. However, the data may not show this for at least two reasons. First, the time interval of the equity funds returns data we have access to is limited (2002-2022) and alpha may converge too slowly for us to see it approacing zero. Secondly, there is a clear survival bias: equity funds that perform worse tend to not last long, since investors will remove money from the fund because of its lower performance (sometimes causing it to perform even worse since assets need to be liquidated quickly)

[Add survivor function plots]

## Hypothesis Test and Synthetic Porfolio Construction

For each equoty fund, we generate 1,000 vector of random weights for 13 different stocks that composed 70% of the IBOV portfolio in March 2002. Each of these vectors is a different synthetic portfolio, and we compute its associated alpha given its returns during the same time interval of the actual portfolio. We then compute the probability of observing the actual alpha if it was sampled from the distribution of synthetic alphas (p-value). If there was no survival bias and alpha cannot be consistently generated, we would expect p-values to be uniformly distributed over 0 and 1.

[Add p-value plot]

The distribution looks fairly unform for p-values in [0.10, 0.90], but the extremes concentrate a lot of the weight. There seems to be evidence for equity funds that perform significatly better and worse than 0.

## Methodological Issues

I list below problems with my analysis:
- No rebalance of the stocks in IBOV: I am always sampling from the same 13 stocks that were relevant in 2003. This provides an unfair advantage to the equity funds I am comparing to since the actual IBOV performed better than this 13 stocks. I could solve this problem by updating my set of stocks to be sampled from at regular periods.


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

