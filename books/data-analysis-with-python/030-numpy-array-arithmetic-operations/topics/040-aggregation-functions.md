title: Aggregation functions
---
  Numpy provides built-in aggregation functions including various statistical functions. These functions aggregate over the flattened array or over the specifies axis.
---
type: live-code
id: 042644ba-a1c7-4d5a-9e69-a2853a1f5169
code: |
  import numpy as np
  a = np.array([5,3,8,2,1])
  np.sum(a)
---
type: coding-question
id: c92ce426-73f3-470e-bc7a-25bdbbfab830
question: |
  For the array `a`, find the mean of the elements and save to `a_mean`.
code: |
  import numpy as np
  a = np.array([6,9,2,15,4])
tests: |
  assert a_mean == 7.2
--- |
  Some of the commonly used aggregation functions in numpy are np.sum, np.prod, np.mean, np.std, np.var, np.min, np.max, np.argmin, np.argmax, np.median, np.percentile.
---
type: live-code
id: 51d7310d-5e30-454d-adc3-3526c60c91f4
code: |
  np.random.seed(42)
  a = np.random.randint(0, 50, 10)
  print (a)
  print ('Index of maximum value in a:', a.argmax())
--- |
  There are aggregate functions for logical operations like `any` (tests whether any array elements along a given axis evaluate to True) and `all` (tests whether all array elements along a given axis evaluate to True.)
---
type: live-code
id: 8f2286bd-2a36-4e27-b6f2-00874aad41a3
code: |
  import numpy as np
  a = np.array([1,2,False,3])
  np.all(a)
--- |
  For multi dimensional arrays, the statistical functions have an optional axis parameter. If the axis is specified, the aggregation is performed along the specified axis.
---
type: live-code
id: 177da8ba-7e12-47cd-ab1d-8aff2beb3ff0
code: |
  a = np.arange(6).reshape(3,2)
  print('Array a:', a)
  # Row-wise mean of elements (axis 0)
  print('Row-wise mean:',np.mean(a, axis = 0))
  # Column-wise mean of elements (axis 1)
  print('Column-wise mean:', np.mean(a, axis = 1))
---
type: coding-question
id: 4e00f0ed-d2d5-4452-a906-fdf958a3c8b5
question: |
  Find the median of each column in the numpy array `a` and save the result to `a_median`.
code: |
  import numpy as np
  np.random.seed(5)
  a = np.random.randint(0, 50, 24).reshape(4,6)
tests: |
  assert np.array_equal(a_median, [25.5, 33. , 15.5, 14.5])
---
type: coding-question
id: 66d90378-93bd-45fe-96cc-93bb5382436f
question: |
  For the array `a`, compute the 50th percentile along axis 0 and store the result to `a_50`. Hint: look at [`np.percentile`](https://docs.scipy.org/doc/numpy/reference/generated/numpy.percentile.html).
code: |
  import numpy as np
  np.random.seed(5)
  a = np.random.randint(0, 50, 24).reshape(4,6)
tests: |
  assert np.array_equal(a_50, [16. , 20.5, 41.5, 21. , 32. , 19.5])
---
type: coding-question
id: b4e220d3-a22c-4f62-9b85-bd2363bd0773
question: |
  Compute the standard deviation of all the elements on the array `a`, round the result to 2 decimals and save to `a_std`. Hint: look at [`np.std()`](https://docs.scipy.org/doc/numpy/reference/generated/numpy.std.html) & [`np.round()`](https://docs.scipy.org/doc/numpy-1.15.1/reference/generated/numpy.around.html).
code: |
  import numpy as np
  np.random.seed(5)
  a = np.random.randint(0, 50, 24).reshape(4,6)
tests: |
  assert a_std == 14.69
---
type: coding-question
id: 1f63a867-2aa0-4600-865e-509b1aa430eb
question: |
  Find the index of the minimum value in the array `a` and save to `a_min_loc`. Hint: [`np.argmin()`](https://docs.scipy.org/doc/numpy-1.15.0/reference/generated/numpy.argmin.html).
code: |
  import numpy as np
  np.random.seed(25)
  a = np.random.randn(20)
tests: |
  assert a_min_loc == 8
---
