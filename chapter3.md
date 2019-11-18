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

```

`@sct`
```{python}
checks: # Individual checks and custom messages per item. This is optional. Without it, it will check that the options are as in the solution code.
  - condition: check_target(height_m) == quant_cont 
    incorrectMessage: "No, a physical quantity such as height is a continuous quantitative variable" 
  - condition: check_target(height_ft) == quant_cont 
    incorrectMessage: "No, a physical quantity such as height is a continuous quantitative variable"    
  - condition: check_target(height_comp) == quant_disc 
    incorrectMessage: "A value on a computer is always discrete. When you use n bits to store a value, you can only have 2^n distinct values."         
  - condition: check_target(tea_china) == quant_disc
    incorrectMessage: "A yuan is divided into 100 fen (similar to how a dollar is divided into a hundred cents), but as there are no coins smaller than one fen, the price would always be an integer number of fens. An integer number is a discrete quantity"
  - condition: check_target(rank) == cat_ordinal
    incorrectMessage: "Military ranks have an order. A general outranks a captain, which outranks a sergeant, which outranks a private"
  - condition: check_target(grade) == cat_ordinal
    incorrectMessage: "A letter grade of A is better than B, which is better than C, etc."
  - condition: check_target(currency) == cat_nominal
    incorrectMessage: "Names don't have an inherent order, so it is categorical nominal"
    
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

---

## Thinking exercise

```yaml
type: PureMultipleChoiceExercise
key: 3929158ea6
xp: 50
```

What variable type is the difference between two interval variables? For example, the change in temperature between one day and the next?

`@hint`
Interval variables can be meaningfully subtracted from each other, but not meaningfully divided, and there is no meaningful zero. Ratio variables have a meaningful zero and can be divided.

`@possible_answers`
- [Ratio]
- Interval
- Ordinal
- Nominal

`@feedback`
<!-- Examples of good feedback messages: https://instructor-support.datacamp.com/en/articles/2299773-exercise-success-messages.  -->
- Exactly
- Change always has a meaningful zero, no change - so it is a ratio variable, not an interval one.
- It's a quantitative variable, not a categorical one
- It's a quantitative variable, not a categorical one
