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

    ## [1] 0.3653897

``` r
mean(pull(la_df, norm_samp_pos))
```

    ## [1] 0.875

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

converting variables from one type to another
---------------------------------------------

Problem 2
=========

``` r
p2_df= tibble(
  x = rnorm(500),
  y = rnorm(500),
  vec_log = x + y > 1
)
```
