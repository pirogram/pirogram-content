title: Advanced Indexing
--- |
  Advanced indexing uses lists or arrays of indices unlike basic indexing which uses tuples of slices for indexing. In advanced indexing, all index lists are first broadcasted to the same shape, and this shape is used for the output array.
  Advanced indexing returns a copy of the data as against basic indexing, which returns a view.
--- |
  Here is an example of selecting a specific element from each row based on the column index.
---
type: live-code
id: 299bcec0-64ab-405b-9f10-fc43185283fc
code: |
  import numpy as np
  a = np.arange(8).reshape(4,2)
  # Return first element at row 0, second at row 1, first at row 2 and 3.
  a[[0, 1, 2, 3], [0, 1, 0,0]]
--- |
  Arrays can also be indexed by passing a 2 - D array at each dimension.
---
type: live-code
id: c3c3cbb5-98ec-4119-be12-1a95cdd00cb2
code: |
  import numpy as np
  a = np.arange(1,17,1).reshape(4,4)
  x = np.array([[0,0], [3,3]], dtype = 'int8')
  y = np.array([[0,1], [2,3]], dtype = 'int8')
  # Return the elements at [0,0], [0,1] and [3,2], [3,3].
  a[x, y]
--- |
  The same can be extended to a 3 dimensional array.
---
type: live-code
id: 5920d28c-913e-4531-8e18-38172c3771a3
code: |
  import numpy as np
  a = np.arange(18).reshape(3,2,3)
  # Return element at [0,0] for index 0 of first dimension and at [1,2] for index 2 of first dimension.
  a[[0,2], [0,1],[0,2]]
--- |
  The advanced indexing can be combined with basic by using a list based integer index at one dimension and a slice at another.
---
type: live-code
id: c2962b84-d468-44df-9076-bb4a18580fe2
code: |
  import numpy as np
  a = np.arange(18).reshape(3,2,3)
  a[[0,2],:,1:]
---
type: coding-question
id: bb1bc9ab-a134-4466-885b-b404e34efb28
question: |
  Return the elements at column 2 and 3 of the first row and column 0 and 1 of the last row from the following 2-D array. Save to `a_select`.
code: |
  import numpy as np
  a = np.arange(24).reshape(6,4)
  a
tests: |
  assert np.array_equal(a_select, [[ 2,  3], [20, 21]])
---
type: coding-question
id: 1b975872-43a3-4e1f-9091-c9d4c91b7984
question: |
  Return the elements at row 0 and 1 of the first column and row 4 and 5 of the last column from the following 2-D array. Save to `a_select`.
code: |
  import numpy as np
  a = np.arange(24).reshape(6,4)
  a
tests: |
  assert np.array_equal(a_select, [[ 3,  7], [16, 20]])  
---
type: coding-question
id: c00056f2-1e5b-45c1-afb0-04b0a55b7a11
question: |
  Return all the elements from the first column of the following 4-D array. Save the resulting (2,2,2) array to `a_col_0`.
code: |
  import numpy as np
  a = np.arange(16).reshape(2,2,2,2)
  a
tests: |
  assert np.array_equal(a_col_0, [[[ 0,  2], [ 4,  6]], [[ 8, 10], [12, 14]]])
---
