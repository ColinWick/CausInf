Causal Inference Midterm
================
Colin Wick
3/11/2021

``` r
knitr::opts_knit$set(message=F,warning=F)
library(tidyverse)
```

    ## -- Attaching packages --------------------------------------- tidyverse 1.3.0 --

    ## v ggplot2 3.3.3     v purrr   0.3.4
    ## v tibble  3.0.6     v dplyr   1.0.4
    ## v tidyr   1.1.2     v stringr 1.4.0
    ## v readr   1.4.0     v forcats 0.5.1

    ## -- Conflicts ------------------------------------------ tidyverse_conflicts() --
    ## x dplyr::filter() masks stats::filter()
    ## x dplyr::lag()    masks stats::lag()

# Question 1

``` r
mydf <- data.frame(matrix(c(4,3,10,8,6,8,2,1,2,4,1,1,6,2,4,9,10,3,5,8,3,3,4,6,1,9,5,2,9,1),ncol = 3,byrow = TRUE))
names(mydf) <- c("Y1","Y0","X")
```

Using the ATE definition *E*(*Y*<sup>1</sup>) − *E*(*Y*<sup>0</sup>)

``` r
ATE <- mean(mydf$Y1) - mean(mydf$Y0)
ATE
```

    ## [1] -0.9

The ATE comes out to -0.9, meaning that exercise is associated with a
-0.9 point decrease in reported health, on average.

# Question 2

The Switching Equation is
*Y*<sub>*i*</sub> = *D*<sub>*i*</sub>*Y*<sub>*i*</sub><sup>1</sup> + (1 − *D*<sub>*i*</sub>)*Y*<sub>*i*</sub><sup>2</sup>

``` r
mydf <- mydf %>%
  mutate(D = ifelse(Y1 > Y0,1,0),
         switch = ifelse(Y1 > Y0,Y1,Y0))
mydf
```

    ##    Y1 Y0  X D switch
    ## 1   4  3 10 1      4
    ## 2   8  6  8 1      8
    ## 3   2  1  2 1      2
    ## 4   4  1  1 1      4
    ## 5   6  2  4 1      6
    ## 6   9 10  3 0     10
    ## 7   5  8  3 0      8
    ## 8   3  4  6 0      4
    ## 9   1  9  5 0      9
    ## 10  2  9  1 0      9

``` r
ATT <- mean(mydf$Y1[mydf$D == 1]) - mean(mydf$Y0[mydf$D == 1])
ATU <- mean(mydf$Y1[mydf$D == 0]) - mean(mydf$Y0[mydf$D == 0])
```

The outcome of the switching equation is stored in our dataframe and
yields ATT = 2.2 and ATU = -4.

ATT != ATU but this is common and expected.

# Question 3

``` r
SDO <- mean(mydf$Y1[mydf$D == 1]) - mean(mydf$Y0[mydf$D == 0]) 
pi <- sum(mydf$D)/10
s_bias <- mean(mydf$Y0[mydf$D == 1]) - mean(mydf$Y0[mydf$D == 0])

decomp <- data.frame(t(c(SDO,ATE,s_bias,(1-pi)*(ATT-ATU))))
names(decomp) <- c("SDO","ATE","Selection","Heterog. TE Bias")

knitr::kable(decomp,caption = "Decomposition") %>% kableExtra::kable_classic_2()
```

<table class=" lightable-classic-2" style="font-family: &quot;Arial Narrow&quot;, &quot;Source Sans Pro&quot;, sans-serif; margin-left: auto; margin-right: auto;">
<caption>
Decomposition
</caption>
<thead>
<tr>
<th style="text-align:right;">
SDO
</th>
<th style="text-align:right;">
ATE
</th>
<th style="text-align:right;">
Selection
</th>
<th style="text-align:right;">
Heterog. TE Bias
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:right;">
-3.2
</td>
<td style="text-align:right;">
-0.9
</td>
<td style="text-align:right;">
-5.4
</td>
<td style="text-align:right;">
3.1
</td>
</tr>
</tbody>
</table>

We have
*S**D**O* = *A**T**E* + *E*(*Y*<sup>0</sup>\|*D* = 1) − *E*(*Y*<sup>1</sup>\|*D* = 0) + (1 − *π*)(*A**T**T* − *A**T**U*)
as the decomposition and each value is listed above.

# Question 4

## a

The two key assumptions necessary for 2SLS to work (along with standard
Gauss-Markov assumptions, of course) are:

*C**o**v*(*Z*, *ϵ*) = 0 and *δ* ≠ 0

The standard 2SLS estimator for *β* is
$\\frac{Cov(Y,Z)}{Cov(X,Z)} = \\hat\\beta\_{IV}$. In this case (two
dummy variables), the estimator is called a Wald estimator, which can be
written as $\\frac{E(Y\|Z=1)-E(Y\|Z=0)}{E(X\|Z=1)-E(X\|Z=0)} = \\beta$

## b

The Weak Instrument problem is one where the relationship between the
exogenous instrument and the endogenous covariate are not strongly
correlated enough to generate unbiased and/or significant estimates.
Having a weak instrument implies the first-stage estimator is
insignificant or extremely small, which will throw off the second-stage
estimate. The most common test for weak instruments is an F-test, where
an F-statistic less than 10 should be considered too weak to use in a
regression.

## c
