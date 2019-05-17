title: Indexing Series
--- |
  Series is a 1-dimentional data structure and can be indexing using [Series.loc](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.Series.loc.html#pandas-series-loc) (label based selection), [Series.iloc](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.Series.iloc.html#pandas-series-iloc) (location/index based selection) and in most basic case, using `[]`.

  ### Selecting data using [ ]

  Indexing using [] works similar to indexing a python list. The index label or the range of labels can be passed to the Series object to get an element or a slice. A slice[lower_index : upper_index] will return all the data from lower_index till 1 less than upper_index.
---
type: live-code
id: 6a831545-a516-4d1e-b66b-f4bab0292be9
code: |
  import pandas as pd
  s = pd.Series([1,2,3])
  s[0]
--- |
  The slice notation followes object[lower_index : upper_index] where data at upper index is excluded. In case of missing lower_index, the slice will be from the beginning of the data and if the upper_index is missing, the data will be sliced till the end. The following returns a slice containing elements at index 0 and 1, but not at index 2.
---
type: live-code
id: d6164774-ef61-4881-b29b-e52401cdaa07
code: |
  import pandas as pd
  s = pd.Series([1,2,3])
  s[:2]
--- |
The slice notation works slightly different in case of custom index and returns all the elements included in the range.
---
type: live-code
id: 9d11ed61-62f1-4553-95bd-7b28f06676af
code: |
  import pandas as pd
  s = pd.Series(np.arange(1,10,1), index = list('ABCDEFGHI'))
  print(s)
  s['B': 'E']
--- |
  If data at specific indexes need to be selected, the Series object can be indexed by passing a list of those index labels.
---
type: live-code
id: 5bb5564a-688f-4fa1-b2f1-ed985f8bc090
code: |
  import pandas as pd
  s = pd.Series(np.arange(1,10,1), index = list('ABCDEFGHI'))
  s[ ['B', 'E'] ]
--- |
  As we saw in the examples above, the [] notation of indexing works for simple use cases. There are certain cases where it returns ambiguous output.

  Here is a Series built using customer integer index. When we pass a single index or a list of index, Pandas assumes them to be index label and NOT position.
---
type: live-code
id: 22ad68cc-52a9-418e-a448-0df7bfd48f81
code: |
  import pandas as pd
  s = pd.Series([1,2,3,4,5], index = [1,3,4,5,6])
  s[ [3, 5]]
--- |
The behavior changes when we try to select a slice. The slice is created based on position and not the custom label.
---
type: live-code
id: c318705f-0071-48ec-b0ec-e5e615706c39
code: |
  import pandas as pd
  s = pd.Series([1,2,3,4,5], index = [1,3,4,5,6])
  s[ 3:5 ]
--- |
  Methods Series.loc and Series.iloc deal with the custom index well and eliminate the possibility of ambiguous output.
