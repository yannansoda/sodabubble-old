[[Machine Learning]]
![](svm_1.png)

# Support Vector
- Support vectors are the ones outside the tube (SVR) or exactly at the maximum margin (SVM)
- Support vectors are so called, because they support the structure or formation of the epsilon-insensitive tube or the maximum margin

# Support Vector Regression  (SVR)
=> performs regression, continuous data

## Kernels SVR
![](svm_2.png)

# Support Vector Machine (SVM)
=> performs classification, discrete data

## Kernels SVM
### Why we need kernels
classification can be non-linear
=> mapping to a higher dimension can help
![](svm_3.png)]]
=> however, the mapping can be highly compute-intensive
=> the Kernel trick can help with that
![](svm_4.png)
More than one kernel can be good too...
![](svm_5.png)

### Types of Kernel Functions
- Gaussian RBF kernel
- Sigmoid Kernel
- Polynomial Kernel
