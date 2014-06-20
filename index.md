---
title       : Automobile Fuel Efficiency Prediction
subtitle    : Course Project for Developing Data products
author      : Changzhou Wang
job         : A Coursera Student
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [bootstrap,quiz]            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Automobile Fuel Efficiency

* A major factor to total ownership cost
* Control pollution and protect environment
* Reduce energy footprint and resource consumption
* What impacts fuel efficiency?

--- .class #id 

## Method
* Build a linear regression model to predict mpg (miles per gallon)
* Data: 1974 Motor Trend US magzine data
  - mtcars dataset in R
* Input variables
  - Number of cylinders
  - Gross horsepower
  - Weight (in 1000lb)
  - Transmission: automatic (0) or manual (1)

--- .class #id 

## Model


```r
data(mtcars)
myfit <- lm(mpg ~ cyl + hp + wt + am, mtcars)
myfit$coefficients
```

```
## (Intercept)         cyl          hp          wt          am 
##    36.14654    -0.74516    -0.02495    -2.60648     1.47805
```

* The higher number of cylinders, horsepower or weight reduce fuel efficiency
* Manual transmission improve fuel efficiency
* E.g., a 6 cylinder, 250 horsepower, 3000lb automatic car has an expected mpg=18.

--- &radio

## Notes
* The dataset is old and its size is small
  - Recent dataset with a large number of morden cars will help 
* The input variables are hand picked
  - They are correlated themselves
    * The p-value for some variables are indeed large (>0.1)
  - There may be other important variables missing
  - Feature selection is likely to be helpful too
  
## What's the Bottom line?
  1. _1_ This is just an example :-)
  2. 2 This will accurately predict for your current cars! 
*** .explanation
More work needed to make the result useful in practice
