title: Element wise operations between arrays and scalars
---
  Element wise operations between multiple arrays is possible only when the arrays are of the same dimension. Arithmetic operation between an array and a scalar can be performed due to the Broadcasting.
---
  To multiply each element of the array `a` by 100, we can multiply `a` with 100 rather than multiplying it with [100, 100, 100, 100].
---
type: live-code
id: fcdad7a2-ce64-4687-9776-d0ed5a05a18b
code: |
  import numpy as np
  a = np.array([1,2,3,4])
  a * 100
--- |
  The element-wise operations work on multi dimensional arrays in the similar way.
---
type: live-code
id: d1ee49db-d3dd-4354-b18b-9ce6e579d71f
code: |
  a = np.array([[1,2], [3,4]])
  # Add 100 to every element of `a` and then divide by 10
  (a + 100)/10
---
type: coding-question
id: 91156df9-2079-44cc-95a9-9bab15d90f3e
question: |
  Here is a numpy array `n` of numbers from 1 to 10. Find the square of each element of `n` and return in the array `n_sqr`.
code: |
  import numpy as np
  n = np.arange(1,11)
tests: |
  assert np.array_equal(n_sqr, [  1,   4,   9,  16,  25,  36,  49,  64,  81, 100])
---
type: coding-question
id: 6b4b2710-6260-44cb-b3b4-cc2de8cc0301
question: |
  For the given numpy array `celsius`, convert each value to fahrenheit and save to array `fahrenheit`. The formula for conversion is F = C * 9/5 + 32.
code: |
  import numpy as np
  celsius = np.array([100, 0, 32, -32])
tests: |
  assert np.array_equal(fahrenheit, [212. ,  32. ,  89.6, -25.6])
---
type: coding-question
id: 7558f9e7-11df-4380-a6a2-b780945bea22
question: |
  The arrays `oz` given below contains the weight in ounces. Convert them to weight in pounds and save to a new array `lb`. Remember, 1 pound = 16 ounces.
code: |
  oz = np.array([16, 200, 256, 0, 1000])
tests: |
  assert np.array_equal(lb, [ 1. , 12.5, 16. ,  0. , 62.5])
---
type: coding-question
id: 93fb2b44-38e3-47dc-b95a-d28cdf60a11c
question: |
  Raise 2 to the power of numbers given in the array `pow` and return the result in `array_2048`.
code: |
  import numpy as np
  pow = np.arange(1, 12)
tests: |
  assert np.array_equal(array_2048, [   2,    4,    8,   16,   32,   64,  128,  256,  512, 1024, 2048])
---
