# Parameter Optimization for SVM
---
## Methodology

We selected a multi-class dataset (Dry Bean Dataset) from the UCI repository with a size of 13,611 rows.

Here is the sample of Dataset:
<img src="static\dataset.png">

The dataset was split using a stratified 70-30 train-test ratio across 10 different random samples to ensure consistent class distribution.

For each sample, we ran 100 iterations of hyperparameter search to optimize the Support Vector Machine (SVM) classifier. The parameters tuned included:

- **Kernel**: linear, poly, rbf, sigmoid
- **C**: Regularization parameter - [0.1,1,10,100]
- **Gamma**: Kernel coefficient
- **Degree**: [2, 3, 4] if kernel is "poly" else 3

The optimization loop retained the best accuracy along with the corresponding hyperparameters. We also logged the accuracy for each iteration to visualize convergence.

## Results Table

Below is the comparative performance of Optimized-SVM for 10 samples.
| Sample | Best Accuracy | Kernel |   C  | Gamma | Degree |
|--------|----------------|--------|------|--------|--------|
| S1     | 0.934133       | rbf    | 100  | 0.01   | 3      |
| S2     | 0.934378       | rbf    | 10   | 0.1    | 3      |
| S3     | 0.937071       | rbf    | 10   | scale  | 3      |
| S4     | 0.929726       | rbf    | 100  | scale  | 3      |
| S5     | 0.931195       | rbf    | 100  | 0.01   | 3      |
| S6     | 0.941234       | rbf    | 100  | 0.01   | 3      |
| S7     | 0.932174       | rbf    | 10   | 0.1    | 3      |
| S8     | 0.933154       | rbf    | 100  | scale  | 3      |
| S9     | 0.931929       | rbf    | 100  | 0.01   | 3      |
| S10    | 0.931440       | rbf    | 10   | 0.1    | 3      |


## Convergence Graph for Best Sample

The following graph shows how the accuracy evolved over the iterations for the best performing sample (Sample 6).

<img src="static\Convergence graph.png" width = 70% height = 70%>


