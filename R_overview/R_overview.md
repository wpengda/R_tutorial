# R_overview
Here I will mainly explain how to download R and Rstudio, and how to use Rstudio, which is a very good IDE (integrated development environment) for R, and can help us to use R better.

The official website for R, https://www.r-project.org/, is where you can download R.

The official website for Rstudio is https://posit.co/ where you can download Rstudio.

## R package
R has a lot of packages that provide a wide range of functionality. When you install the basic R software, you are already accompanied by the necessary extension packages, such as base, stats, graphics, etc. These packages are loaded by default when you start R and do not require user intervention.

However, there are many other packages that are not loaded by default. You need to install them yourself and load them when you need them. The installation of the package is very simple, just use the install.packages() function. For example, if you want to install the ggplot2 package, you can use the following code:

```r
install.packages("ggplot2")
```

After the installation is complete, you can use the library() function to load the package. For example, if you want to load the ggplot2 package, you can use the following code:

```r
library(ggplot2)
```

Since different packages may use the same function name, the "package::function()" syntax should also be used when there is a conflict between the names of functions in two packages. For example, if you want to use the mean() function in the base package, you can use the following code:

```r
base::mean()
```

