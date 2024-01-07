# ANOVA

## One-way ANOVA

Source of variation | Sum of squares | Degrees of freedom | Mean square        | F
Between             | SSb            | k-1                | MSb = SSb/k-1      | F = MSb / MSw
Within              | SSw            | N-k                | MSw = SSw/(N-k)    |
Total               | SSt            | N-1                |                    |

R code:
```r
# if df is a data frame with two columns: Score and Group
# And Group is a categorical variable
df$Group <- as.factor(df$Group) # this is very important, otherwise R will treat Group as a continuous variable

model <- aov(Score ~ Group, data = df)

# we also need to check the variance assumption for ANOVA
leveneTest(model) # if the p-value is less than 0.05, we can reject the null hypothesis that the variances are equal

oneway.test(Score ~ Group, data = df, var.equal = T) # if homogeneity is violated then set var.equal = F

# if the variances are equal we can also just summary the model
summary(model)
```
### Effect size
Unlike *t* test, ANOVA doesn't have a single effect size measure. Instead, it has several effect size measures. The following are some of the effect size measures for ANOVA.
#### Eta squared
R code:
```r
library(effsize)
eta_squared(anova, partial = FALSE)
```

#### Omega squared
R code:
```r
library(effsize)
omega_squared(model)
```

#### Partial eta squared
R code:
```r
library(effsize)
eta_squared(anova, partial = TRUE)
```

#### Cohen's *f*
R code:
```r
library(effsize)
cohen.f(model)
```
