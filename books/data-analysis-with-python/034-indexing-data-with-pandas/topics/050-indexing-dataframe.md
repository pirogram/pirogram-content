title: Indexing DataFrame
--- |
  Dataframe is a 2 dimentional data structure and hence selecting a value from DataFrame would involve selection based on row as well as column.

  Similar to Series, values can be selected from DataFrame using simple [] notation or using [DataFrame.loc](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.loc.html#pandas-dataframe-loc) and [DataFrame.iloc](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.iloc.html#pandas-dataframe-iloc). Methods loc and iloc select data based on labels and positions respectively. The [] notation of selection works different from that in Series.

  ### Selecting data using [ ]
  As Series is a 1-dimentional data structure, indexing Series using [] returns a value based on index. On the other hand, indexing DataFrame using [] returns values based on columns.
---
type: live-code
id: 86e0f9ba-0c0b-4ca2-82ee-63f806cb5d3d
code: |
  import pandas as pd
  df = pd.DataFrame(np.arange(20).reshape(4,5))
  df
--- |
  When the above DataFrame is indexed by passing an integer, pandas returns a slice by assuming it to be column and NOT index. The following code will return column 2.
---
type: live-code
id: fd33def5-17da-484a-b20b-a6d0b1362bb8
code: |
  import pandas as pd
  df = pd.DataFrame(np.arange(20).reshape(4,5))
  df[2]
--- |
  It works similarly if the column names are not the default range-based values.
---
type: live-code
id: 8b62fb2b-7e44-469e-9058-45a3da23d666
code: |
  import pandas as pd
  df = pd.DataFrame(np.arange(20).reshape(4,5), columns = list('ABCDE'))
  df
---
type: live-code
id: cc32e5f4-0796-4b22-9d5d-87cc5dd56e78
code: |
  import pandas as pd
  df = pd.DataFrame(np.arange(20).reshape(4,5), columns = list('ABCDE'))
  df['B']
--- |
  Please note that each column of a Pandas DataFrame is a Series. To create a DataFrame with one column instead of a Series, pass the column name in a bracket.
---
type: live-code
id: 089ecf37-de16-4aa6-abce-0ebe5171fd7b
code: |
  import pandas as pd
  df = pd.DataFrame(np.arange(20).reshape(4,5), columns = list('ABCDE'))
  print(type(df['B']))
  print(type(df[ ['B'] ]))
--- |
  Multiple columns can be selected from a Dataframe by passing a list of column names to DataFrame object.
---
type: live-code
id: 42c13a93-0f47-46f0-8e0e-26baef7c2ced
code: |
  import pandas as pd
  df = pd.DataFrame(np.arange(20).reshape(4,5), columns = list('ABCDE'))
  df[['B', 'E']]
