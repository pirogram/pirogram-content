title: Indexing DataFrame
--- |
  [DataFrame.loc](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.loc.html#pandas-dataframe-loc)[row label, column label] is used to return one or more values based on labels.

  Here is a DataFrame with custom column names and default rangeindex.
---
type: live-code
id: eb54fa49-0620-4b16-814c-6631b6baef83
code: |
  import pandas as pd
  df = pd.DataFrame(np.arange(20).reshape(4,5), columns = list('ABCDE'))
  df
--- |
  If we index the above dataframe by passing index 1 and column B to  DataFrame.loc, it returns a scalar (single value).
---
type: live-code
id: d9a51905-bbbf-4f20-ba92-9d38cf000c94
code: |
  import pandas as pd
  df = pd.DataFrame(np.arange(20).reshape(4,5), columns = list('ABCDE'))
  df.loc[1, 'B']
--- |
  DataFrame.loc supports a combination of single value, list and slice at both index and column levels.
  To find values at index 1 for columns B and D, pass a list of column names.
---
type: live-code
id: 7575468d-308d-4cdf-a762-3afbcf79275f
code: |
  import pandas as pd
  df = pd.DataFrame(np.arange(20).reshape(4,5), columns = list('ABCDE'))
  df.loc[1, ['B', 'D']]
--- |
  Lets select values of columns A and B on '2019-01-02' for the following DataFrame with DateTimeIndex.
---
type: live-code
id: ab0a314d-08c3-4462-b05e-0a57cb2111ba
code: |
  import pandasas pd
  df = pd.DataFrame(np.arange(20).reshape(4,5), columns = list('ABCDE'), index = pd.date_range('01-01-2019', periods=4))
  df.loc['2019-01-02', ['A', 'B']]
---
