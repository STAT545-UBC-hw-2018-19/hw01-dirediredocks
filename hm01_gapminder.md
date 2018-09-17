Hw01\_Gapminder
================
Matias
2018-09-16

Gapminder Exploration
=====================

1. Load gapminder data
----------------------

``` r
require(gapminder)
```

    ## Loading required package: gapminder

2. How many rows and columns?
-----------------------------

``` r
nrow(gapminder)
```

    ## [1] 1704

``` r
ncol(gapminder)
```

    ## [1] 6

3. There are 6 columns
----------------------

``` r
head(gapminder)
```

    ## # A tibble: 6 x 6
    ##   country     continent  year lifeExp      pop gdpPercap
    ##   <fct>       <fct>     <int>   <dbl>    <int>     <dbl>
    ## 1 Afghanistan Asia       1952    28.8  8425333      779.
    ## 2 Afghanistan Asia       1957    30.3  9240934      821.
    ## 3 Afghanistan Asia       1962    32.0 10267083      853.
    ## 4 Afghanistan Asia       1967    34.0 11537966      836.
    ## 5 Afghanistan Asia       1972    36.1 13079460      740.
    ## 6 Afghanistan Asia       1977    38.4 14880372      786.

4. Lets explore GDP per capita
------------------------------

``` r
mean(gapminder$gdpPercap)
```

    ## [1] 7215.327

``` r
median(gapminder$gdpPercap)
```

    ## [1] 3531.847

``` r
min(gapminder$gdpPercap)
```

    ## [1] 241.1659

``` r
max(gapminder$gdpPercap)
```

    ## [1] 113523.1
