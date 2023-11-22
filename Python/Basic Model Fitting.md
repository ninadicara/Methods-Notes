
Usually...
- `X` = features
- `y` = prediction target
- `model.fit(X, y)` to fit your model.

To get a training and validation set...
```Python
from sklearn.model_selection import train_test_split

# Split up the data
train_X, test_X, train_y, test_y = train_test_split(X, y, random_state=??)

# Fit a model on the training data
model = DecisionTreeRegressor()  # For example
model.fit(train_X, train_y)

# Validate the model
predictions = model.predict(test_X)
mean_absolute_error(test_y, predictions)  # Using MAE as an example here

```

---
These notes are from the #Kaggle Learn platform. 
October 2023. 


