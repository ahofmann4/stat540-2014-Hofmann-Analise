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
##          [,1]    [,2]     [,3]     [,4]
##  [1,] -0.7898 -1.0590 -0.07554  0.28685
##  [2,] -0.4362 -1.3323  0.13888  2.17364
##  [3,] -0.6193 -0.4024  0.27123 -0.33950
##  [4,] -1.0810  0.4740 -0.07433  0.36334
##  [5,] -0.4249 -0.7405  0.42488  0.61343
##  [6,]  0.8947  0.6694 -0.93313 -0.45200
##  [7,] -0.7700  1.0256  0.51354  2.33111
##  [8,] -2.1736 -1.0123  0.92101  0.40465
##  [9,]  0.3153 -0.5745 -0.08822 -0.55400
## [10,] -0.5984  0.8848  2.50823 -0.05216
```



To assign names to the rows and columns:

```r
rownames(x) <- sprintf("obs%02d", 1:n)
colnames(x) <- sprintf("samp%02d", 1:B)
x
```

```
##        samp01  samp02   samp03   samp04
## obs01 -0.7898 -1.0590 -0.07554  0.28685
## obs02 -0.4362 -1.3323  0.13888  2.17364
## obs03 -0.6193 -0.4024  0.27123 -0.33950
## obs04 -1.0810  0.4740 -0.07433  0.36334
## obs05 -0.4249 -0.7405  0.42488  0.61343
## obs06  0.8947  0.6694 -0.93313 -0.45200
## obs07 -0.7700  1.0256  0.51354  2.33111
## obs08 -2.1736 -1.0123  0.92101  0.40465
## obs09  0.3153 -0.5745 -0.08822 -0.55400
## obs10 -0.5984  0.8848  2.50823 -0.05216
```


To make plots you can use very easy commands: 


```r
colMeans(x)
```

```
##  samp01  samp02  samp03  samp04 
## -0.5683 -0.2067  0.3607  0.4775
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


