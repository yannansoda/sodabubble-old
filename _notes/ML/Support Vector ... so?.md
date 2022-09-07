![[Pasted image 20220206183628.png]]

# Support Vector
- Support vectors are the ones outside the tube (SVR) or exactly at the maximum margin (SVM)
- Support vectors are so called, because they support the structure or formation of the epsilon-insensitive tube or the maximum margin

# Support Vector Regression  (SVR)
=> performs regression, continuous data

## Kernels SVR
![[Screenshot 2022-02-26 at 18.58.04 (2).png]]

# Support Vector Machine (SVM)
=> performs classification, discrete data

## Kernels SVM
### Why we need kernels
classification can be non-linear
=> mapping to a higher dimension can help
![[Screenshot 2022-02-26 at 18.43.41 (2).png]]
=> however, the mapping can be highly compute-intensive
=> the Kernel trick can help with that
![[Screenshot 2022-02-26 at 18.40.15 (2).png]]
More than one kernel can be good too...
![[Screenshot 2022-02-26 at 18.40.52 (2).png]]

### Types of Kernel Functions
- Gaussian RBF kernel
- Sigmoid Kernel
- Polynomial Kernel
