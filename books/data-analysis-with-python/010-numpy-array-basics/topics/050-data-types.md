title: Data Types
--- |
  NumPy supports a much greater variety of numerical types. There are 5 basic numerical types representing `booleans` (bool), `integers` (int), `unsigned integers` (uint), `floating point` (float) and `complex`. Those with numbers in their name indicate the `bitsize` of the type (Number of bits needed to represent a single value in memory). Print `np.sctypes` to see the all the supported types.  
---
type: live-code
id: 0fa8a567-b499-4d17-8d5d-2a805f2bd520
code: |
  import numpy as np
  np.sctypes
--- |
  You can create an array of required type by specifying the `dtype` while creating the array.
---
type: live-code
id: 09083caa-98a8-472c-8c02-fa683f2501d7
code: |
  import numpy as np
  a_uint = np.array([1,2,3,4,5], dtype = 'uint')
  a_uint.dtype
---
type: live-code
id: cfa92726-3080-4d2c-9f12-6edcb581dc00
code: |
  import numpy as np
  a_bool = np.array([1,0,0,1,0], dtype = 'bool')
  print(a_bool)
  print(a_bool.dtype)
---
type: coding-question
id: ad73f1d1-bcb5-4a88-b617-724065f4f47b
question: |
  Create an array of type `float32` from the list given below and save it to `a_float`.
code: |
  import numpy as np
  l = [1,2,3]
  # Your code here
tests: |
  assert a_float.dtype == 'float32'
--- |
  String Arrays:
  Numpy requires `string` arrays to have a fixed maximum length. When you create an array, numpy sets the length based on the maximum length of the strings passed. Check the `dtype` of the array to see the maximum length. Subsequent assignments into the array are truncated to fit this `dtype`.
---
type: live-code
id: fefe4862-6c81-4dc3-9b29-1a23f2a4074a
code: |
  # Here is an array of strings.
  import numpy as np
  a_str = np.array(['a', 'abcdef', 'abc', 'abcd', 'abcdefghi', 'ab'])
  print("Array:", a_str)
  print("Array datatype:", a_str.dtype)
--- |
  Create an array of `strings` and replace the first element. Print the array and `dtype`. Since the maximum length is set to 9 characters, the new string gets truncated to 9. The solution would be to create the array with dtype = <U26 which will support strings up to 26 characters.
---
type: live-code
id: ddfda963-c9f3-401b-91c7-486c3ebf4fe7
code: |
  import numpy as np
  a_str = np.array(['a', 'abcdef', 'abc', 'abcd', 'abcdefghi', 'ab'])
  a_str[0] = 'abcdefghijklmnopqrstuvwxyz'
  print("Array:", a_str)
  print("Array datatype:", a_str.dtype)
---
type: testless-coding-question
id: 4b665dbc-3f6a-4b25-848c-a08b2143639d
question: |
  Create an array from the list given below and store in `array_city`. Now check the data type of `array_city`.
code: |
  import numpy as np
  l = ['London', 'New York', 'Boston']
  # Your code here
---
type: testless-coding-question
id: 1e4a5850-dfb7-409f-baa4-f836f0298015
question: |
  Create an array from the list given below and store in `array_city`. Assign 'San Fransisco' to the first element of `array_city`. Print the array, is San Fransisco truncated?
code: |
  import numpy as np
  l = ['London', 'New York', 'Boston']
---
type: coding-question
id: db5bc008-ba6b-425e-b6cd-cc6c7f5c20b1
question: |
  Create an array `array_city` from the list given below by specifying the `dtype` such it supports the length of up to 20 characters.
code: |
  import numpy as np
  l = ['London', 'New York', 'Boston']
  # Your code goes Here
tests: |
  array_city[0] =  'San Fransisco'
  assert array_city[0] ==  'San Fransisco'
---
