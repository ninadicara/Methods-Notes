
These are a type of [[Ensemble Learning]], specifically of Bagging. 

Random Forests use [[Bootstrapping]] to train each tree on a different sample of the original dataset. 
Not only do they bootstrap observations to train on, but they can also bootstrap the training features, so they are training on a subset of the data in terms of rows and columns. 

This has the effect of reducing the correlation between the different outputs from each tree and making the outputs more robust.

## Implementation - Python


```Python
from sklearn.ensemble import RandomForestRegressor
from sklearn.metrics import mean_absolute_error

forest_model = RandomForestRegressor(random_state=1)
forest_model.fit(train_X, train_y)
melb_preds = forest_model.predict(val_X)
print(mean_absolute_error(val_y, melb_preds))
```


## Gini Index

Varies between 0 and 1, where 0 expresses purity of classification (i.e. everything ended up in one class) and 1 indicates elements randomly distributed across various classes. 
0.5 indicates an equal distribution of elements over some classes. 

When designing a decision tree, the features with the smallest Gini Index would be preferred.

--- 

[Ensemble methods: bagging, boosting and stacking - Towards Data Science](https://towardsdatascience.com/ensemble-methods-bagging-boosting-and-stacking-c9214a10a205)