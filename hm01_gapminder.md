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

5. By loading the `tidyverse` package we can do more interesting analysis.
--------------------------------------------------------------------------

``` r
library(tidyverse)
```

    ## ── Attaching packages ────────────────────────────────────────────── tidyverse 1.2.1 ──

    ## ✔ ggplot2 3.0.0     ✔ purrr   0.2.5
    ## ✔ tibble  1.4.2     ✔ dplyr   0.7.6
    ## ✔ tidyr   0.8.1     ✔ stringr 1.3.1
    ## ✔ readr   1.1.1     ✔ forcats 0.3.0

    ## ── Conflicts ───────────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()

6. A comparison of lifeExp and gdpPercap by country, sorted by lifeExp first and then by gdpPercap.
---------------------------------------------------------------------------------------------------

``` r
gapminder %>%
  select(lifeExp, gdpPercap, country) %>%
  arrange(lifeExp, gdpPercap)
```

    ## # A tibble: 1,704 x 3
    ##    lifeExp gdpPercap country     
    ##      <dbl>     <dbl> <fct>       
    ##  1    23.6      737. Rwanda      
    ##  2    28.8      779. Afghanistan 
    ##  3    30        485. Gambia      
    ##  4    30.0     3521. Angola      
    ##  5    30.3      880. Sierra Leone
    ##  6    30.3      821. Afghanistan 
    ##  7    31.2      525. Cambodia    
    ##  8    31.3      469. Mozambique  
    ##  9    31.6     1004. Sierra Leone
    ## 10    32.0      543. Burkina Faso
    ## # ... with 1,694 more rows

7. A plot of lifeExp versus gdpPercap for all countries.
--------------------------------------------------------

``` r
ggplot(gapminder, aes(x = gdpPercap, y = lifeExp)) + geom_point()
```

![](hm01_gapminder_files/figure-markdown_github/unnamed-chunk-7-1.png)

``` r
plot <- ggplot(gapminder, aes(x = gdpPercap, y = lifeExp)) 
```
