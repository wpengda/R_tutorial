# Regression

## Pearson Correlation Coefficient

$$
r = \frac{\sum_{i=1}^{n} (X_{i} - \overline{X})(Y_{i} - \overline{Y})}{\sqrt{\sum_{i=1}^{n} (X_{i} - \overline{X})^{2}} \sqrt{\sum_{i=1}^{n} (Y_{i} - \overline{Y})^{2}}}
$$

$$
r = \frac{\text{Cov}(X, Y)}{\sigma_X \sigma_Y}
$$

## Covariance

if is population divided by n

$$
\text{Cov}(X, Y) = \frac{1}{n-1} \sum_{i=1}^{n} (X_i - \overline{X})(Y_i - \overline{Y})
$$

## Regression coefficient

$$
b = \frac{\sum_{i=1}^{n} (X_i - \overline{X})(Y_i - \overline{Y})}{\sum_{i=1}^{n} (X_i - \overline{X})^2}
$$

$$
Y = a + bX
$$

$$
b = \frac{\sigma_{XY}}{\sigma_X^2}
$$

$ \sigma_{XY} $ is the covariance of X and Y

## Standardized regression coefficient

$$
\beta = b \times \frac{\sigma_X}{\sigma_Y}
$$

## Correlation and regression coefficient

$$
b = r\frac{\sigma_Y}{\sigma_X}
$$


