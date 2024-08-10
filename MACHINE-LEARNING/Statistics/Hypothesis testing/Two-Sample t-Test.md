#### **What is this?**

The two-sample t-test compares the means of two independent samples to determine if they are significantly different from each other.

#### **When to use?**

Use this test when you have two independent samples and want to compare their means.

#### **Real-Life Problem Statement**

You want to compare the average test scores of students from two different classes to see if one class performs significantly better than the other.

# In Python

import scipy.stats as stats

# Sample data
class_A_scores = [85, 88, 90, 91, 87, 86, 84, 90, 88, 89]
class_B_scores = [78, 82, 80, 79, 77, 81, 76, 80, 83, 78]

# Perform two-sample t-test
t_statistic, p_value = stats.ttest_ind(class_A_scores, class_B_scores)

# Results
print(f"t-statistic: {t_statistic}, p-value: {p_value}")

# Interpretation
alpha = 0.05
if p_value < alpha:
    print("Reject the null hypothesis: There is a significant difference in the average test scores of the two classes.")
else:
    print("Fail to reject the null hypothesis: There is no significant difference in the average test scores of the two classes.")

- **Null Hypothesis (HO​)**: The mean scores of Class A and Class B are equal.
- **Alternative Hypothesis (H1​)**: The mean scores of Class A and Class B are not equal.