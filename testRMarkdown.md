---
title: "Test R Markdown"
output: 
  html_document: 
    keep_md: yes
---

Write a single English sentence.


```r
library(dplyr)
```

```
## 
## Attaching package: 'dplyr'
```

```
## The following objects are masked from 'package:stats':
## 
##     filter, lag
```

```
## The following objects are masked from 'package:base':
## 
##     intersect, setdiff, setequal, union
```

```r
library(tibble)
data("mtcars")
head(mtcars, 6)
```

```
##                    mpg cyl disp  hp drat    wt  qsec vs am gear carb
## Mazda RX4         21.0   6  160 110 3.90 2.620 16.46  0  1    4    4
## Mazda RX4 Wag     21.0   6  160 110 3.90 2.875 17.02  0  1    4    4
## Datsun 710        22.8   4  108  93 3.85 2.320 18.61  1  1    4    1
## Hornet 4 Drive    21.4   6  258 110 3.08 3.215 19.44  1  0    3    1
## Hornet Sportabout 18.7   8  360 175 3.15 3.440 17.02  0  0    3    2
## Valiant           18.1   6  225 105 2.76 3.460 20.22  1  0    3    1
```

```r
mtcars <- mtcars %>%  rownames_to_column(var="type")

  
mtcars %>% group_by(type) %>% 
  summarize(mpg=mean(mpg))
```

```
## `summarise()` ungrouping output (override with `.groups` argument)
```

```
## # A tibble: 32 x 2
##    type                 mpg
##    <chr>              <dbl>
##  1 AMC Javelin         15.2
##  2 Cadillac Fleetwood  10.4
##  3 Camaro Z28          13.3
##  4 Chrysler Imperial   14.7
##  5 Datsun 710          22.8
##  6 Dodge Challenger    15.5
##  7 Duster 360          14.3
##  8 Ferrari Dino        19.7
##  9 Fiat 128            32.4
## 10 Fiat X1-9           27.3
## # ... with 22 more rows
```


