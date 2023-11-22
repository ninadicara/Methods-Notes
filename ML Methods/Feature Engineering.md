A.K.A Feature Extraction 

This refers to the manipulation of your dataset to get it ready for model training. The benefits are: 
- Reducing overfitting
- Improving model accuracy/[[Evaluation Metrics]] in general
- Reducing training time

It is most useful if feature engineering is often informed by domain knowledge. 

## Dimensionality Reduction

If we have too many variables/features then the feature space will be too big, and very sparse. It is likely to result in a model that is inefficient to train and probably overfitted. 

Dimensionality reduction usually refers to creating new variables that reflect the combined information of several variables. Relevant techniques include:
- [[Principal Components Analysis]] 
- Linear Discriminant Analysis (LDA)
- t-SNE
- UMAP

## Feature Selection

![|500](https://machinelearningmastery.com/wp-content/uploads/2019/11/Overview-of-Feature-Selection-Techniques3.png)


Feature selection is also used when there are too many variables, but refers to choosing a subset of the most relevant variables. To do this you might use:
- [[Mutual Information]] to see which variables are most useful to keep.
- Feature importance methods - [[Ensemble Learning|Bagged]] [[Random Forests|Decision Trees]] like random forests and Extra Trees.
- Automated methods like `SelectKBest` with scikitlearn.
- Recursive Feature Elimination ([related to Backward Elimination](https://stats.stackexchange.com/questions/450518/rfe-vs-backward-elimination-is-there-a-difference), a type of stepwise regression) 

---

[Dimensionality Reduction vs Feature Selection by Ankit Sanjyal on Medium](https://medium.com/@asanjyal81/dimensionality-reduction-vs-feature-selection-e68f91aa8724)

[Feature Selection in Python](https://machinelearningmastery.com/feature-selection-machine-learning-python/)
[How to Choose a Feature Selection Method for Machine Learning](https://machinelearningmastery.com/feature-selection-with-real-and-categorical-data/)
