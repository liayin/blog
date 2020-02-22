---
layout: post
title: Interview at TJX
---

Their data science group has two full time data scientists and one full time senior data analyst. The other members are two co-ops. Their data science manager is Chen Liu and the senior data analyst is Wenchi Jin. Wenchi conducted a half-hour phone interview with me today. First introduced the group, then asked me to introduce myself. Then asked statistics questions, SQL questions, and a programming question.

Statistics questions:

0. Bias - variance tradeoff

This is a criterion for comparing models. One model might have a large bias but a small variance across samples, another might have a smaller bias but a large variance across samples. In order to mitigate this problem, we should use the concept of mean squared error, which is bias squared plus variance. Maybe it helps to talk about how OLS has no bias, but regularization methods such as lasso has a smaller variance.

1. If we are to compare the average height of Americans and Canadians, what test should we use? And then about null hypothesis and alternative hypothesis.

two sample T test.

2. If the p-value is .01 and the level of significance is .05, is the result significant?

Yes.

3. How would you explain p-value to someone who has not taken statistics before? 

I answered that there is a 99% percent chance that the two values are not the same and 1% chance that the two values are the same.

SQL question:
1. What's the difference between an inner join and a left join?

2. How do you select emails that are in Table 1 but not in Table 2?
Use notin command.

Programming question:
1. Binary search

Product question:
What is a good customer? If there is a customer who spends $10,000 and another one who spends $100 in a given time period, which customer is better?
I touched upon looking at other time periods, checking if they returned items, but then arrived at the conclusion that the customer who spends $10,000 is a better customer.

Results won't be back until March.
