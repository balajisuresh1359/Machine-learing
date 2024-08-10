#### **What is this?**

The paired t-test compares the means of two related groups. This test is used when the samples are not independent, such as measurements taken before and after a treatment on the same subjects.

#### **When to use?**

Use this test when you have paired or matched samples, like pre-test and post-test scores of the same group of individuals.

#### **Real-Life Problem Statement**

You are testing the effectiveness of a new training program. You measure the productivity of 15 employees before and after the training and want to know if the training had a significant impact.

# In Python

import scipy.stats as stats

# Sample data
before_training = [50, 55, 53, 52, 54, 58, 57, 56, 59, 60, 61, 55, 56, 54, 53]
after_training = [65, 66, 64, 63, 67, 69, 68, 66, 70, 71, 72, 68, 67, 65, 66]

# Perform paired t-test
t_statistic, p_value = stats.ttest_rel(before_training, after_training)

# Results
print(f"t-statistic: {t_statistic}, p-value: {p_value}")

# Interpretation
alpha = 0.05
if p_value < alpha:
    print("Reject the null hypothesis: The training program had a significant impact on productivity.")
else:
    print("Fail to reject the null hypothesis: The training program did not have a significant impact on productivity.")


- **Null Hypothesis (H0​)**: The mean difference between before and after training is zero.
- **Alternative Hypothesis (H1​)**: The mean difference between before and after training is not zero.