title: Universal Functions
--- |
  NumPy provides various arithmetic, trigonometric, comparison and specialized functions called `Universal functions`(ufunc). These functions operate element wise on an array and produce an array as output.
--- |
 Here are some arithmetic `ufuncs`.
---
type: live-code
id: 41926e29-8d11-44d1-921f-0e9803c99c65
code: |
  import numpy as np
  a = np.array([1,2,3,4,5])
  b = np.full(5, 5)
  np.add(a, b)
--- |
  The arithmetic ufuncs work in case of array operations with scalars.
---
type: live-code
id: 4a5221e8-f28e-4fe3-acb5-2cd0219a2e7a
code: |
  import numpy as np
  a = np.array([1,2,3,4,5])
  np.subtract(a, 5)
---
type: coding-question
id: f76b0d3e-aa52-4d0b-a26b-14dba66da1f9
question: |
    Find the floor division of array `a1` with array `a2` and store the result in `a_quotient`. Use the ufunc for floor division ([`np.floor_divide()`](https://docs.scipy.org/doc/numpy/reference/generated/numpy.floor_divide.html)).
code: |
  import numpy as np
  a1 = np.array([6, 2, 19, 31, 9])
  a2 = np.array([2, 5, 4, 5, 6])
tests: |
  assert np.array_equal(a_quotient, [3, 0, 4, 6, 1])
---
type: coding-question
id: 4dda9986-a12b-4af2-8831-e14cd23789aa
question: |
    Raise the elements in array `a1` to the power of `a2` using the ufunc and save the resulting array to `a_power`. Hint: use [`np.power()`](https://docs.scipy.org/doc/numpy/reference/generated/numpy.power.html).
code: |
  import numpy as np
  a1 = np.array([1, 3, 5, 4, 2])
  a2 = np.array([3, 4, 4, 1, 3])
tests: |
  assert np.array_equal(a_power, [  1,  81, 625,   4,   8])
---
type: coding-question
id: 89d15b4c-f4fe-4e7c-979a-7fdddbbe7043
question: |
  Calculate element wise remainder between arrays a and b. Save the result to `a_b_remainder`. Hint: use [`np.remainder()`](https://docs.scipy.org/doc/numpy-1.14.0/reference/generated/numpy.remainder.html).
code: |
  import numpy as np
  a = np.array([5, 10, 12, 15, 17])
  b = np.full(5, 3)
tests: |
  np.array_equal(a_b_remainder, [2, 1, 0, 0, 2])
--- |
  Now lets look at some trignometric functions in Numpy.
---
type: live-code
id: 04c4e616-d50e-4b96-b84b-c93aa2deb308
code: |
  import numpy as np
  angles = np.array([0., 30., 45., 60., 90.])
  np.sin(angles)
--- |
  Here are some comparison functions.
---
type: live-code
id: 3ecda0cc-f421-47af-b90c-dfb36d4f5442
code: |
  import numpy as np
  a = np.array([9, 5, False, False, 3])
  b = np.array([False, 4, 2, False, 1])
  np.logical_and(a, b)
---
type: coding-question
id: 687852fc-d3cf-484e-ba8e-1eee3dec6842
question: |
  For the arrays `a` and `b` given below, return the truth value of a > b element-wise and save the result to `bool_a_b` (Hint: look for a numpy function greater)
code: |
  import numpy as np
  np.random.seed(10)
  a = np.random.randn(5)
  b = np.random.randn(5)
tests: |
  assert np.array_equal(bool_a_b, [ True,  True, False, False,  True])
--- |
  Some of the functions for rounding are `round`, `rint`, `floor`, `ceil`, `trunc`.
---
type: coding-question
id: 78112847-bfd1-4c38-8c54-3c9ef5f5f077
question: |
  Round the array `a` to 2 decimals (Hint: look at np.round) and save the result to `a_round`.
code: |
  import numpy as np
  np.random.seed(1)
  a = np.random.randn(5)
tests: |
  np.array_equal(a_round, [ 1.62, -0.61, -0.53, -1.07,  0.87])
---  
