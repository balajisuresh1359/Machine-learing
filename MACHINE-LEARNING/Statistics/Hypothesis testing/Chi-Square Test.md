#### **What is this?**

The chi-square test is used to determine if there is a significant association between two categorical variables.

#### **When to use?**

Use this test when you want to see if there’s a relationship between two categorical variables in a contingency table.

#### **Real-Life Problem Statement**

A company wants to know if there’s a relationship between the department employees work in (HR, IT, Sales) and their job satisfaction level (Satisfied, Unsatisfied).

import scipy.stats as stats
import pandas as pd

# In Python
# Sample data
data = {'Department': ['HR', 'HR', 'HR', 'IT', 'IT', 'IT', 'Sales', 'Sales', 'Sales'],
        'Satisfaction': ['Satisfied', 'Unsatisfied', 'Satisfied', 'Satisfied', 'Unsatisfied', 'Unsatisfied', 'Satisfied', 'Unsatisfied', 'Satisfied']}

df = pd.DataFrame(data)
contingency_table = pd.crosstab(df['Department'], df['Satisfaction'])

# Perform chi-square test
chi2, p, dof, expected = stats.chi2_contingency(contingency_table)

# Results
print(f"Chi-square statistic: {chi2}, p-value: {p}")

# Interpretation
alpha = 0.05
if p < alpha:
    print("Reject the null hypothesis: There is a significant association between the department and job satisfaction.")
else:
    print("Fail to reject the null hypothesis: There is no significant association between the department and job satisfaction.")


- **Null Hypothesis (H0​)**: There is no association between the two categorical variables (independence).
- **Alternative Hypothesis (H1​)**: There is an association between the two categorical variables (dependence).
