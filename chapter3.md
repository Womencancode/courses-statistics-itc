---
title: 'Part 1.1 Data Types'
description: 'Part 1.1 Data Types'
---

## Part 1.1 Data Types

```yaml
type: VideoExercise
key: b5f571cb6d
xp: 50
```

`@projector_key`
46ce39bf7d91104f28c21a7b488b985e

---

## Types of variables: Quantitative Or Qualitative 

```yaml
type: DragAndDropExercise
key: 424413adea
xp: 100
```

<!-- Guidelines for contexts: https://instructor-support.datacamp.com/en/articles/2375526-course-coding-exercises. -->

`@instructions`
<!-- Guidelines for instructions https://instructor-support.datacamp.com/en/articles/2375526-course-coding-exercises. -->
Classify the variables

`@hint`
<!-- Examples of good hints: https://instructor-support.datacamp.com/en/articles/2379164-hints-best-practices. -->
- Quantitative variables are numbers
  - Continuous variables have a meaningful value between any two values
  - Discrete variables have values that are "next to each other" without any meaningful value in the middle
- Categorical variables may be represented by numbers, but can just as easily be represented by other means
  - Ordinal variables have a natural order. 
  - Nominal variables can only be checked for equality or lack thereof.

`@solution`
```{python}
# Edit or remove this code to create your own exercise.
# This is 1 type of drag and drop exercise, there are 2 other types. See documentation:
# http://instructor-support.datacamp.com/en/articles/3039539-course-drag-drop-exercises

# Make sure you only use SPACES, NOT TABS in front of each line.

# Drag zone that holds all the options.
# Specify an ID for this zone to use in SCTs.
- id: variables
  title: "Variables" # Title of your zone This is not shown with more than 2 zones.

- id: quant_cont
  title: "Quantitative Continuous"
  items: # Each drop zone has a list of items it contains. These will be shown in a random fashion.
    - content: "Height in meters" # Name of an item. Feel free to use markdown.
      id: height_m # ID of the item. This can be used in the SCTs.
    - content: "Height in feet"
      id: height_ft

- id: quant_disc
  title: "Quantitative Discrete"
  items:
    - content: "Height in meters, when stored on computer"
      id: height_comp
    - content: "Price of tea in a specific store in Beijing, in Yuan"
      id: tea_china
      
- id: cat_ordinal
  title: "Categorical Ordinal"
  items:
    - content: "Rank in the military"
      id: rank
    - content: "Letter grade"
      id: grade
      
- id: cat_nominal
  title: "Categorical Nominal"
  items:
    - content: "Country name"
      id: country
    - content: "Name of currency"
      id: currency
```

`@sct`
```{python}
checks: # Individual checks and custom messages per item. This is optional. Without it, it will check that the options are as in the solution code.
  - condition: check_target(pandas) == dropzone_python # Check that pandas is in dropzone_python.
    incorrectMessage: 'Hmm! Pandas is a Python package.' # If that condition is not true, show this message.
  - condition: check_target(numpy) == dropzone_python
    incorrectMessage: 'Damn, this is far from perfect!'
  - condition: check_target(dplyr) == dropzone_r
    incorrectMessage: "Hmm, keep doing R courses! :-)"
  - condition: check_target(stringr) == dropzone_r
    incorrectMessage: "How funny if stringr would be a Python package."
successMessage: "Congratulations" # Message shown when all is correct.
failureMessage: "Try again!" # Message shown when there are errors (and there is no specific error available).
isOrdered: false # Should the items in the zones be ordered as in the solution code?
```

---

## Interval Vs. Ratio

```yaml
type: DragAndDropExercise
key: 6322b6474c
xp: 100
```

<!-- Guidelines for contexts: https://instructor-support.datacamp.com/en/articles/2375526-course-coding-exercises. -->

`@instructions`
<!-- Guidelines for instructions https://instructor-support.datacamp.com/en/articles/2375526-course-coding-exercises. -->
Classify the variables between Internal vs. Ratio

`@hint`
- Ratio variables can be divided (A is twice as heavy as B, so weight is a ratio variable)
- Interval variables cannot be divided, but can be subtracted (such as the output of `new Date().getTime()` in JavaScript)
- Categorical variables cannot even be subtracted

`@solution`
```{python}

# Drag zone that holds all the options.
# Specify an ID for this zone to use in SCTs.
- id: variables
  title: "Variables" # Title of your zone This is not shown with more than 2 zones.

- id: ratio
  title: "Ratio"
  items: # Each drop zone has a list of items it contains. These will be shown in a random fashion.
    - content: "Height in meters" # Name of an item. Feel free to use markdown.
      id: height_m # ID of the item. This can be used in the SCTs.
    - content: "Height in feet"
      id: height_ft

- id: interval
  title: "Interval"
  items:
    - content: "Temperature in Centrigrade"
      id: temp_c
    - content: "Year that a country gained independence"
      id: year
      
- id: categorical
  title: "Categorical (Nominal or Ordinal)"
  items:
    - content: "[Country by population rank](https://www.cia.gov/library/publications/the-world-factbook/fields/335rank.html) (China first, then India, etc.)"
      id: pop_rank
```

`@sct`
```{python}
checks: # Individual checks and custom messages per item. This is optional. Without it, it will check that the options are as in the solution code.
  - condition: check_target(height_m) == ratio 
    incorrectMessage: "You can meaningfully say that somebody is twice as high as somebody else"
  - condition: check_target(height_ft) == ratio 
    incorrectMessage: "You can meaningfully say that somebody is twice as high as somebody else"
  - condition: check_target(temp_c) == interval 
    incorrectMessage: "There is no meaningful zero in centigrade, so it is an interval variable"
  - condition: check_target(year) == interval 
    incorrectMessage: "There is no meaningful year zero, so it is an interval variable"    
  - condition: check_target(pop_rank) == categorical 
    incorrectMessage: "Subtraction is meaningless, the difference between the US and India is not the same as the difference between India and China"    
successMessage: "Congratulations" # Message shown when all is correct.
failureMessage: "Try again!" # Message shown when there are errors (and there is no specific error available).
isOrdered: false # Should the items in the zones be ordered as in the solution code?
```
