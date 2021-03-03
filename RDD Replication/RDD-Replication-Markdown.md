Assignment 2
================
Colin Wick
2/10/2021

Hansen (2015) uses panel BAC and police data to construct a regression
discontinuity model exploiting the “arbitrary” cutoffs of DUI
consequences at different BAC levels. The first task is establishing the
homogeneity and independence of BAC in order to validate that there is
no clustering around specific values, as shown in Figure 1. The BAC of
drivers is approximately normal with no evidence of bunching around
cutoffs.

Then, exploiting the underlying normality of BAC levels, he is able to
analyze differences between those who fell just above and just below a
given threshold and DUI recidivism. He finds a sharp drop in recidivism
along the first BAC cutoff (.08) and a weaker drop on the second.

He then does a handful of robustness checks and deeper looks into
recidivism, finding the effect is strongest for those whom had never
been tested and were caught above the .08 threshold but below the .15
threshold.

![](RDD-Replication-Markdown_files/figure-gfm/unnamed-chunk-4-1.png)<!-- -->

    ## [1] "with P-value of McCrary tests 0.89 and 0.46 we fail to reject the null that there is no bunching around cutoffs"

Recreating Figure 1 from Hansen. A histogram of BAC shows there is no
visible evidence of bunching around either cutoff. Running the McCrary
test finds no statistical evidence either.

<table class="kable_wrapper lightable-classic-2" style="font-family: &quot;Arial Narrow&quot;, &quot;Source Sans Pro&quot;, sans-serif; margin-left: auto; margin-right: auto;">
<tbody>
<tr>
<td>
<table>
<caption>
For BAC=.08
</caption>
<thead>
<tr>
<th style="text-align:left;">
</th>
<th style="text-align:right;">
male
</th>
<th style="text-align:right;">
white
</th>
<th style="text-align:right;">
age
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left;">
estimate
</td>
<td style="text-align:right;">
0.0062
</td>
<td style="text-align:right;">
0.0057
</td>
<td style="text-align:right;">
-0.1405
</td>
</tr>
<tr>
<td style="text-align:left;">
se
</td>
<td style="text-align:right;">
0.0060
</td>
<td style="text-align:right;">
0.0050
</td>
<td style="text-align:right;">
0.1640
</td>
</tr>
<tr>
<td style="text-align:left;">
mean at .079
</td>
<td style="text-align:right;">
0.7900
</td>
<td style="text-align:right;">
0.8500
</td>
<td style="text-align:right;">
34.1800
</td>
</tr>
</tbody>
</table>
</td>
<td>
<table>
<caption>
For BAC=.15
</caption>
<thead>
<tr>
<th style="text-align:left;">
</th>
<th style="text-align:right;">
male
</th>
<th style="text-align:right;">
white
</th>
<th style="text-align:right;">
age
</th>
</tr>
</thead>
<tbody>
<tr>
<td style="text-align:left;">
estimate
</td>
<td style="text-align:right;">
0.0003
</td>
<td style="text-align:right;">
0.0068
</td>
<td style="text-align:right;">
0.1152
</td>
</tr>
<tr>
<td style="text-align:left;">
se
</td>
<td style="text-align:right;">
0.0040
</td>
<td style="text-align:right;">
0.0040
</td>
<td style="text-align:right;">
0.1190
</td>
</tr>
<tr>
<td style="text-align:left;">
mean at .149
</td>
<td style="text-align:right;">
0.7900
</td>
<td style="text-align:right;">
0.8600
</td>
<td style="text-align:right;">
34.5000
</td>
</tr>
</tbody>
</table>
</td>
</tr>
</tbody>
</table>

<img src="RDD-Replication-Markdown_files/figure-gfm/unnamed-chunk-7-1.png" style="display: block; margin: auto;" />

    ##             V1           V2       V3
    ## 1 -0.024032531 -0.024032531 92.76366
    ## 2  0.004353026  0.004353026 16.84294
