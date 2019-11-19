---
title: 'Additional Exercises'
description: 'Additional Exercises'
---

## Copy of Copy of Ploting Categorical Data

```yaml
type: NormalExercise
key: 2a00f7e911
xp: 100
```

<!-- Guidelines for contexts: https://instructor-support.datacamp.com/en/articles/2375526-course-coding-exercises. -->

`@instructions`
- The starting code will load a csv file containing data about housing prices 
  (https://www.kaggle.com/c/house-prices-advanced-regression-techniques)
  After reading the file it print out the columns and a sample of a single data point
- Choose one of the columns that contains categorical data
- Count the frequency of each of the categories ( you can use dataframe method: value_counts())
- Normalize it to represent the frequency in percentage 
- Plot as a pie chart ( you can yous the dataframe method .plot.pie() )

`@hint`
<!-- Examples of good hints: https://instructor-support.datacamp.com/en/articles/2379164-hints-best-practices. -->
- This is an example hint.
- This is an example hint.

`@pre_exercise_code`
```{python}
data_file = 'https://assets.datacamp.com/production/repositories/5503/datasets/fa19780a7b011d9b009e8bff8e99922a8ee2eb90/housing_prices_data.csv'
```

`@sample_code`
```{python}
import pandas as pd
import matplotlib.pyplot as plt
%matplotlib inline

df = pd.read_csv( data_file )
print(df.columns)
print(df.iloc[0])
```

`@solution`
```{python}

```

`@sct`
```{python}
# Examples of good success messages: https://instructor-support.datacamp.com/en/articles/2299773-exercise-success-messages.
```
