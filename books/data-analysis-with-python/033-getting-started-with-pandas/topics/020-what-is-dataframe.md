title: What is DataFrame
--- |
  Pandas is the most preferred Python library for data analysis. The reason is its core data structure DataFrame, a 2-dimensional labeled data structure with columns of potentially different types.

  So what is a DataFrame and why do we need it when eventually we are going to use a Numpy array for Machine Learning? Lets look at the data of demographic profile of 10 randomly selected users of an online retail company. The company is trying to predict how many users will sign up for annual membership.
---
type: live-code
id: 0cd6eab2-0477-42c1-9f7c-1afd26d60e5a
code: |
  import numpy as np
  data = np.array([[ 100000,       1,       1,      59,       1],
       [ 110000,       1,       5,      31,       0],
       [ 200000,       0,       4,      45,       0],
       [  75000,       1,       3,      27,       1],
       [ 125000,       0,       1,      18,       1],
       [ 210000,       0,       2,      26,       0],
       [  60000,       0,       2,      55,       1],
       [ 250000,       1,       4,      22,       0],
       [5000000,       0,       2,      24,       1],
       [ 175000,       1,       3,      51,       1],
       [  70000,       0,       2,      40,       0]])

  data
--- |
  Even though the data is efficiently contained in the Numpy array, it gives no insight to the data analyst about the variables. Now lets convert the array into a Pandas DataFrame. The tabular data structure of a Pandas DataFrame organizes data in the form of `rows` and `columns`. The column header allows users to understand the `variables` and the row headers indicate that each row is an `observation`. The Pandas DataFrame also supports mixed datatypes making it an ideal starting point.
---
type: live-code
id: 690fccb0-f289-4dfc-8237-b89e332a9af0
code: |
  import numpy as np
  import pandas as pd
  data = np.array([[ 100000,       1,       1,      59,       1],
       [ 110000,       1,       5,      31,       0],
       [ 200000,       0,       4,      45,       0],
       [  75000,       1,       3,      27,       1],
       [ 125000,       0,       1,      18,       1],
       [ 210000,       0,       2,      26,       0],
       [  60000,       0,       2,      55,       1],
       [ 250000,       1,       4,      22,       0],
       [5000000,       0,       2,      24,       1],
       [ 175000,       1,       3,      51,       1],
       [  70000,       0,       2,      40,       0]])
  df = pd.DataFrame(data, columns = ['family_income','sex','family_size','age','member'])
  df
--- |
  The above DataFrame indicates that we are looking at family income, sex, family size and age as key `variables`. We can now see what does the data in each column indicates.
  The benefits of working with data in this format are:
  * It is easier to get feel of the data.
  * It is easier to visualize the data from a DataFrame.
  * DataFrame object can be of mixed data types unlike Numpy arrays which need to be homogenous.
  * If the data is messy, the tabular data structure allows cleaning to convert it to tidy structure.
  * Handling missing values and outliers.
  * Encoding categorical data
  * Cleaning text data
  * Working with datetimes

  There are various methods built-in to pandas that can be used for purpose. The processed data is then converted to Numpy NDarray for Machine Learning.
