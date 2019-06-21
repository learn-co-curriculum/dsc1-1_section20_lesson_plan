
# Experimental Design - Lesson Plan


## Objectives

You will be able to:
 * Explain the relation between $\alpha$ (alpha), $\beta$ (beta), power and type I/II errors
 * Explain the tradeoffs in experimental design between power, sample size and effect size
 * Perform a standard T-Test to compare the means of equal sized samples
 * Demonstrate the relationship between power, sample size and effect size using graphs

## Prework

* Introduction
* Introduction to Experimental Design
* P-values and the Null Hypothesis
* Effect Sizes
* Type 1 and Type 2 Errors
* Statistical Power
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

## Class Outline

1. Introduction 15+ minutes
    * Perform an informal assessment and ask students to explain the relations between alpha, beta, power and type I / II errors, clarify if needed
    * Progress the discussion to include effect size and sample size and how these intrinsically relate to power
        * Again informal assessments should be used to gauge students understanding of this concept
        * Discussing the difficulty of detecting a unfair coin with P(Heads)=.55 vs an unfair coin with P(Heads)=.9 can provide intuitive context for how effect size, sample size and power are interconnected
2. Applications
    * I Do (5 min)
    * We Do (10 min)
    * You Do (10 min)
3. Discussion / Assessment
    * Circle back to a high level discussion regarding effect size, sample size and power
    * Key Questions:
        * If you increase the effect size, and the sample size remains constant, what will happen to the power of the statistical test?
        * For a set effect size, how are sample size and power related?
        * Explain how the power of a statistical test relates to type I and II errors.

## Introduction: Effect Size, Sample Size, Power and Type I vs II errors

> *Use this as a guideline to orientate the class and review key concepts*

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
```


```python
## We do - Mirror Code Above

## Generate 2 random samples

## Perform T-Test

## Repeat and Validate Type I/ Type II error Rates - How can we encapsulate this procedure using a function or functions?
def simulate_t_test():
    #Probably appropriate as a summative assessment or class discussion

## Repeat and Validate Type I/ Type II error Rates
effect_size = 
sample_size =
alpha = 
typeI_errors = 0
typeII_errors = 0

for i in range(10**3):
    #Generate Samples; potentially use a conditional to determine whether null hypothesis is true/false
    #Perform T-Test
    #Save results to typeI/typeII error counters
```


```python
## You do
#Choose an effect size. 
#Generate random samples using this parameter and determine the effective power at various sample sizes. 
```

## Discussion Question:

* How might you investigate the relationship between effect size, sample size and power for the above scenario?

## Assessment

* If you increase the effect size, and the sample size remains constant, what will happen to the power of the statistical test?
* For a set effect size, how are sample size and power related?
* Explain how the power of a statistical test relates to type I and II errors.

## Common Misconceptions

* **Misconception**: Effect size is the difference between the control and experimental group.
    > **Clarification**: Effect size is the difference between the null hypothesis and the alternative hypothesis; the difference which you hope to be able to measure. These statistical techniques will not definitively tell you the parametric difference between the two populations themselves. Rather, you are comparing the differences between two population *samples* and using this to determine the likelihood that the underlying populations are substantially different or not. The effect size is the minimum difference that you consider substantial and want to be able to detect in your statistical test.

### Reflection - To be filled out during pilot / subsequent implementations

Here's a list of thought starters for the instructor:
* How do you think this lesson went? What were the strongest points? Weakest?
* Were there additional student misconceptions that came up?
* To what degree have students mastered the defined objectives?
* Do you have any thoughts on alternative activities or explanations that would enhance this lesson? 

Further reflection questions for students can be found [here](https://github.com/learn-co-curriculum/ds-lessons-starter/blob/master/lesson-plan-materials/ReflectionQuestions.md).
