title: Indexing DataFrame using iloc
--- |
  [DataFrame.iloc](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.iloc.html#pandas-dataframe-iloc)[row position, column position] is used to return one or more values based on index and column `position`.
  Here is a DataFrame with custom column names and default rangeindex.
---
type: live-code
id: cb314ebe-04af-4b43-b5b3-a6a203fdeedc
code: |
  import pandas as pd
  df = pd.DataFrame(np.arange(20).reshape(4,5), columns = list('ABCDE'))
  df
--- |
  The following code returns a scalar (single value) at index 1 and column position 1 (second column - column B).
---
type: live-code
id: 04e97af0-9ce9-4765-88e5-c28b47e77b78
code: |
  import pandas as pd
  df = pd.DataFrame(np.arange(20).reshape(4,5), columns = list('ABCDE'))
  df.iloc[1,1]
--- |
  Even if the DataFrame is constructed using custom index, DataFrame.iloc returns values based on rangeindex based position.
---
type: live-code
id: 6dd3fda2-d293-4688-a4e6-818e7e11e3e3
code: |
  import pandas as pd
  df = pd.DataFrame(np.arange(20).reshape(4,5), columns = list('ABCDE'), index = pd.date_range('01-01-2019', periods=4))
  print(df)
  df.iloc[1, 1]
--- |
  The same works for DataFrames with DateTimeIndex. To find values on '2019-01-03' and '2019-01-04' for columns A and B, pass a list of index positions followed by list of column positions to DataFrame.iloc.
---
type: live-code
id: 895c29f2-f8b4-4115-80d0-fabfe5a39466
code: |
  import pandas as pd
  df = pd.DataFrame(np.arange(20).reshape(4,5), columns = list('ABCDE'), index = pd.date_range('01-01-2019', periods=4))
  df.iloc[[2, 3], [0, 1]]
