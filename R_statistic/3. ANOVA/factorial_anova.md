# ANOVA

## Factorial ANOVA

Source of variation | Sum of squares | Degrees of freedom | Mean square              | F
A                   | SSA            | J-1                | MSA = SSA/J-1            | F = MSA / MSE
B                   | SSB            | K-1                | MSB = SSb/K-1            | F = MSB / MSE
A*B                 | SSAB           | (J-1)(K-1)         | MSAB = SSAB/(J-1)(K-1)   | F = MSAB / MSE
Error               | SSE            | N-JK               | MSE = SSE/(N-JK)         |
Total               | SST            | N-1                |                          |

R code:
```r
# if df is a data frame with three columns: Score, A, and B
# And A and B are categorical variables
df$A <- as.factor(df$A) # this is very important, otherwise R will treat A as a continuous variable
df$B <- as.factor(df$B) # this is very important, otherwise R will treat B as a continuous variable

model <- aov(Score ~ A * B, data = df)

summary(model)

# if we want consider the equal variance assumption, it will be more complicated, will discuss in regression part.
```

## Repeated measures ANOVA

