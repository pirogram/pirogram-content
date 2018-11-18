title: Data Type Conversion
--- |
  `Numpy.array` provides an optional parameter `dtype` to specify the desired datatype for the array. If not given, the type will be determined as the minimum type required to hold the objects in the sequence. It can only be used to upcast the array. The method .astype() is used to downcast the arrays.
---
type: live-code
id: 28348e03-3e9e-485e-b2f5-3af93501f0ef
code: |
  # Numpy infers the datatype of the following array as `float` because that is the minimum type to support the last value 5.0.
  import numpy as np
  a_num = np.array([1,2,3,4,5.0])
  a_num.dtype
---
type: live-code
id: b6876100-bc51-493f-b55d-4eae28ea3732
code: |
  # Numpy infers the datatype of the following array as `<U1` because that is the minimum type to support the character length.
  a_str = np.array(['a', 'b', 'c'])
  a_str.dtype
---
type: coding-question
id: 8fee4e1b-53de-4709-8b68-ceb4ae56c773
question: |
  Create an array of type `float32` (upcasting) from the list and save to `a_num`.
code: |
  import numpy as np
  l = [1,2,3,4,5]
tests: |  
  assert a_num.dtype == 'float32'
--- |
  The array can be converted to a different `dtype` using the method .astype(). It returns a new array and needs to be assigned to a variable.
---
type: live-code
id: 6b77f4af-3ced-4927-8f8d-2793fb7ef483
code: |
  # The array of `floats` with type `int16` (downcasting)
  import numpy as np
  a_num = np.array([1.0,2.5,3.3,4.2,5.0])
  a_num = a_num.astype('int16')
  a_num
--- |
  Downcasting `integers` returns unexpected value and one has to be careful with those operations.
---
type: live-code
id: 2cd14b9a-9c48-4d0e-858b-6f58b9076707
code: |
  # Downcasting `integers`
  a_num = np.array([12345678910])
  a_num.astype('int32')
---
type: coding-question
id: 67c810f0-7e30-4ef5-956f-ceed44295683
question: |
  Convert the following array so that it supports a string with upto 10 character length.
code: |
  import numpy as np
  a_str = np.array(['a', 'b', 'c'])
tests: |
  a_str[2] = 'new_string'
  assert a_str[2] ==  'new_string'
---
type: coding-question
id: aaf32ade-d992-460f-bee2-5f88cb45fe10
question: |
  Convert the `dtype` of the 2-D array of ones from `float64` to `int64`.
code: |
  import numpy as np
  a_ones = np.ones((2,3))
tests: |
  assert a_ones.dtype == 'int64'  
