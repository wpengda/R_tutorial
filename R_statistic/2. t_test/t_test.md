# *t* test
As said before, if the populaton standard deviation is unknown, a *t* test is usually used instead.

## One sample *t* test
The one-sample *t* test is used to compare a sample mean to a population mean when you have a sample from a population that has a normal distribution and you don't know the population standard deviation.

$$
t = \frac{\bar{x} - \mu}{\frac{s}{\sqrt{n}}}
$$

where:

$\bar{x}$ is the sample mean

μ is the population mean

s is the sample standard deviation

n is the sample size

R code:
In R, the t.test() function is built-in and is included in the stats package of the base R distribution. stats is one of the standard packages for R. It is automatically included in the default installation of R, so there is no need to install it additionally.
```r
# x is a sample
x <- c(1, 2, 3, 4, 5)
t.test(x, mu = 0) # mu is the population mean

```

## Independent sample *t* test
The independent sample *t* test is used to compare two sample means from two populations when you have two samples from two populations that have normal distributions and you don't know the population standard deviations.   

$$
t = \frac{\bar{X}_1 - \bar{X}_2}{s_{\text{pooled}} \sqrt{\frac{1}{n_1} + \frac{1}{n_2}}}

s_{\text{pooled}} = \sqrt{\frac{(n_1 - 1)s_1^2 + (n_2 - 1)s_2^2}{n_1 + n_2 - 2}}
$$

where:

$\bar{X}_1$ is the sample mean of sample 1

$\bar{X}_2$ is the sample mean of sample 2

$s_{\text{pooled}}$ is the pooled standard deviation

$s_1$ is the sample standard deviation of sample 1

$s_2$ is the sample standard deviation of sample 2

$n_1$ is the sample size of sample 1

$n_2$ is the sample size of sample 2

R code:
```r
# if x1 and x2 are two samples
x1 <- c(1, 2, 3, 4, 5)
x2 <- c(1, 2, 3, 4, 5)
t.test(x, y, var.equal = TRUE) # var.equal = TRUE means the two samples have the same variance
```

## Paired sample *t* test
The paired sample *t* test is used when the two samples are related in some way. For example, if you have two samples of the same people before and after some treatment, you can use the paired sample *t* test to compare the means of the two samples.

$$
t = \frac{\bar{d}}{\frac{s_d}{\sqrt{n}}}
$$

where:

$\bar{d}$ is the mean of the differences between the two samples

$s_d$ is the standard deviation of the differences between the two samples

n is the sample size

R code:
```r
# if x and y are two samples
x <- c(1, 2, 3, 4, 5)
y <- c(1, 2, 3, 4, 5)
t.test(x, y, var.equal = TRUE, paired = TRUE)
```

## Homoscedasticity and heteroscedasticity
Homoscedasticity is the property of a set of random variables where the variance is the same for all variables. Heteroscedasticity is the property of a set of random variables where the variance is not the same for all variables. 

## Welch's *t* test
Welch's *t* test is used when the two samples have different variances. It is more robust than the independent sample *t* test, which assumes that the two samples have the same variance.

$$
t = \frac{\bar{X}_1 - \bar{X}_2}{\sqrt{\frac{s_1^2}{n_1} + \frac{s_2^2}{n_2}}}

\text{df} = \frac{\left(\frac{s_1^2}{n_1} + \frac{s_2^2}{n_2}\right)^2}{\frac{\left(\frac{s_1^2}{n_1}\right)^2}{n_1 - 1} + \frac{\left(\frac{s_2^2}{n_2}\right)^2}{n_2 - 1}}
$$

where:

$\bar{X}_1$ is the sample mean of sample 1

$\bar{X}_2$ is the sample mean of sample 2

$s_1$ is the sample standard deviation of sample 1

$s_2$ is the sample standard deviation of sample 2

$n_1$ is the sample size of sample 1

$n_2$ is the sample size of sample 2

df is the degrees of freedom

R code:
```r
# if x and y are two samples
t.test(x, y, var.equal = FALSE) # var.equal = FALSE means the two samples have different variances
```
### How do you know if the two samples have different variances?
We can use Levene's Test to test if the two samples have different variances. If the p-value is less than 0.05, we can reject the null hypothesis that the two samples have the same variance. If the p-value is greater than 0.05, we can't reject the null hypothesis that the two samples have the same variance.

R code:
```r
# if x and y are two samples
library(car)
leveneTest(x, y)
```

### Other function related to *t* test
R code:
```r
# t is the t value
# df is the degrees of freedom
pt(t, df, lower.tail = TRUE) # lower tail probability
# pt will give the probability of the lower tail
pt(t, df, lower.tail = FALSE) # upper tail probability
# pt will give the probability of the upper tail

# p is the probability
# df is the degrees of freedom
qt(p, df, lower.tail = TRUE) # lower tail quantile
# qt will give the lower tail quantile
qt(p, df, lower.tail = FALSE) # upper tail quantile
# qt will give the upper tail quantile
```
## Effect size

### Cohen's *d*
Cohen's *d* is a measure of effect size. It is the difference between two means divided by a standard deviation for the data. It is used for comparing the difference between two means. It is also used for comparing the difference between a mean and a known value. It is also used for comparing the difference between two proportions.

effect siz as small (*d* = 0.2), medium (*d* = 0.5), and large (*d* = 0.8).

R code:
```r
# if x and y are two samples
library(effsize)
# cohen.d() is a function in the effsize package
# pool = TRUE means the pooled standard deviation is used, variance is assumed to be equal
d_pooled <- cohen.d(group1, group2, pooled = TRUE)
# pool = FALSE means the unpooled standard deviation is used, variance is assumed to be unequal
d_unpooled <- cohen.d(group1, group2, pooled = FALSE)
```

