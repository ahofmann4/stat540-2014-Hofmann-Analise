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
##          [,1]    [,2]     [,3]    [,4]
##  [1,] -0.4667 -0.3083  1.03254 -0.4780
##  [2,]  1.1376  1.3866  1.00219 -1.2053
##  [3,]  1.3199  0.3096  0.03707  3.1718
##  [4,]  1.0739 -1.1302 -1.02973 -0.2980
##  [5,]  0.1649  0.3681  0.52611 -0.8869
##  [6,] -0.5839  0.2492 -0.42050  0.3136
##  [7,]  0.1760 -0.1226  1.14207 -1.2646
##  [8,]  1.4915 -1.3699  1.53274 -0.1841
##  [9,] -1.7367  1.1975  0.65432 -0.2082
## [10,]  0.7170  0.0419 -0.56048 -0.4766
```



To assign names to the rows and columns:

```r
rownames(x) <- sprintf("obs%02d", 1:n)
colnames(x) <- sprintf("samp%02d", 1:B)
x
```

```
##        samp01  samp02   samp03  samp04
## obs01 -0.4667 -0.3083  1.03254 -0.4780
## obs02  1.1376  1.3866  1.00219 -1.2053
## obs03  1.3199  0.3096  0.03707  3.1718
## obs04  1.0739 -1.1302 -1.02973 -0.2980
## obs05  0.1649  0.3681  0.52611 -0.8869
## obs06 -0.5839  0.2492 -0.42050  0.3136
## obs07  0.1760 -0.1226  1.14207 -1.2646
## obs08  1.4915 -1.3699  1.53274 -0.1841
## obs09 -1.7367  1.1975  0.65432 -0.2082
## obs10  0.7170  0.0419 -0.56048 -0.4766
```


To make plots you can use very easy commands: 


```r
colMeans(x)
```

```
##   samp01   samp02   samp03   samp04 
##  0.32934  0.06219  0.39163 -0.15164
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



