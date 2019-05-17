title: Indexing Series using loc
--- |
  [Series.iloc](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.Series.iloc.html#pandas-series-iloc) is used to access group of values based on position. Even if a Series is created using custom index, one or more values can be selected based on the underlying postion. The position is based on rangeindex (0 to len(data) -1).
---
type: live-code
id: 68e4ef6d-e1c4-4baa-96a2-59dbb5cb1a26
code: |
  import pandas as pd
  s = pd.Series([1,2,3,4,5], index = [1,3,4,5,6])
  s
--- |
  The first element of the above Series can be selected by passing position 0 to Series.iloc, even though the custom index does not contain 0.
---
type: live-code
id: f47e6690-21fa-4636-a81b-3cd14bae4131
code: |
  import pandas as pd
  s = pd.Series([1,2,3,4,5], index = [1,3,4,5,6])
  s.iloc[0]
--- |
  Similarly, a group of elements are selected by passing a list of positions to Series.iloc.
---
type: live-code
id: 2c0fdc5b-a759-4943-825d-1ddea1bd7eaa
code: |
  import pandas as pd
  s = pd.Series([1,2,3,4,5], index = [1,3,4,5,6])
  s.iloc[[2, 4]]
--- |
Creating a slice using Series.iloc[lower_index, upper_index] follows Python slicing notation. The below code returns elements values at position 1 and 2 but not at 3.
---
type: live-code
id: d9b162c6-e057-406e-8ea8-ed0934e5748d
code: |
  import pandas as pd
  s = pd.Series([1,2,3,4,5], index = [1,3,4,5,6])
  s.iloc[1:3]
