
Used to prevent over-fitting in machine learning models. 
It does this by introducing some _bias_ into the trained model so that it isn't overfitted to the training data, and therefore performs better for testing data.

There are two types of ridge regression, L1 and L2, also known as Ridge and Lasso. 
Combined these create Elastic Net regression.

## Which to use?

- Are most features in the dataset useful? -> Ridge
- Are there lots of potentially irrelevant features? -> Lasso
- Do you not know enough about variables to know if features are useful? -> Elastic Net
- Are your variables in lots of correlated groups? -> Elastic Net

## Things to know

> [!summary] 
> L1 Ridge modifies the over-fitted models by adding a _penalty_ to the cost function being minimised that is the square of the slope, multiplied by $\lambda$ which gives how harsh the penalty should be.
> 
> Whereas, L2 LASSO does the same but doesn't use the square of the slope, it just uses the magnitude of the slope. This allows it to push coefficients to zero.
> 
> Elastic Net contains the penalty functions for both L1 and L2 regression. It's particuarly good for large features spaces of correlated variables, or where you don't know much about your variables.

- $\lambda$ is known as the tuning parameter. 
- If $\lambda$ = 0 we are doing normal regression, because that would make the penalty term 0. 
- $\lambda$ has a range of 0 to + $\inf$
- As $\lambda$ increases the regression slope gets flatter, meaning that changes in the input variables result in less dramatic changes in the outcome. 
- The best value of $\lambda$ is determined using [[Cross-validation]] testing a range of potential values, and find the model with the lowest variance.

## Ridge Regularisation (L2)

### When to use
- This is useful to reduce sensitivity to new data that comes from **small sample sizes**.
- Keeps all variables in the model. 
- But relaxes the constraint that we need at least as many data points as features (e.g. in large genetic datasets with thousands of genes and only 500 participants). 
- Shrinks correlated variables together.
- Ridge regression can also be used for categorical features and logistic regression.
### How it works
The cost function is: 

> $Cost =$ `Sum of Squared Residuals` $+ (\lambda * slope^2)$ 

Here `Sum of Squares` is what is usually minimised for normal regression. 

$\lambda * slope^2$ is the added penalty function to create Ridge Regularisation where:
- $slope^2$ is the penalty we are adding, 
- $\lambda$ is how severe the penalty is. 

### Using in `sklearn`

```from sklearn import Ridge```
## LASSO Regularisation (L1)

### When to use 
- You've got lots of potentially irrelevant features. 
- Want a simpler and easier to interpret model (because some variables are removed). 

>[!warning] If you have lots of correlated variables then LASSO tends to only pick **one** of them. 
### How it works

> $Cost =$ `Sum of Squared Residuals` $+ (\lambda * abs(slope))$ 

When shrinking the coefficients, they don't have to be reduced equally. So, some variables can be pushed to zero, whilst others might remain.

Increasing $\lambda$ may be needed to get rid of most useless variables. 
Again, [[Cross-validation]] is used to tune this hyper-parameter. 

## Elastic Net

### When to use
- Best when you have features that operate in correlated groups (e.g. genetic or behavioural data). 
- Groups and shrinks correlated variables so it leaves them all in or removes them all together.
- When we have a model with millions of variables and no opportunity to investigate them all. 

### How it works

> $Cost =$ `Sum of Squared Residuals` $+ (\lambda_{1} * abs(slope))+ (\lambda_{2} * slope^2)$ 

(i.e. `Sum of Squared Residuals` + `L1/LASSO` + `L2/Ridge`)

Note that we have **two** different lambdas here. Again, we'd use cross validation to optimise them both. 


---
Resources:
- [Ridge (L2) Regression from StatQuest](https://www.youtube.com/watch?v=Q81RR3yKn30)
- [LASSO (L1) Regression from StatQuest](https://youtu.be/NGf0voTMlcs?si=3RijFJbCgI9mKRGv)
- [Elastic Net Regression from StatQuest](https://youtu.be/1dKRdX9bfIo?si=E7bVTXw0IohldbRd)

