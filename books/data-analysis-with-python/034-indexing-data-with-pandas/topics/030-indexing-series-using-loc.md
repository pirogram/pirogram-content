title: Indexing Series using loc
--- |
  [Series.loc](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.Series.loc.html#pandas-series-loc) is used to access group of values based on labels.
  Here is a series created using custom labels.
---
type: live-code
id: 3314f867-97a6-4dc0-88e6-33a97e7a4b5e
code: |
  import pandas as pd
  s = pd.Series([1,2,3,4,5], index = [2,4,6,8,10])
  s
--- |
  Passing the index label to series.loc returns the element at that index.
---
type: live-code
id: 2e134353-b9fd-4d28-864a-a829dcc6d16d
code: |
  import pandas as pd
  s = pd.Series([1,2,3,4,5], index = [2,4,6,8,10])
  s.iloc[4]
--- |
  Similarly, a group of elements can be selected by passing a list of index labels to Series.loc.
---
type: live-code
id: 2303087e-0f57-4c08-afa4-66f3d920e8ab
code: |
  import pandas as pd
  s = pd.Series([1,2,3,4,5], index = [2,4,6,8,10])
  s.iloc[ [4, 8] ]
--- |
  Creating a slice using Series.loc[lower_index, upper_index] returns elements at lower_index, upper_index and between the two. (Note that this behaviour is different from that in Python slicing)
---
type: live-code
id: 5a58545c-fc1b-419f-bcd5-59ed01e7b851
code: |
  import pandas as pd
  s = pd.Series([1,2,3,4,5], index = [2,4,6,8,10])
  s.loc[4:8]
