title: Data overview
--- |
  Once the data is loaded from the given source in a DataFrame, first step would be to overview the data. There are some built-in attributes and methods for the purpose.

  Attributes
  * DataFrame.shape
  * DataFrame.dtypes
  * DataFrame.index
  * DataFrame.columns
  * DataFrame.values

  Methods:
  * DataFrame.head
  * DataFrame.tail
  * DataFrame.describe

  ### Attributes

  #### DataFrame.shape
  [DataFrame.shape](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.shape.html) returns returns a tuple representing the dimensionality (number of rows and columns) of the Series or DataFrame object .
---
type: live-code
id: a0dfada1-005d-4691-909a-cf7410e1a50c
code: |
  import pandas as pd
  iris = pd.read_csv('data/pandas/iris.csv')
  iris.shape
--- |
  #### DataFrame.dtypes
  [DataFrame.dtypes](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.dtypes.html#pandas.DataFrame.dtypes) returns the data type of each column in the DataFrame.
---
type: live-code
id: 557f33c2-b062-4324-a01a-41e154bb8c6c
code: |
  import pandas as pd
  iris = pd.read_csv('data/pandas/iris.csv')
  iris.dtypes
--- |
  #### DataFrame.index
  [DataFrame.index](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.index.html) returns an NDarray containing axis labels of the object.
---
type: live-code
id: 3b33d26d-4b85-452d-970e-7707314904ee
code: |
  import pandas as pd
  iris = pd.read_csv('data/pandas/iris.csv')
  iris.index
--- |
  #### DataFrame.columns
  [DataFrame.columns](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.columns.html) returns column labels of the DataFrame.
---
type: live-code
id: f5a6815a-7eda-4c37-9ad6-d93bc276b583
code: |
  import pandas as pd
  iris = pd.read_csv('data/pandas/iris.csv')
  iris.columns
--- |
  #### DataFrame.values
  [DataFrame.values](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.values.html) return a Numpy representation of the DataFrame.
---
type: live-code
id: b3ff4675-ed40-444b-bae5-735bae1f67ea
code: |
  import pandas as pd
  iris = pd.read_csv('data/pandas/iris.csv')
  iris.values
--- |
  ### Methods

  #### DataFrame.head & DataFrame.tail

  [DataFrame.head](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.head.html) & [DataFrame.tail](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.tail.html#pandas.DataFrame.tail) return top or bottom n rows respectively. The default value of n is 5 but can be set to any required integer.
---
type: live-code
id: 408f8263-ac66-40c0-a7bf-9e5dc2bd4970
code: |
  import pandas as pd
  iris = pd.read_csv('data/pandas/iris.csv')
  iris.head()
---
type: live-code
id: 179b1508-38ab-407c-9420-08c9c7a1076c
code: |
  import pandas as pd
  iris = pd.read_csv('data/pandas/iris.csv')
  iris.tail(3)
--- |
  #### DataFrame.describe

  [DataFrame.describe](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.describe.html) describe generates the descriptive statistics that summarizes the central tendency, dispersion and shape of a dataset’s distribution, excluding NaN values. The parameter `include` can be used to include columns with non-numeric types.
---
type: live-code
id: d53acde0-47d8-446a-a6fb-053562a3f2c7
code: |
  import pandas as pd
  iris = pd.read_csv('data/pandas/iris.csv')
  print('Statistical summary of numeric columns: ',iris.describe())
  print('Statistical summary of object columns: ',iris.describe(include = ['O']))
  print('Statistical summary of all columns: ',iris.describe(include = 'all'))
