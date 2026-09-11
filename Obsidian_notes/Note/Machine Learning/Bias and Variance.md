
### Bias
*bias is the error ccaused because the model is too simple, The model is simply not powerful enough to understand the actual pattern*
#### High bias means:

- Model is too simple
- Important patterns aren't learned
- Training data isn't fitted properly
- Causes **underfitting**
- Training performance is poor
- Test performance is also usually poor

### Variance
*It Tells us how much the models prediction change when the traning data changes*
>it fits the traning data extremely closely 
>but when you give it new data it performs badly

#### High variance means:

- Model is too complex
- Learns noise
- Memorizes training data
- Causes **overfitting**
- Training accuracy is high
- Test accuracy is low
- Poor generalization


### Under Fitting
Underfitting happens when the model is too simple 
The model perdorms badly even on the traning data
`Hight Bias and low Variance`
### Over Fitting
It happens when the model becomes too complex and essentially memorize the traning data
```
Training accuracy = 99%
Testing accuracy  = 75%
```

### Bias-Variance Trade-off

**The bias-variance trade-off is the balance between model simplicity and model complexity to achieve the lowest possible prediction error and good generalization on unseen data.**
### Solutions for OverFitting

- **Regularization**
	- Regularization is a technique used to reduce overfitting by adding a penalty term to the loss function to control the complexity of a machine learning model
		- **Ridge Regression**
			- It is an L2 regularization technique that reduces model complexity by adding a penalty based on the squared value of the model coefficient 
		- **Lasso Regression**
			- It i an L1 Regularization techinque that reduces model complexity by adding a penalty based on the absolute values of the model coefficients
		- **Feature Selection**
			- Feature selection is the process of selecting the most relevant features for a model while eliminating irrelevant features.
- **Early stopping**
	- Early stopping is a regularization technique that stops the traning process before the model begins to overfit the traning data
- **More training data**
- **Data augmentation**
	- Data augmentation is the process of artificially modifying existing training data to create additional variations that resemble the variations expected in real-world data.
- **Dropout**
- Dropout is a regularization technique in which units or neurons of a neural network are randomly deactivated during training to reduce overfitting
- **Batch normalization**
	- Batch normalization is a technique that normalizes the activations of a neural network using the statistical properties of a batch, making training faster and more stable.
 `Generalization is the ability of a machine learning model to perform accurately on unseen data`
 