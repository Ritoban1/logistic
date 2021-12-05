# logistic

<!-- badges: start -->

[![R-CMD-check](https://github.com/Ritoban1/logistic/workflows/R-CMD-check/badge.svg)](https://github.com/Ritoban1/logistic/actions)
<!-- badges: end -->

The goal of logistic is to allow the user to use logistic regression in a beginner friendly way. In this package, we create a function with output that is limited to metrics that are important when beginning to learn about these regression techniques. Compared to glm, this function is easy to understand and interpret, and allow for easy, real-world, prediction capabilities. My hope for this package is for students, with knowledge of how to put data into these functions and formats, are able to better access and understand the functionalities of these methods.

Installation
------------

You can install the released version of logistic from GitHub. First, you should run in your console (or in a script, whatever..)

``` r
.rs.restartR()
remove.packages('logistic')
```

just to be sure and to avoid any possible bugs!

Then you can run

``` r
install.packages('devtools')
devtools::install_github('Ritoban1/logistic', build_vignettes = T)
library("logistic")
```

to get the package on your computer This will install two packages (bench and ggbeeswarm) automatically so that the user can access the vignettes!

What type of data should I use?
-------------------------------



### logistic

You *need* an *n* × *p* design matrix X of numeric covariates and either 1. an *n* × 1 binary outcome vector *y* or 2. two discrete *n* × 1 vectors, *y* and *n*, of "successes" (*y*) per "trials" (*n*). So, *y* &lt; *n*. The other options are optional, but as above specify the addition of an intercept and the possibility to predict outcomes using the model you have fit. There is also an option to change the number of iterations the algorithm runs to estimate the parameters, but this would rarely be needed.

Example
-------

This is a basic example which shows you how to solve a common problem and illustrates very basically the usage of the functions in the package:

``` r
library(logistic)


ucla =  read.csv("https://stats.idre.ucla.edu/stat/data/binary.csv")

X = cbind(ucla$gpa)

y = ucla$admit

fit_logistic = logistic(X,y)
#> Converged at iteration 4

names(fit_logistic) # more things to choose from
#> [1] "coeffs"    "se"        "wald"      "p"         "or"        "fitted"   
#> [7] "predicted"
```

These are basic examples which preclude any or planned analysis, please use

``` r
?logistic 
```

for more examples or, for even more info (recommended!!!!), use

``` r
browseVignettes(package = 'logistic')
```

and click HTML to see more complex examples and how to use these functions in a more complete way.


