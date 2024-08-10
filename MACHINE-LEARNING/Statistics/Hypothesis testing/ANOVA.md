#### **What is this?**

ANOVA (Analysis of Variance) is a statistical method used to compare the means of three or more independent groups to determine if at least one group mean is significantly different from the others. It extends the t-test to multiple groups.

#### **When to use?**

Use ANOVA when you have three or more independent groups and want to test whether there is a statistically significant difference in their means.

#### **Real-Life Problem Statement**

Imagine a researcher wants to test if different diets have an effect on weight loss. The researcher divides participants into three groups, each following a different diet plan: Diet A, Diet B, and Diet C. After 12 weeks, the researcher records the weight loss for each participant and wants to know if there is a significant difference in the average weight loss across the three diet plans.

# In Python

\import scipy.stats as stats
import pandas as pd

# Sample data
data = {'Diet': ['A', 'A', 'A', 'B', 'B', 'B', 'C', 'C', 'C'],
        'WeightLoss': [4, 5, 3, 2, 3, 1, 6, 7, 5]}

df = pd.DataFrame(data)

# Perform ANOVA
anova_result = stats.f_oneway(df[df['Diet'] == 'A']['WeightLoss'],
                              df[df['Diet'] == 'B']['WeightLoss'],
                              df[df['Diet'] == 'C']['WeightLoss'])

# Results
print(f"F-statistic: {anova_result.statistic}, p-value: {anova_result.pvalue}")

# Interpretation
alpha = 0.05
if anova_result.pvalue < alpha:
    print("Reject the null hypothesis: At least one diet plan leads to a significantly different average weight loss.")
else:
    print("Fail to reject the null hypothesis: There is no significant difference in average weight loss among the diet plans.")

- **Null Hypothesis (H0​)**: The means of all groups are equal.
- **Alternative Hypothesis (H1​)**: At least one group mean is different.