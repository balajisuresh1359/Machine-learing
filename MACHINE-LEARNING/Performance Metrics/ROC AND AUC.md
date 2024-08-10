[ROC AND AUC CURVE](https://youtu.be/A_ZKMsZ3f3o?feature=shared)

# ROC (Receiver Operating Characteristic) Curve

	- The ROC curve is a graphical representation of a classification model's performance, showing the trade-off between the true positive rate (sensitivity) and the false positive rate (1-specificity) at various threshold settings.

# **AUC (Area Under the Curve)**: 
	AUC is a single scalar value that summarizes the overall performance of a classification model by measuring the entire two-dimensional area under the ROC curve. A higher AUC indicates better model performance.

	The AUC is calculated by integrating the ROC curve over all possible thresholds. It represents the probability that a randomly chosen positive instance is ranked higher than a randomly chosen negative instance by the classifier.

-  **AUC Values**:
        - 0.5: Model has no discrimination ability (random guess).
        - 1.0: Model has perfect discrimination ability.
        - AUC values between 0.5 and 1.0 indicate varying degrees of model performance.


Use ROC and AUC when evaluating the performance of a binary classification model, especially when dealing with imbalanced datasets.

#### **Real-Life Problem Statement**

Consider a medical diagnostic test used to identify a certain disease (e.g., diabetes). The test outputs a probability score for each patient, and based on a threshold, patients are classified as either "diseased" or "not diseased." The goal is to evaluate how well the test performs in distinguishing between patients with and without the disease.

import numpy as np
from sklearn.metrics import roc_curve, auc
import matplotlib.pyplot as plt

# Example data: predicted probabilities and true labels
y_true = np.array([0, 0, 1, 1, 0, 1, 0, 0, 1, 1])  # True labels (0 = no disease, 1 = disease)
y_scores = np.array([0.1, 0.4, 0.35, 0.8, 0.2, 0.7, 0.3, 0.4, 0.65, 0.85])  # Predicted probabilities

# Calculate ROC curve
fpr, tpr, thresholds = roc_curve(y_true, y_scores)

# Calculate AUC
roc_auc = auc(fpr, tpr)

# Plot ROC curve
plt.figure()
plt.plot(fpr, tpr, color='blue', lw=2, label=f'ROC curve (AUC = {roc_auc:.2f})')
plt.plot([0, 1], [0, 1], color='gray', lw=2, linestyle='--')
plt.xlim([0.0, 1.0])
plt.ylim([0.0, 1.0])
plt.xlabel('False Positive Rate')
plt.ylabel('True Positive Rate')
plt.title('Receiver Operating Characteristic')
plt.legend(loc="lower right")
plt.show()

# Results
print(f"AUC: {roc_auc:.2f}")



![[IMG - AUC-ROC.png]]