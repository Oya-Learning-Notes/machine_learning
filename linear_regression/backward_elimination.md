- [About Backward Elimination](#about-backward-elimination)
- [Concepts](#concepts)
  - [Central Limit Theorem](#central-limit-theorem)
  - [Standard Error Of Predictors](#standard-error-of-predictors)
    - [Meaning Of Estimate Variance](#meaning-of-estimate-variance)
  - [P-Value](#p-value)


# About Backward Elimination

Backward Elimination **uses P-Value to check if a feature is unnecessary**, keep removing useless features to make the model better.

Backward Elimination is also **a way to resolve Overfitting** of the model.

# Concepts

## Central Limit Theorem

This theorem says: for any Distributions, **the `means` of the sample would fit `Normal Distribution`** with following formula.

$$
D \sim N(\mu, \frac{\sigma}{\sqrt{n}})
$$

- $\mu$ : The `means` of original Distributions.
- $\sigma$ : The `Standard Deviation` of original Distributions.
- $n$ : Size of the Population.

>  [Scribbr - Central Limit Theorem](https://www.scribbr.com/statistics/central-limit-theorem)

## Standard Error Of Predictors

In Linear Regression, we could calculate the `Standard Error` of each estimate coefficient ${\omega}_i$ from `Variance` of the predictor.

$$
SE_{\omega} = \sqrt{Variance(\omega)}
$$

However in Linear Regression, we only get one estimate coefficient as the result, what does the Variance means for an estimate? how could we calculate the Variance?

### Meaning Of Estimate Variance

We should remember that the model is trained upon a selected subset of the population, or we can say `sample`, so result the estimation $\omega_{Estimate}$ we made based on such sample will different from the True Coefficient $\omega_{True}$.

Here we only get one estimation $\omega$ since we only have one sample. However, imagine you have infinite set of sample, then you could train and get a set of estimation $\{\omega_1, \omega_2, \dots, \omega_n\}$, and the **Variance of the estimation would be the Variance of this set from the True Slope $\omega_{True}$**.

If we **only get one result** of estimation $\omega$, we could **still calculate the `Varaince` of the result by using the following formula**:

$$
\begin{aligned}
Variance(\omega_j) &= \frac{\sigma^2}{\sum (x_{ij} - \overline{x_j})^2 } \\
SE(\omega_j) &= \sqrt[]{Variance(\omega_j)} \\
&=\frac{\sigma}{\sum (x_{ij} - \overline{x_i} )}  
\end{aligned}
$$

In the formula:

- $\omega_j$ : The estimate coefficient of j-th `feature`
- $x_{ij}$ : The value of i-th `Observation` of j-th `feature`
- $\sigma$ : Standard Deviation of the `Residual`

-----

> [StackExchange - SE of Predictors in OLS Regression](https://stats.stackexchange.com/questions/391254/standard-error-of-simple-linear-regression-coefficients)

## P-Value

`P-Value` is a corresponding concept of Significant Level `SL`. It's used to 

> - [Medium - Essential Maths In ML](https://medium.com/@weidagang/essential-math-for-machine-learning-hypothesis-testing-t-statistic-and-p-value-933cb25fd757)
> - [GeeksForGeeks - P-Values With Examples](https://www.geeksforgeeks.org/p-value-in-machine-learning/)
