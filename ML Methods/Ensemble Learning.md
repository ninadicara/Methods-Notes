Linked to #bagging and #boosting

So-called 'weak' learners are combined to create a 'strong' learner. 
Usually you combine several of the same type of model trained in different ways.
Typically if you use models with high variance, you combine them to create an ensemble that reduces overall variance. Same for bias. 

There are three main ways to combine weak learners: 
1. Bagging - making ensembles with less *variance* than their parts
2. Boosting - making ensembles with less *bias* than their parts
3. Stacking - making ensembles with less *bias* than their parts

## Bagging

Bagging stands for 'bootstrap aggregating'. See the statistical explanation of [[Bootstrapping]].

We can use the principles of bootstrapping to create multiple training datasets, fit a weak learner for each and then aggregate their outputs to obtain an ensemble model with less variance than its outputs. 

Averaging the weak learners in this way does not change the expected answer, but reduces the variance. It is a **parallel method** because each of the weak learners can be trained separately, in parallel. 

Ways to combine the outputs of the learners: 
- Regression: literal averaging of the outputs of interest
- Classification: 
	- Hard Voting - Class output by each model is a vote, and the class with the most votes 'wins'. 
	- Soft Voting - Consider the probabilities of each class returned by all models, average these probabilities and keep the class with the highest average probability. Can use weights if relevant. 

[[Random Forests]] are an example of bagging. 

## Boosting

This is a **sequential** method, where multiple models are fitted iteratively so that training the next model depends on the previous one. 
Because this method cannot be parallelised we tend to use it for models that are less computationally expensive to fit - i.e. few degrees of freedom. 

In each new model the idea is to learn from the mistakes made by previous classifiers. 

Examples of boosting models are [[AdaBoost]] and [[Gradient Boost]].
### Gradient Boost


---
[Ensemble methods: Bagging, Boosting and Stacking - Towards Data Science](https://towardsdatascience.com/ensemble-methods-bagging-boosting-and-stacking-c9214a10a205)