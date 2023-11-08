
## `loc` vs `iloc`

Both are [row, column]. 

`iloc` finds values based on their index value. 
`loc` finds values based on their index labels. 

Remember if using index notation with loc that it will return the range inclusive of both ends. So:
- `iloc(0:100)` will return 100 numbers, 0 to 99.
- `loc(0:100)` will return 101 numbers, 0 to 100.

## `map()` and `apply()`

A **map** takes a function, which should expect a *single value* from a Series.
It returns a new Series with transformed values. 
e.g. To add 3 to every value of the column. 
- `df.column.map(lambda x: x + 3)` 
If using a custom function, you can just state the function name, no need to pass arguments.

**Apply** will transform the whole DataFrame by calling a custom method on each row. 
It can also act on columns. This depends on the `axis` argument.
e.g. 
```
def calculate(row): 
	row.col1 = row.col1 - row.col2
	return row

df.apply(calculate, axis='columns')
```

Remember...
- `axis = columns` transforms rows
- `axis = rows` transforms columns

## `groupby()` and `agg()`

To operate on a group:

`df.groupby('column').column.count()` 

Here, `count()` could be replaced by any summary function like `min()`

You can think of each group being a slice of the main dataframe containing only data with values that match. This means we can use apply on these mini-dataframes.
e.g.
`df.groupby('col1').apply(lambda data: data.col2.iloc[0])`
This will give a column of the unique values in col1, and a second column that gives the first value in col2 for each of the col1 mini-dataframes.

This also works with group-by on more than one column. 
`df.groupby(['col1, 'col2']).apply(lambda data:data.loc[data.col3.idxmax()])`
This will pick the top value for a dataframe grouped by col1 and col2. 

## Missing values

- Missing values are `NaN` and are always `float64`
- Can use `pd.isnull()` or `pd.notnull()`
	- e.g. `df[pd.isnull(df.col1)]` 
- Can fill NaN values using `fillna()`
	- e.g. `df.col1.fillna('Unknown')`
- Can replace values with `replace()`
	- e.g. `df.col1.replace("Old", "New")`

If you need to deal with missing values then check out [[Imputation]].
## `merge()`,`concat()`,  and `join()`

Merge and Join are very similar - it's usually easier to just use Join. 
Concat is easiest. 

`pd.concat([datasettop, datasetbottom])` 
This will put them 'on top' of eachother. 

If they have an index in common then you need `join()`

```
left = dataset1.set_index(['common_index_name'])
right = dataset2.set_index(['common_index_name'])

left.join(right, lsuffix='df1_', rsuffix='df2_')
```



---
Notes based on Kaggle Learn - Pandas course. 
24.10.2023