[[_Machine Learning]]
# How it works
![[Pasted image 20220501132303.png]]
1. Convolution operation
![[Pasted image 20220501115845.png]]
>- stride = the moving step size of the feature detector: usually 2
>- feature detector = kernel = filter :usually 3x3, but other models such as AlexNet use 7x7
2. Pooling
Pooling(=down-sampling) can reduces features and is more robust to overfitting.
![[Pasted image 20220501130422.png]]

types: max pooling, aum Pooling, Avg Pooling(~subsampling)
3. Flattening
![[Pasted image 20220501130437.png]]
4. Full connection 
The flattened vectors are propagated into an ANN as the input layer
![[Pasted image 20220501131745.png]]