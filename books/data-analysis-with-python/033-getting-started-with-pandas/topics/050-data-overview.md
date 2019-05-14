title: Data overview
--- |
  Once we load the data into a Series or a Dataframe, we start by gettting an overview of the data. The following methods and attributes in Pandas which make the process easier.
  #### Viewing the data
  [DataFrame.head](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.head.html) & [DataFrame.tail](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.tail.html#pandas.DataFrame.tail) return the first and the last n rows respectively. The default value of n is 5.
---
type: live-code
id: 408f8263-ac66-40c0-a7bf-9e5dc2bd4970
code: |
  import numpy as np
  import pandas as pd
  df = pd.DataFrame(data = np.random.randn(50,4), columns = ['One', 'Two', 'Three', 'Four'])
  print('Top 5 rows: ',df.head())
  print('Bottom 4 rows: ',df.tail( n = 4))
--- |
  #### Viewing index, columns and underlying Numpy array.
  [DataFrame.index](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.index.html),  [DataFrame.columns](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.columns.html) and [DataFrame.values] display the index, columns and the data in the form of Numpy array respectively.
---
type: live-code
id: 0280695c-e556-4642-aeea-d5643586d054
code: |
  import numpy as np
  import pandas as pd
  df = pd.DataFrame(data = np.random.randn(50,4), columns = ['One', 'Two', 'Three', 'Four'])
  print('Index: ',df.index)
  print('Columns: ',df.columns)
  print('Data: ', df.values)
--- |
  #### Statistical summary of data
  [DataFrame.describe](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.describe.html) generates descriptive statistics of numeric columns that summarize the central tendency, dispersion and shape of a dataset’s distribution, excluding NaN values. The parameter `include` can be used to specify non-numeric types.
---
type: live-code
id: d53acde0-47d8-446a-a6fb-053562a3f2c7
code: |
  import numpy as np
  import pandas as pd
  df = pd.DataFrame({'name':['a', 'b', 'c', 'd'], 'val1':[1,2,3,4], 'val2':[1.1,1.2,1.3,1.4]})
  print(df)
  print('Statistical summary of numeric columns: ',df.describe())
  print('Statistical summary of object columns: ',df.describe(include = ['O']))
  print('Statistical summary of all columns: ',df.describe(include = 'all'))
--- |
  The index and columns of a DataFrame can be transposed using [DataFrame.T](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.T.html). It reflects the DataFrame over its main diagonal by writing rows as columns and vice-versa. The `property` T is an accessor to the method transpose().
---
type: live-code
id: 2d734798-5762-4bde-98d0-010913bb6d26
code: |
  import numpy as np
  import pandas as pd
  df = pd.DataFrame(data = {'col1':[1,2,3,4], 'col2':['a', 'b', 'c', 'd']})
  print(df)
  print(df.T)
--- |
  A DataFrame can be sorted by index or values using the methods [DataFrame.sort_index](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.sort_index.html) and [DataFrame.sort_values](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.sort_values.html). Both the methods work on
