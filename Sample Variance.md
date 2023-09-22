Let $X_{1},...,X_{n}$ be a random sample. The sample variance is defined as
$$s^{2} = \frac{1}{n-1} \sum_{k=1}^{n} (X_{k} - \bar{X})^2.$$
It may seem odd that we divide by $n-1$ as the sum includes $n$ terms but there are good reasons for it. However, to grasp the underlying reason, we first have to introduce the concept of estimators.

Assume that we have a random sample $X_{1},...,X_{n}$ generated from some distribution with an unknown parameter $\theta$. By utilizing the random sample, given that it is of sufficently large size, we can 
formulate a random variable, $\hat{\theta}$, to estimate the unknown parameter $\theta$. This random variable, $\hat{\theta}$, is called an estimator of $\theta$. It is common practice to use the sample mean $\bar{X}$ as an estimator for the true mean $\mu$. This seems reasonable, but how can we be sure that there is no better estimator for $\mu$ than $\bar{X}$? And how do we judge if an estimator is good or bad? A sound reasoning for a good estimator $\hat{\theta}$ is that it should be as close as possible to the true parameter $\theta$. Recall that the estimator $\hat{\theta}$ is a random variable that is a function of the given random sample and thus has an expected value $E[\hat{\theta}]$. It seems reasonable to assume that the expected value of a good estimator should be equal to the unkown parameter, that is
$$E[\hat{\theta}] = \theta.$$
When this equality holds we say that $\hat{\theta}$ is unbiased and biased if not. 

Lets now prove that the sample mean is an unbiased estimator for $\mu$. We have that 
$$E[\bar{X}] = E[\frac{1}{n}\sum_{k=1}^{n} X_{k}] = \frac{1}{n} \sum_{k=1}^{n} E[X_{k}] = \frac{1}{n} \sum_{k=1}^{n} \mu = \frac{1}{n} \cdot n \cdot \mu = \mu.$$

Lastly, we will now argue that 
$$s^{2} = \frac{1}{n-1} \sum_{k=1}^{n} (X_{k} - \bar{X})^2,$$
is a better estimator for the variance than 
$$\hat{s}^{2} = \frac{1}{n} \sum_{k=1}^{n} (X_{k} - \bar{X})^2$$
by showing that $\hat{s}^{2}$ is biased whilst $s^{2}$ is not.

We have 
$$E[\hat{s}^{2}] = E[\frac{1}{n} \sum_{k=1}^{n} (X_{k} - \bar{X})^2] = E[\frac{1}{n} \sum_{k=1}^{n} X_{k}^2 - n\bar{X}^2] = \frac{1}{n} \sum_{k=1}^{n} E[X_{k}^2] - nE[\bar{X}^2].$$
By utilizing 
$$Var[X] = E[X^2] - E[X]^2$$
we get
$$E[X_{k}^2] = Var[X_{k}] + E[X_{k}]^2 = \sigma^2 + \mu^2$$
and
$$E[\bar{X}^2] = Var[\bar{X}] + E[\bar{X}]^2 = \frac{\sigma^2}{n} + \mu^2.$$
Putting it all together we get
$$E[\hat{s}^{2}] = \frac{1}{n} \cdot ( n(\sigma^2 + \mu^2) - n(\frac{\sigma^2}{n} + \mu^2)) = \frac{1}{n} \cdot \sigma^2(n-1) = \frac{n-1}{n}\sigma^2 \neq \sigma^2,$$
which shows that \hat{s}^{2} is biased. However, it is easy to see that if we instead would divide by $n-1$ as we do in the definition of $s^2$ the factors would cancel out which would give us
$$E[s^2]=\sigma^2,$$
giving us an unbiased estimator. That is the reason why we divide by $\frac{1}{n-1}$ instead of dividing by the total number of random variables in the sample.
