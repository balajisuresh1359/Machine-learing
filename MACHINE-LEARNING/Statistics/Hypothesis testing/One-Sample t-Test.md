#### **What is this?**

The one-sample t-test is used to determine whether the mean of a single sample is significantly different from a known or hypothesized population mean.

#### **When to use?**

Use this test when you have one sample and want to compare its mean to a known or hypothesized population mean.

#### **Real-Life Problem Statement**

Imagine you work at a factory that produces light bulbs. The factory claims that the average lifetime of a light bulb is 1000 hours. You take a random sample of 30 light bulbs and want to test if the average lifetime of light bulbs produced by your factory is indeed 1000 hours.

# In Python


import scipy.stats as stats

# Sample data
sample_lifetimes = [980, 995, 1001, 1020, 990, 1005, 1002, 998, 1003, 1010,
                    1008, 999, 995, 1004, 1007, 1002, 1015, 1005, 1000, 1001,
                    995, 997, 1006, 1003, 1004, 1009, 996, 1000, 1003, 1002]

# Perform one-sample t-test
t_statistic, p_value = stats.ttest_1samp(sample_lifetimes, popmean=1000)

# Results
print(f"t-statistic: {t_statistic}, p-value: {p_value}")

# Interpretation
alpha = 0.05
if p_value < alpha:
    print("Reject the null hypothesis: The average lifetime of the light bulbs is not 1000 hours.")
else:
    print("Fail to reject the null hypothesis: The average lifetime of the light bulbs is 1000 hours.")



- **Null Hypothesis (H0)**: The mean lifetime of light bulbs is 1000 hours.
- **Alternative Hypothesis (H1​)**: The mean lifetime of light bulbs is not 1000 hours.
