<<<<<<< HEAD

=======
>>>>>>> 377d9c8e78829164590150f4030e3fc1136516b4
Seminar 2
============================

Generating data
------------------

This is setting up a random " rnorm" 10 x 4 matrix:
<<<<<<< HEAD

```r
n <- 10
B <- 4
x <- matrix(rnorm(n * B), nrow = n)
x
```

```
##           [,1]     [,2]     [,3]     [,4]
##  [1,] -1.05771 -0.10171  0.29128 -1.08420
##  [2,] -1.45314 -0.48142 -0.53298  0.03820
##  [3,]  2.54016 -0.02761 -0.11140 -0.22346
##  [4,] -1.00592 -1.08278 -1.55681  0.57666
##  [5,]  0.79305  0.53879 -1.09399 -0.98127
##  [6,] -2.81229  1.17569 -0.44606  1.67985
##  [7,]  0.34365  0.26845  0.06427  0.30428
##  [8,]  1.53223 -2.18819  0.34254 -1.52646
##  [9,] -0.49920  0.38954 -0.92183  0.08898
## [10,] -0.05945 -0.56703 -0.63258 -0.67686
```



To assign names to the rows and columns:

```r
rownames(x) <- sprintf("obs%02d", 1:n)
colnames(x) <- sprintf("samp%02d", 1:B)
x
```

```
##         samp01   samp02   samp03   samp04
## obs01 -1.05771 -0.10171  0.29128 -1.08420
## obs02 -1.45314 -0.48142 -0.53298  0.03820
## obs03  2.54016 -0.02761 -0.11140 -0.22346
## obs04 -1.00592 -1.08278 -1.55681  0.57666
## obs05  0.79305  0.53879 -1.09399 -0.98127
## obs06 -2.81229  1.17569 -0.44606  1.67985
## obs07  0.34365  0.26845  0.06427  0.30428
## obs08  1.53223 -2.18819  0.34254 -1.52646
## obs09 -0.49920  0.38954 -0.92183  0.08898
## obs10 -0.05945 -0.56703 -0.63258 -0.67686
```


To make plots you can use very easy commands: 


```r
colMeans(x)
```

```
##  samp01  samp02  samp03  samp04 
## -0.1679 -0.2076 -0.4598 -0.1804
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


=======
```{r}
n  <- 10
B <- 4
x <- matrix(rnorm(n*B), nrow = n)
x
```


To assign names to the rows and columns:
```{r}
rownames(x)  <- sprintf("obs%02d", 1:n)
colnames(x)  <- sprintf("samp%02d", 1:B)
x
```

To make plots you can use very easy commands: 

```{r}
colMeans(x)
plot(colMeans(x))
```

If you use the #1 it refers to row, #2 column:
```{r}
h <- apply(x, 1, mean)
```

Here is another scatter plot of the means of the rows:
```{r}
plot(h)
```

>>>>>>> 377d9c8e78829164590150f4030e3fc1136516b4
