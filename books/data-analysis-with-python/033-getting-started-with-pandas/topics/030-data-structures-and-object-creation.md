title: Data Structures and Object creation
--- |
  We will start with an overview of the two data structures in Pandas, `Series` and `DataFrame`.

  ### Series
  Series is a `one-dimensional` array labeled with axis labels. The two key components of a series are `data` and `index`.
  #### Data
  The `data` can be of various types like integers, strings, floating point numbers, Python objects, etc.
  Here are some data structures that can be used to create a series:
  * Numpy array
  * Python list
  * Python dictionary
  * A scalar value
  #### Index
  The axis labels are referred to as the `index` and should be of hashable type like integers, strings, floating point numbers, tuples etc.

  The basic method to create a Series is to call [pandas.series](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.Series.html#pandas.Series). The default setting for data and index parameters is None and will create an empty series. If we pass data but no index to [pandas.series](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.Series.html#pandas.Series), Pandas automatically generates `integer index` having values (0, len(data)-1)
---
type: live-code
id: 14ea82a0-4c00-4aae-a91c-d1744712bc5c
code: |
  import pandas as pd
  s = pd.Series()
  s
---
type: live-code
id: 4ebeecd3-c151-4567-8368-6ca9d7a04cdb
code: |
  import numpy as np
  import pandas as pd
  # Series from a Numpy array
  s = pd.Series(data = np.random.randn(4))
  s
---
type: live-code
id: 7307313d-4e66-436e-83a6-72c01f946d9a
code: |
  import pandas as pd
  # Series from a Python list with index
  s = pd.Series(data = [1,2,3,4], index = ['a', 'b', 'c', 'd'])
  s
--- |
  When the data is a `dictionary`, and an index is not passed, the Series index will be ordered by the dict’s insertion order,
---
type: live-code
id: ecfa6b69-6bd8-4dd1-8d2f-efd5e5d1ecb6
code: |
  import pandas as pd
  # Series from a Python dictionary
  s = pd.Series(data = {'a': 1, 'b': 2, 'c': 3, 'd': 4})
  s
--- |
  If data is a scalar value, an index must be provided. The value will be repeated to match the length of index.
---
type: live-code
id: 35de5cfe-aef3-41b7-8210-dfb5395a8fc1
code: |
import pandas as pd
  # Series from a Python dictionary
  s = pd.Series(data = 100, index = ['a', 'b', 'c', 'd'])
  s
--- |
  ### Dataframe
  Dataframe is a `2-dimensional` labeled data structure which supports columns of different types. It contains three key components, `data`, `index` and `columns`.
  #### Data
  Data can be one of various types listed below:
  * Dict of 1D ndarrays, lists, dicts, or Series
  * 2-D numpy.ndarray
  * Pandas Series
  #### Index
  Index works in similar way as that in Series and should be of hashable type like integers, strings, floating point numbers, tuples etc. Pandas automatically generates `integer index` having values (0, len(data)-1) if no index is specified. Since Dataframe is 2 dimensional data structure, there are two levels of axis labels. Index is referred to as axis 0.
  #### Columns
  The second level of axis labels in Dataframe called columns. They are referred to as axis 1.

  The basic method to create a Series is to call [pandas.DataFrame](https://pandas.pydata.org/pandas-docs/version/0.23.4/generated/pandas.DataFrame.html). The default setting for data and index parameters is None and will create an empty dataframe. If we pass data without index and columns to [pandas.DataFrame](https://pandas.pydata.org/pandas-docs/version/0.23.4/generated/pandas.DataFrame.html), Pandas automatically generates `integer index` having values (0, len(data axis 0)-1) and column names having values (0, len(data axis 1)-1).
---
type: live-code
id: c9d5fd2c-189f-4ca7-be59-61c8690d11ec
code: |
  import numpy as np
  import pandas as pd
  # Dataframe from a 2-d Numpy array
  df = pd.DataFrame(data = np.random.randn(5,2))
  df
--- |
  While creating a dataframe from dictionary of arrays, `ndarrays` must all be the same length. If an `index` is passed, it must also be the same length as the arrays.
---
type: live-code
id: ad2aedeb-5db5-4ffe-918b-0b6d7f62adc5
code: |
  import numpy as np
  import pandas as pd  
  # Dataframe from a Dict of lists
  df = pd.DataFrame(data = {'col1':[1,2,3,4], 'col2':['a', 'b', 'c', 'd']})
  df
--- |
  A Dataframe can also be created from Pandas Series. They can be passed as dictionary `column name` as keys and `series` as values.
---
type: live-code
id: fadb5657-7419-4099-afb7-ebee49bfd941
code: |
  import pandas as pd
  s1 = pd.Series([1,2,3])
  s2 = pd.Series([4,5,6])
  df = pd.DataFrame({'s1':s1, 's2':s2})
  df
---
type: testless-coding-question
id: dc28c9a3-b82a-4bb1-8f80-77aaa5e65a0c
question: |
  Create a pandas Series from the numpy arrays given below. The dates should be index and the values as the value.
code: |
  import numpy as np
  import pandas as pd
  dates = pd.date_range(end = np.datetime64('today'), periods = 10)
  np.random.seed(1234)
  values = np.random.randint(10, 100, 10)
  # Your code goes Here
