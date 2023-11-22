
## Mean imputation

If we're doing some [[Basic Model Fitting]] then mean imputation usually performs well enough. 
More complex imputation doesn't make a big improvement for these. 

### Pandas solution 

This is the fastest way to fill in a large dataset. [Thanks Stack Overflow!](https://stackoverflow.com/questions/18689823/pandas-dataframe-replace-nan-values-with-average-of-columns)

```Python
#---Applying Only on variables with NaN values
for i in df.columns[df.isnull().any(axis=0)]:     
    df[i].fillna(df[i].mean(),inplace=True)
```

### sklearn

To replace each of the missing values with the column mean:

```Python
from sklearn.impute import SimpleImputer

# Imputation
my_imputer = SimpleImputer()
imputed_X_train = pd.DataFrame(my_imputer.fit_transform(X_train))
imputed_X_valid = pd.DataFrame(my_imputer.transform(X_valid))

# Imputation removed column names; put them back
imputed_X_train.columns = X_train.columns
imputed_X_valid.columns = X_valid.columns

```
%% This code  is from the #Kaggle Intermediate ML Course. %%


## Multiple Imputation by Chained Equations (MICE)

Imputes one column by creating a regression equation using the rest of the input columns as independent variables. It does this for each column in turn, and can be iterated multiple times.