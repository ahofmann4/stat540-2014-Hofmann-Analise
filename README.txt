Seminar 2
============================

Generating data
------------------

This is setting up a random " rnorm" 10 x 4 matrix:

```r
n <- 10
B <- 4
x <- matrix(rnorm(n * B), nrow = n)
x
```

```
##           [,1]    [,2]    [,3]     [,4]
##  [1,] -0.11934  0.2319  0.2757  0.86738
##  [2,] -0.92638  1.3078  0.4886  0.56042
##  [3,] -0.33619  0.6501  1.7917 -0.47170
##  [4,] -1.24135 -0.6608  0.1475  1.16050
##  [5,]  0.02571 -0.0547  1.1252 -1.23069
##  [6,]  0.55478 -0.5920 -1.5510 -0.41619
##  [7,]  0.37675  1.7835 -0.2695 -1.25209
##  [8,]  0.02861  0.9105  1.0604 -0.06528
##  [9,] -0.67793  0.9460 -0.6377  1.55470
## [10,] -0.20409 -0.2477 -0.2830  0.75359
```



To assign names to the rows and columns:

```r
rownames(x) <- sprintf("obs%02d", 1:n)
colnames(x) <- sprintf("samp%02d", 1:B)
x
```

```
##         samp01  samp02  samp03   samp04
## obs01 -0.11934  0.2319  0.2757  0.86738
## obs02 -0.92638  1.3078  0.4886  0.56042
## obs03 -0.33619  0.6501  1.7917 -0.47170
## obs04 -1.24135 -0.6608  0.1475  1.16050
## obs05  0.02571 -0.0547  1.1252 -1.23069
## obs06  0.55478 -0.5920 -1.5510 -0.41619
## obs07  0.37675  1.7835 -0.2695 -1.25209
## obs08  0.02861  0.9105  1.0604 -0.06528
## obs09 -0.67793  0.9460 -0.6377  1.55470
## obs10 -0.20409 -0.2477 -0.2830  0.75359
```


To make plots you can use very easy commands: 


```r
colMeans(x)
```

```
##  samp01  samp02  samp03  samp04 
## -0.2519  0.4275  0.2148  0.1461
```

```r
plot(colMeans(x))
```

![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-3.png) 


If you use the #1 it refers to row, #2 column:

```r
h <- apply(x, 1, mean)
```


Here is another scatter plot of the means of the rows:

```r
plot(h)
```

![plot of chunk unnamed-chunk-5](figure/unnamed-chunk-5.png) 


