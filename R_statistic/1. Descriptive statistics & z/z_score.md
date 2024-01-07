# R basic

## Descriptive statistics
### Measure of central tendency
#### Mean
The mean is the average of the numbers. It is easy to calculate: add up all the numbers, then divide by how many numbers there are.

```r
x <- c(1, 2, 3, 4, 5)
mean(x)
```

#### Median
The median is the middle number in a sorted, ascending or descending, list of numbers and can be more descriptive of that data set than the average.

```r
x <- c(1, 2, 3, 4, 5)
median(x)
```

#### Mode
The mode is the number that is repeated more often than any other, so 13 is the mode.

```r
x <- c(1, 2, 3, 4, 5)
mode(x)
```

### Measure of variability
#### Range
The range is the difference between the largest and smallest numbers.

```r
x <- c(1, 2, 3, 4, 5)
range(x)
```

#### Interquartile range
The interquartile range is the difference between the third quartile and the first quartile.

```r
x <- c(1, 2, 3, 4, 5)
IQR(x)
```

#### Standard deviation
The standard deviation is a measure of how spread out numbers are.

```r
x <- c(1, 2, 3, 4, 5)
sd(x)
```

#### Variance
The variance is a measure of how far each number in the set is from the mean.

```r
x <- c(1, 2, 3, 4, 5)
var(x)
```

### Measure of shape
#### Skewness
Skewness is a measure of the asymmetry of the probability distribution of a real-valued random variable about its mean.

```r
x <- c(1, 2, 3, 4, 5)
skewness(x)
```

#### Kurtosis
Kurtosis is a measure of the "tailedness" of the probability distribution of a real-valued random variable.

```r
x <- c(1, 2, 3, 4, 5)
kurtosis(x)
```

## *z* score
*z* score is a measure of how many standard deviations below or above the population mean a raw score is.

$$
z = \frac{x - \mu}{\sigma}
$$

where:
x is a raw score to be standardized

μ is the mean of the population

σ is the standard deviation of the population

```r
# if x is a population
# and we must know the mean and standard deviation of the population
x <- c(1, 2, 3, 4, 5)
mean <- mean(x) # mean of the population
sd <- sd(x) # standard deviation of the population
z <- (1 - mean) / sd # z score of 1, 1 can be any number in the population (raw score)
z
```

## Standard error
The standard error measures the standard deviation of sample statistics when repeated samples are taken from the same population (the standard deviation of the sampling distribution of a statistic).

$$
SE = \frac{\sigma}{\sqrt{n}}
$$

where:

σ is the standard deviation of the population

n is the sample size

```r
# if x is a sample
x <- c(1, 2, 3, 4, 5)
sd <- 1 # standard deviation of the population, assume we know it
n <- length(x) # sample size
se <- sd / sqrt(n)
se
```

## *z* test
*z* tests usually require that the population standard deviation be known, which is not common in practice. If the populaton standard deviation is unknown, a *t* test is usually used instead.

When the sample size is large (n > 30), the sample standard deviation provides a better estimate of the overall standard deviation and the *z* test results are more reliable.

### One sample z test
The one-sample *z* test is used to compare a sample mean to a population mean when you have a sample from a population that has a normal distribution and you know the population standard deviation.

$$
z = \frac{\bar{x} - \mu}{\frac{\sigma}{\sqrt{n}}}
$$

where:

$\bar{x}$ is the sample mean

μ is the population mean

σ is the population standard deviation

n is the sample size

```r
# if x is a sample
x <- c(1, 2, 3, 4, 5)
mean <- mean(x) # sample mean
mu <- 3 # population mean, assume we know it
sd <- 1 # standard deviation of the population, assume we know it
n <- length(x) # sample size
z <- (mean - mu) / (sd / sqrt(n))
z
```

### Two sample *z* test
The two-sample *z* test is used to compare two sample means from two populations when you have two samples from two populations that have normal distributions and you know the population standard deviations.

$$
z = \frac{\bar{x_1} - \bar{x_2}}{\sqrt{\frac{\sigma_1^2}{n_1} + \frac{\sigma_2^2}{n_2}}}
$$

where:

$\bar{x_1}$ is the sample mean of sample 1

$\bar{x_2}$ is the sample mean of sample 2

$\sigma_1$ is the population standard deviation of population 1

$\sigma_2$ is the population standard deviation of population 2

$n_1$ is the sample size of sample 1

$n_2$ is the sample size of sample 2

```r
# if x1 and x2 are two samples
x1 <- c(1, 2, 3, 4, 5)
x2 <- c(1, 2, 3, 4, 5)
mean1 <- mean(x1) # sample mean of sample 1
mean2 <- mean(x2) # sample mean of sample 2
sd1 <- 1 # standard deviation of the population 1, assume we know it
sd2 <- 1 # standard deviation of the population 2, assume we know it
n1 <- length(x1) # sample size of sample 1
n2 <- length(x2) # sample size of sample 2
z <- (mean1 - mean2) / sqrt((sd1^2 / n1) + (sd2^2 / n2))
z
```

