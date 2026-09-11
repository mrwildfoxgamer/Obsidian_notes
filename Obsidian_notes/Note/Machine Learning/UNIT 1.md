## Types of Machine Learning
- Supervised Learning
	- The model is trained on supervised learning 
	- The training data contains both input and output
	- The Goal is to find a mapping function f That can accurately predict the output y for new and unseen data `y=f(x)`
	- Eg :
		- Regression
		- Classification
			- K nearest neighbor KNN
			- Support Vector Machines SVM
			- Decision Tree
			- Random Forest
			- Artificial Neural Network
- Unsupervised Learning
	- The data is not labeled categorized or annotated
	- The model is trained to find and discover hidden patterns,underlying structures or natural grouping entirely on its own
	- Eg:
		- Clustering
		- Association Rule Mining
		- Dimensionality reduction
- Reinforcement Learning 
	- Learning by trial and error ,Reinforcement Learning is when a computer learns what to do by trying different actions and learning from rewards and penalties.
	- The dataset is created by the Agent
- Semi Supervised Learning 
	- It is a traning method which uses both labled and unlabled data to train a model used when labled data is rare and unlabled data is plenty
	- The model is trained using the labled data and Model predicts labels for the unlabled data 

## Steps in developing a Learning system
- Problem formulation and data collection
- Data preprocessing and feature Engineering
- Data splitting
- Model selection and Traning
- Evaluation and Diagostics 

## Regression
*It it a superviced learning techinique used to model the relationship between input variables and a continuos output variables*
**Dependent variable** - Outcome or responce variable
**Indipendent variable** - Predicators,covariates,explantory variables ,features 


## Types of Regressions
#### Linear Regression
*It is used to predict dependent varibale y beased on the values of indipendent variable x*
- Simple linear Regression or Multivariant Linear Regression
	- only one indipendent variable
- Multiple linear Regression or multivariant linear Regression
	- more that one indepenedent variable
	
#### Non linear Regression
- used in complex dataset where Dependent and independed variables show non-linear relationship

### Cost / Loss Function
- A **cost function or loss function** is used in machine learning to measure **how different the model's prediction is from the actual value**.
- It measures how far an estimated value is from its true value if the predictions deviates too much from actual results loss function will be very large

### Assumptions  of linear Regrestion
1. Linear Relationship
	- The relationship between the indipendent variable x and dependent variable y should be approximately a stright line relationship
2. Indipendance
	- one observation should not dependet on another observation
3. Normality
	- The errors/residuals of the regression should approximatley follow a normal distribution
4. No Multicollinearity
	- The independent variable should be highly correlated with each other
5. No Autocorrelation
	- The current error/values is related to a previous error/values
6. Homoscedasticity
	* The spread of the error should  remain roughly constant accross different values of x 

|Assumption|Simple meaning|Example of problem|
|---|---|---|
|**Linear relationship**|X and Y should have roughly a straight-line relationship|Curved relationship|
|**Independence**|Observations shouldn't depend on each other|One observation affects another|
|**Normality**|Errors/residuals should be roughly normally distributed|Errors have a very unusual distribution|
|**No multicollinearity**|X variables shouldn't be highly related to each other|Age and years of experience|
|**No autocorrelation**|Errors shouldn't be related across time|Today's error related to yesterday's|
|**Homoscedasticity**|Error spread should remain roughly constant|Errors become increasingly spread out|

## Geadient Descent Algorithm
**It is an optimization algorithm used to minimize the error of a machine learning model by updating the model parameters**
*IT finds the best-fit solution with minimal loss for a given traning dataset in a smaller number of iterations*

`Gradient is the reate of change of the cost with respect to the model parameters it tells us Direction to move and how steel the slop is`
`It it the derivatve of the loss function with respect to the model paramerts`
+ve gradiant -> Move left
-ve gradiant -> Move right

### Algorithm
Sure. Without mathematical notation, the **Gradient Descent algorithm** can be written like this:

### Gradient Descent Algorithm

1. **Initialize the parameters** with some starting values, usually zero or random values.
    
2. **Choose a learning rate** — this controls how large each update will be.
    
3. **Make predictions** using the current parameter values.
    
4. **Calculate the error** between the predicted values and the actual values.
    
5. **Find the direction in which the error increases the most.**
    
6. **Update the parameters in the opposite direction** so that the error decreases.
    
7. **Repeat steps 3–6** until the error becomes small enough or the maximum number of iterations is reached.
    
8. **Return the final parameter values.**

### Learning rate
>It decides how big a step Gradient descent takes each time it updates the model
>
>If the learning rate is too large Its called Overshooting  If the learning rate is extremely large, Gradient Descent might **never reach the minimum** and can even **diverge**, meaning the error keeps getting larger
>
>If the learning rate is too small You will eventually reach the bottom, but it can take a **very long time**.

### The ideal learning rate

You want a learning rate that is **large enough to learn quickly but small enough that you don't overshoot the minimum**.


