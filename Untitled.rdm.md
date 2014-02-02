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
##  [1,]  0.09585 -0.1442 -0.4858  0.83483
##  [2,] -2.64294  0.1543  0.4240  0.17613
##  [3,] -0.42998  0.3768 -0.7016  0.06638
##  [4,]  2.92581 -0.4120  1.2410  0.18912
##  [5,] -0.75875 -0.2552 -1.2034  0.45365
##  [6,] -0.58368  0.2051  0.8000 -0.32195
##  [7,] -0.73584 -0.2528 -0.6640 -0.41255
##  [8,] -1.93092 -1.3097 -1.0299 -0.54913
##  [9,] -0.46128  2.0572 -1.5974 -1.39705
## [10,] -1.52066  0.7462  0.8492 -1.18624
```



To assign names to the rows and columns:

```r
rownames(x) <- sprintf("obs%02d", 1:n)
colnames(x) <- sprintf("samp%02d", 1:B)
x
```

```
##         samp01  samp02  samp03   samp04
## obs01  0.09585 -0.1442 -0.4858  0.83483
## obs02 -2.64294  0.1543  0.4240  0.17613
## obs03 -0.42998  0.3768 -0.7016  0.06638
## obs04  2.92581 -0.4120  1.2410  0.18912
## obs05 -0.75875 -0.2552 -1.2034  0.45365
## obs06 -0.58368  0.2051  0.8000 -0.32195
## obs07 -0.73584 -0.2528 -0.6640 -0.41255
## obs08 -1.93092 -1.3097 -1.0299 -0.54913
## obs09 -0.46128  2.0572 -1.5974 -1.39705
## obs10 -1.52066  0.7462  0.8492 -1.18624
```


To make plots you can use very easy commands: 


```r
colMeans(x)
```

```
##  samp01  samp02  samp03  samp04 
## -0.6042  0.1166 -0.2368 -0.2147
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



