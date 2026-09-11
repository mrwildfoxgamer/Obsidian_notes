Logistic Regression is a statistical model used for classification and predictive analysis when the dependent variable is categorical. It estimates the probability of an event occurring based on one or more independent variables.

### Binary Classification

Binary classification is a classification problem in which the dependent variable has only two possible outcomes, usually represented as 0 and 1.

### Sigmoid Function

**The sigmoid function is a mathematical function used in logistic regression to transform a real-valued input into a value between 0 and 1, representing the probability of an outcome**

### Threshold Value

**A threshold value is a predetermined probability value used to convert the predicted probability into a categorical class such as 0 or 1.**

### Logit Function

**The logit function is the natural logarithm of the odds of an event, where odds are defined as the probability of success divided by the probability of failure.**

### Odds

**Odds are the ratio of the probability of an event occurring to the probability of the event not occurring.**

### Maximum Likelihood Estimation (MLE)

**Maximum Likelihood Estimation is a method used to estimate the parameters of a logistic regression model by finding parameter values that maximize the likelihood of observing the given data.**

### Logistic Regression Equation

The logistic regression first calculates a linear combination of the input variables:

```
z = b₀ + b₁x₁ + b₂x₂ + ... + bₙxₙ
```

Then the sigmoid function converts this value into a probability:

```
P(Y = 1) = 1 / (1 + e⁻ᶻ)
```
### Dependent Variable

**The dependent variable is the target variable that the model attempts to predict. In logistic regression, it is categorical and, in binary logistic regression, takes the values 0 or 1.**

### Independent Variable

**An independent variable is an input feature used by the logistic regression model to predict the probability of the dependent variable.**

### Bias / Intercept

**The bias term, also called the intercept, is the constant term in the logistic regression equation that represents the model's baseline value when the input variables are zero.**

### Weight / Coefficient

**A coefficient or weight represents the contribution of an independent variable to the logistic regression model.**

### Multiclass Classification

**Multiclass classification is a classification problem in which the target variable has more than two possible categories**


## Naive Bayes
It is a probabilistic classification algorithm that applies bays theorem with the assumption that features are independent 