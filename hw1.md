p8105\_hw1\_lc3391
================
09/17/2019

Problem 1
=========

Creating a data frame
---------------------

``` r
la_df= tibble(
  norm_samp = rnorm(8),
  norm_samp_pos = norm_samp > 0,
  vec_char = c("a","b","c","d","e","f","g","h"),
  vec_factor = factor(c("low","med","high","low","low","med","high","high"))

)

mean(pull(la_df, norm_samp))
```

    ## [1] -0.1343904

``` r
mean(pull(la_df, norm_samp_pos))
```

    ## [1] 0.375

``` r
mean(pull(la_df, vec_char))
```

    ## Warning in mean.default(pull(la_df, vec_char)): argument is not numeric or
    ## logical: returning NA

    ## [1] NA

``` r
mean(pull(la_df, vec_factor))
```

    ## Warning in mean.default(pull(la_df, vec_factor)): argument is not numeric
    ## or logical: returning NA

    ## [1] NA

The mean of the numeric vector, norm\_samp, is -0.1343904. The mean of the logical vector, norm\_samp\_pos is 0.375. And NO mean could be taken for the character vector and factor vector.

converting variables from one type to another
---------------------------------------------

``` r
#covert the logical vector to numeric and multiply the random samnple by the result
as.numeric(pull(la_df, norm_samp_pos))*pull(la_df, norm_samp)
```

    ## [1] 0.15133162 0.00000000 0.00000000 0.00000000 0.91154280 0.06797252
    ## [7] 0.00000000 0.00000000

``` r
#covert the logical vector to factor and multiply the random samnple by the result
as.factor(pull(la_df, norm_samp_pos))*pull(la_df, norm_samp)
```

    ## [1] NA NA NA NA NA NA NA NA

``` r
#convert the logical vector to a factor and then convert the result to numeric, and multiply the random sample by the result
as.numeric(as.factor(pull(la_df, norm_samp_pos)))*pull(la_df, norm_samp)
```

    ## [1]  0.3026632 -0.1626245 -0.4130264 -0.4824880  1.8230856  0.1359450
    ## [7] -0.2715142 -0.8763170

Problem 2
=========

``` r
p2_df= tibble(
  x = rnorm(500),
  y = rnorm(500),
  vec_log = x + y > 1
)
```
