---
title: 'Part 1.2 Data Structures'
description: '1.2 Data Structures'
attachments:
    slides_link: 'https://s3.amazonaws.com/assets.datacamp.com/production/course_22747/slides/chapter4.pdf'
---

## Structured data Vs. Unstructured data

```yaml
type: VideoExercise
key: 05f3df0746
xp: 50
```

`@projector_key`
3a21c6a1d317e3917885b7431572340e

---

## Structure Data Hands On

```yaml
type: VideoExercise
key: d61e4ccfe2
xp: 50
```

`@projector_key`
e6d8cb31d9e16a777247bb8009140d95

---

## Read data from csv

```yaml
type: NormalExercise
key: 9a65cbb6c1
xp: 100
```

<!-- Guidelines for contexts: https://instructor-support.datacamp.com/en/articles/2375526-course-coding-exercises. -->

`@instructions`
Your goal in this exercise
- read the data from a csv file 
- save the file as a json 
- read the json file and print the first line 

We attach a code sample of how to read the file as a text file
Please note that it will be easier to read the file using the pandas method: read_csv()

`@hint`
<!-- Examples of good hints: https://instructor-support.datacamp.com/en/articles/2379164-hints-best-practices. -->
- read the file using the command: df = pd.read_csv()
- don't forget to import pandas before
- save the data frame to json by using the command: df.to_json('my_file_name.json')

`@pre_exercise_code`
```{python}
csv_file = 'https://assets.datacamp.com/production/repositories/5503/datasets/271580220b9d9f5d16bd1b56fb6eff6be522ac9a/csv_data_100.csv'

```

`@sample_code`
```{python}
with file open(csv_file,'r') as f:
  print(f.readline())
```

`@solution`
```{python}

```

`@sct`
```{python}
# Examples of good success messages: https://instructor-support.datacamp.com/en/articles/2299773-exercise-success-messages.
```
