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

    ## [1] 0.4290628

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

``` r
#covert the logical vector to numeric and multiply the random samnple by the result
as.numeric(pull(la_df, norm_samp_pos))*pull(la_df, norm_samp)
```

    ## [1] 0.62050429 0.91739703 0.00000000 0.85800653 0.68935999 0.05601697
    ## [7] 0.60566970 1.23864921

``` r
#covert the logical vector to factor and multiply the random samnple by the result
as.factor(pull(la_df, norm_samp_pos))*pull(la_df, norm_samp)
```

    ## Warning in Ops.factor(as.factor(pull(la_df, norm_samp_pos)), pull(la_df, :
    ## '*' not meaningful for factors

    ## [1] NA NA NA NA NA NA NA NA

``` r
#convert the logical vector to a factor and then convert the result to numeric, and multiply the random sample by the result
as.numeric(as.factor(pull(la_df, norm_samp_pos)))*pull(la_df, norm_samp)
```

    ## [1]  1.2410086  1.8347941 -1.5531013  1.7160131  1.3787200  0.1120339
    ## [7]  1.2113394  2.4772984

Problem 2
=========

``` r
p2_df= tibble(
  x = rnorm(500),
  y = rnorm(500),
  vec_log = x + y > 1
)
```
