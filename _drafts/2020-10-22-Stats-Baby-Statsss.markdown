---
layout: post
title:  "STATISTICS"
author: "Carter Lockwood"
date:  2020-10-22
categories: school stats
---
Disclaimer: I may split this document into many parts in the future, but for now this will be the compiled location of notes that I take while reading Learning statistics with R by Danielle Navarro (insert link later)


## Measurement
Theoretical construct - the thing you're trying to measure
Measure - the method or tool you use to make your observations (survey, behavioural observation, brain scan)
Operationalisation - logical connection between construct and measure. Process by which we try to derive a measure from a construct.
Variable - what we end up with when we apply our measure to something in the world. The actual 'data' we end up with in our data sets.

### Scales of Measurement
#### Nominal Scale
Also referred to as a categorical variable. Nomical scale is one in which there is no particular relationship between the different variables. Eye color, gender : none of them are 'better' than the other.

#### Ordinal Scale
Ordinal scale variables are more structured than nominal. OS variables have a natural order to the different possibilities, but that's it. You can use natural ordering to group, but you cannot average responses.

#### Interval Scale
Interval scale and ratio scale variables are variables where the numerical values are genuinely meaningful. The differences between variables are interpretable. When comparing values, differences are interpretable but dividing and multiplying values are not. With interval scale 0 is more of an arbitrary value. If you're measuring temp: 0 is a temperature and you can have values above and below that. 20 degrees isn't 100% hotter than 10 degrees.

#### Ratio Scale
With Ratio scale variables, zero really means zero. It's ok to multiply and divide. For example if you're measuring time, 0 seconds is not an arbitrary value. It literally means no time has passed. 4 seconds is literally twice as long as 2 seconds.

#### Continuous versus Discrete Variables
Two types of variables. Need to be aware of the distinction.
- Continuous Variable- for any two values it is always logically possible to have another value in between.
- Discrete Variable- There is nothing between two values.

Kinda abstract. Time is continuous. Nominal scale variables are always discrete. Nominal, Ordinal, Interval, and Ratio can all be discrete. Only nominal and ratio can be continuous.

### Assessing the reliability of a measurement
Reliability is how precisely you are measuring, validity is how accurate a measure is.

### The 'role' of variables: predictors and outcomes
- Independent variable - the predictor, the thing doing the explaining (represented by X)
- Dependent Variable- the variable being explained (Y)
IV and DV are terrible names because the IV is never actually independent of everything else and if there's no relationship between the variables then the DV doesn't actually depend on the IV.
Predictors(x) and Outcomes(y) are better names.

### Descriptive Statistics
Any time that you get a new data set, one of the first things you should do is find ways to summarize the data in a compact, easily understood fashion. This is what *descriptive statistics* is all about.

#### Measures of central tendency
In most situations, the first thing you're going to look for when investigating is the 'central tendency' of the data. This is helpful for getting a good gist of the data.

##### Mean, median, and mode
The mean is the good old fashioned average. You already know what this is. N is usually used to refer to the number of observations in a set. Y

#### Variance and Standard deviation
Variance is the average of the squared deviation of the mean considering degrees of freedom. Commonly referred to as S squared. The standard deviation is the square root of the variance. Also referred to as S, sigma, sd, or std dev. Basic rule of thumb, 68% of your data should fall 1 sd from the mean. 95% within 2; 99.7% between 3. This works most of the time but is built on the premise that our data distribution or histogram is symmetric and bell-shaped.


## Probability
#### Frequentist vs Bayes
Frequentist - defines probabiility as a long run frequency. The more observations you get the closer you get to the truth. Frequentist view of probability is grounded in the real world and unambiguous. Disadvantage: infinite sequences don't exist in the real world. Pretty narrow scope.

Bayesian - probability is the degree of belief that a rational agent assigns to the truth of that event. 'Rational Gambling'

### Probability Distributions
The vast majority of this book relies on 5 distributions: binomial distribution, normal distribution, t distribution, chi square distribution, and F distribution.

#### Introducing the binomial distribution
Hypothetical game: dice roll - you've got 20 dice. 1 side of each die has a skull on it, the other 5 sides are blank. The number of dice rolls in our experiment is the size parameter of our binomial distribution. Theta will represent the probability a single die comes up with a skull. This theta value is also known as the success probability of the binomial. We'll use X to refer to the results of our experiment, aka the total number of skulls when all 20 dice get rolled. The actual value of X is left up to chance so we call it the random variable. We want to know the probability that X=4 given that we know Theta = 0.167 (1/6) and N = 20. *Binomial Distributions are discrete, not continuous*

### The normal distribution
The most important - aka the bell curve and the Gaussian distribution. A normal distribution is described using two parameters: the mean of the distribution and the standard deviation of the distribution. (Distribution mean is represented by mu, looks like a u with a trunk and Std Dev of the distribution is represented by sigma, a circle with a mullet). *Normal distributions are continuous, whereas binomial are discrete.* The area beneath the curve must add up to 1, much how like the sum of the bars in binomial must add up to 1. A note about probability density: it's difficult to give a true probability for a continuous value, so it's more reasonable to talk about the probability something lies within a particular range of values. We do this by calculating the area under the curve. Probability density (y axis in a normal distrib) doesn't mean much by itself, but they're 'rigged' to ensure that the area under the curve is always interpretable as probabilites.

### t distribution
The t distribution looks a lot like a normal distribution, but has heavier tails. This distribution tends to come up in situations where you think the data actually follows a normal distribution, but you don't know the mean or standard deviation.

### Chi square distribution
We mainly see these when doing categorical data analysis, but they pop up everywhere. If you have a bunch of variables that are normally distributed, square up their values and then add them up (known as sum of squares), this sum has a chi square distribution.

### F distribution
Looks similar to a chi square distribution, and arises when you need to compare two chi square distributions to one another. Chi square is important when looking at sum of squares, but what happens if you want to compare two different sum of squares. Greater depth will come in later chapters.

These distributions are all related to the normal distribution and to each other. 

## Estimating unknown quantities from a sample
