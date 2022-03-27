# Website A/B Test
## by Miguel Orellana

This was the third project from Udacity's Data Analyst Nanodegree covering the block on Practical Statistics.

The goal of this project is to determine if an e-commerce website should implement a new website. The dataset contains 290k divided in two groups, 'treatment' and 'control'.

The study is first done through an A/B Test and on a second stage using a Logistic Regression model.

## A/B Test

### Hypothesis definition

Null hypothesis : the converted rate of the new page minus the converted rate of the old page is equal or lower than 0:

    p(new) - p(old) <= 0

Alternative hypothesis : the converted rate of the new page minus the converted rate of the old page is higher than 0:

    p(new) - p(old) > 0

Type I error rate of 5%.

### Summary of Findings from A/B Test

1. Just by looking at the probability of the users that convert for both the control and treatment groups, there doesn't seem to be evidence to say that the new treatment page leads to more conversions. In fact, based only on these results, the probability for them to convert is slightly higher for the control group.

2. The A/B test fails to reject the null hypothesis, with a p-value of 0.9046. The graph below shows the mean difference between the probability for converting for 'treatment' and 'control' groups for a 10000 random sample. The red line indicates the actual difference observed in the original dataset.

![Mean difference distribution](/images/fig1.jpg)

## Logistic Regression

### Hypothesis definition

In a logistic regression model, the hypotheses refer to the relationship between two variables, in this case **X** would be the landing_page, and **Y** would be the conversion result. The null would say there's no relationship, and the alternative that there's a relationship. No relationship means both pages provide similar converted rates, so we  write them as follows:

    H0: p_new - p_old = 0
    H1: p_new - p_old != 0

Type I error rate of 5%.

### Summary of Findings from Regression Model

The regression model doesn't provide a clear understanding on what's making people convert, as the page (old vs new) doesn't seem to be clearly correlated, with a p-value of 0.1899.

After adding the country variable, the p-value is still above 0.05 and therefore a relationship between country and conversion cannot be established either.

## Conclusions

The dataset doesn't provide enough evidence to assume the new website would increase the conversion rate. Furthermore, there isn't a variable having a clear correlation to the converted rate so far. This suggests we'd still need to keep looking at other potential factors that may impact the converted rate. The dataframe contains information about the date and time when these pages were visited, so that could be another exploration to do. Another option would be to extend the experiment for a longer period of time, since the results might start varying as well.
