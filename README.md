
# Experimental Design

## Introduction

This section is all about conducting statistical experiments! 

## Prework

* Introduction
* Introduction to Experimental Design
* P-values and the Null Hypothesis
* Effect Sizes
* Type 1 and Type 2 Errors
* Statistical Power
* 
* Multiple Comparisons Problem
* A/B Testing
* Goodhart’s Law and Metric Tracking
* ANOVA
* Section Recap

## Postwork
* Type 1 and Type 2 Errors - Lab
* One Sample T-Test - Lab
* Two Sample T-Test - Lab
* Statistical Power - Lab
* Effect Sizes, P Values, and Power - Lab
* A/B Testing - Lab
* ANOVA - Lab

## Effect Size, Sample Size, Power and Type I vs II errors

Designing well thought out experiments requires careful consideration of balancing the precision and confidence you desire your results to have versus the amount of data required to meet these standards. If you wish to detect a 1% increase in patient outcomes for a new blood pressure medicine, you will need substantially more data then if you were in search of a 5% increase in outcomes. The reason is that more subtle differences such as an increase of only 1%, could be caused by simple random variation alone, and thus the sample size required to confidently detect such small differences can be quite large. 

One of the most common experimental designs is a **hypothesis test** or **A/B test**. In a hypothesis test, one states the null hypothesis. Typically, this is written with the hope of rejecting the null hypothesis. In the case of the blood pressure example above, it would be sensible to state the null hypothesis along the lines of "drug B will lower patients normal systolic blood pressure by 10." In addition, one then also defines the desired effect size one wishes to be able to reasonably detect for the alternative hypothesis. For example, one might state the alternative hypothesis as "drug B will lower patients normal systolic blood pressure by 12." In this scenario, the measure **effect size** is 2. (The null hypothesis stated 10 vs the alternative hypothesis stated 12; the difference is the effect size.) Finally, one then chooses either a sample size that is feasible to attain, or a required confidence level required for the domain. Typically, many researches use de facto standards of $\alpha = .05$ or $\alpha = .01$. These translate to having a 95% confidence and 99% confidence in the results achieved, respectively. That is, an $\alpha$ value of .05 implies that you will reject the null hypothesis 5% of the time when it is actually true. This is also know as the rate of **type I errors**. While you can use lower values of alpha such as $\alpha=.01$, doing so will increase the rate of **type II errors**, or the chance that you will accept the null hypothesis when it is actually false. 

Similarly, we call the rate of type II errors $\beta$ (beta). Alternatively, the term **power** is used which is $1-\beta$. Thus as the power increases, the rate of type II errors decreases. Ideally one strives for statistical tests with a high level of power while also maintaining realistic sample sizes. With all of this, let's take a look at conducting some T-tests to compare the means of two sample groups. Afterwards, we'll then further investigate the relationship between power, sample size and effect size.


```python
## I do
import numpy as np

## Generate 2 random samples
sample1 = np.random.normal(loc=10, size=20)
sample2 = np.random.normal(loc=12, size=20)

## Perform T-Test
stats.ttest_ind(sample1, sample2)

## Repeat and Validate Type I/ Type II error Rates
```


```python
## We do 
```


```python
## You do
```

## Discussion Questions:

* How might you investigate the relationship between effect size, sample size and power for the above scenario?

# Additional Useful Investigation from V2

https://github.com/learn-co-curriculum/dsc-effect-sizes-pvalues-and-power-lab/tree/solution

## ANOVA

> Note: Briefly mention, but focus attention to developing a solid understanding of A/B testing. There's already a lot of theory and concepts for students to master
