title: Broadcasting
--- |
  Numpy allows element wise operations between arrays of different shapes with certain `restrictions`. The process is called `Broadcasting`. The smaller array is “broadcast” across the larger array so that they have compatible shapes.

  NumPy compares the dimensions of the arrays starting with the trailing ones, and works its way backwards. Two dimensions are compatible when:
  * The shape of the smaller array matches the shape of the larger one comparing backwards.
  * The shape of the two arrays do not match but one of them equals to 1.

  When the smaller array runs out of dimension, Numpy assumes a shape of 1 in that dimension to match with that of the larger array till the dimensions of the larger array runs out.
---
type: live-code
id: 7b3ddc71-1171-449a-bbc2-5f3b8102b2b1
code: |
  import numpy as np
  a1 = np.arange(6).reshape(2, 3)
  a2 = np.arange(3)
  a1 + a2
---
type: testless-coding-question
id: 3f7b0cd0-b476-4762-b01c-867f994192b5
question: |
  Multiply the the arrays `a1` and `a2` and see how the broadcasting works for arrays with different shapes.
code: |
  import numpy as np
  a1 = np.ones((2, 3, 4))
  a2 = np.arange(12).reshape(3,4)
--- |
  Arrays with no matching shape can be reshaped to take advantage of the Broadcasting.
---
type: live-code
id: 9669ea16-78fc-4148-ad11-dc22b62cecea
code: |
  import numpy as np
  a1 = np.arange(5)
  a2 = np.arange(4)
  print (a1.shape, a2.shape)
  a2 = a2.reshape(-1,1)
  print (a1.shape, a2.shape)
  a1 + a2
--- |
  The arrays can also be reshaped using numpy.newaxis. Each newaxis object expands the dimensions of the resulting selection by one unit-length dimension.
---
type: coding-question
id: 97910441-30e5-470c-ab91-3fe35dc1c783
question: |
  Multiply the arrays `a1` and `a2` given below by adding a new axis to the array `a2` and save the resulting array to `a_prod`. Do not use reshape.
code: |
  import numpy as np
  a1 = np.arange(3)
  a2 = np.arange(4)
tests: |
  assert np.array_equal(a_prod, [[0, 0, 0], [0, 1, 2], [0, 2, 4], [0, 3, 6]])
---
