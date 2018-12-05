title: Boolean Indexing
--- |
  Boolean indexing is a form of advanced indexing in which the indexing object is an array object of Boolean type (usually returned from a comparison operator). It returns a 1-D array of the elements of the indexed array corresponding to the True values of object.
---
type: live-code
id: d991ad2a-35b0-4a8a-85f8-09e9bf127259
code: |
  import numpy as np
  a = np.array([5,3,12,9,8,15])
  # Index the array a to return an array with only the numbers greater than 10.
  a[ a > 10]
--- |
  Arrays can also be indexed using bulit-in methods that return indices or a boolean array.
---
type: live-code
id: 77d08777-2c1f-4ec4-8d78-fab50cb32916
code: |
  import numpy as np
  a = np.array([1,2,3,0,np.nan,5,np.nan,0])
  # Return only the finite (not-null) values from the given array.
  a[np.isfinite(a)]
--- |
  Boolean indexing can be used in conjunction with ~ to perform bit-wise inversion or bit-wise NOT.
---
type: live-code
id: 07184b5d-1044-4803-a8c5-3aa23957496a
code: |
  import numpy as np
  a = np.array([1,2,3,0,np.nan,5,np.nan,0])
  a[~np.isnan(a)]
---
type: coding-question
id: 0082c61e-ceed-410e-a7c0-850950d78ee4
question: |
  The following array has some outliers (numbers greater than or equal to 999). Use boolean indexing to filter those numbers and save the resulting array in `a_clean`.
code: |
  import numpy as np
  a = np.array([5,3,1212,9,1008,999, 1,2, 11, 1000])
  a
tests: |
  assert np.array_equal(a_clean ,[5, 3, 9, 1, 2, 11])
---
type: coding-question
id: 735288a8-e13e-423d-9356-0a8fead0748f
question: |
  Extract odd numbers from the following array `a` and save to `a_odd`.
code: |
  import numpy as np
  np.random.seed(123)
  a = np.random.randint(0, 10, 9)
tests: |
  assert np.array_equal(a_odd ,[1, 3, 9, 1])
---
type: coding-question
id: 508db6c7-b7e6-4b91-9be2-5884a8e456a2
question: |
  Return non-zero values from the array `a` and save the result to `a_nonzero`. Use numpy [`nonzero()`](https://docs.scipy.org/doc/numpy-1.15.0/reference/generated/numpy.nonzero.html) for indexing.
code: |
  import numpy as np
  np.random.seed(1230)
  a = np.random.randint(-3 , 3, 10)
  a
tests: |
  assert np.array_equal(a_nonzero ,[ 2, -2, -2, -2, -3, -3, -3])
--- |
  Arrays can be indexed based on multiple conditions using `bitwise` & (and) and | (or) operators. It is important to separate the conditions by parentheses as `bitwise` & has higher precedence than `<` and `>` which in turn have higher precedence than logical `and`.
---
type: live-code
id: 88ba746f-9036-4d11-85f7-061be853150a
code: |
  import numpy as np
  # Extract the numbers divisible by 3 or 5 from the array `a`.
  a = np.array([3, 14, 8, 9, 15, 10, 22, 5])  
  a[(a % 3 == 0) | (a % 5 == 0)]
---
type: coding-question
id: 7e474efa-875e-4566-b453-1e63d74167de
question: |
  Use boolean indexing to extract numbers greater than -5 and smaller than 10 from the following array `a`. Save the output to `a_small`.
code: |
  import numpy as np
  np.random.seed(10)
  a = np.random.randint(-10 , 20, 20)
  a
tests: |
  assert np.array_equal(a_small , [-1,  5,  7,  6,  7, -2, -1,  0, -2])
---
type: coding-question
id: b3487214-4e0e-46f2-9e84-a1d5c53b61a2
question: |
  Remove zero and null values from the array `a` and save the result to `a_clean`.
code: |
  import numpy as np
  a = np.array([1,np.nan, 2, 3, 0, 0, np.nan, 5])
tests: |
  assert np.array_equal(a_clean ,[ 1, 2, 3, 5])
---
