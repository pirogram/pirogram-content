title: Array Creation
--- |
  Array can be created from a python list or using various functions
---
type: live-code
id: 3bed0b9e-0522-40f3-9ed4-ce3d48c03b30
code: |
  # Array from a list of lists
  import numpy as np
  a = np.array([[1,2], [3,4], [5,6]])
  a
---
type: live-code
id: ab8853a0-b3ed-4ba8-8bcb-39a94960699c
code: |
  # Array using function arange ([start], stop, [step])
  import numpy as np
  a = np.arange(0,10,2)
  a
---
type: live-code
id: 989a90f7-2a9b-43d8-aade-3bb15c9c5a2e
code: |
  # Array with all zeroes
  import numpy as np
  a = np.zeros(2)
  a
---
type: live-code
id: 942b1109-7e3c-4058-9531-996b9c61d396
code: |
  # Array of random numbers of shape (2,3)
  import numpy as np
  a = np.random.random((2,3))
  a
---
type: fill-in-the-blank-question
id: fa868593-300c-4c3a-9aca-9e23430ec0ee
question: |
  Create an array from the nested list given below and answer the questions.
code: |
  import numpy as np
  l = [[1,2], [3,4], [5,6], [7,8]]
blanks:
 - label: How many elements are in a?
   answer: 8
 - label: What is the rank(dimensions) of a?
   answer: 2
 - label: What is the shape of a?
   answer: (4,2)
---
type: fill-in-the-blank-question
id: 5cbac918-4592-48f1-b4f1-b5b9fcc158d5
question: |
  Create an array from nested list below and answer the questions.
code: |
  import numpy as np
  l = [[[1,2], [3,4]], [[5,6], [7,8]]]

blanks:
 - label: How many elements are in a?
   answer: 8
 - label: What is the rank(dimensions) of a?
   answer: 3
 - label: What is the shape of a?
   answer: (2,2,2)
---
type: coding-question
id: 4c5bed66-685d-480d-b30d-0e7e64608799
question: |
  Create an array of numbers from 0 to 20 using function `arange` and store in variable `a`. What is the size of the a?
code: |
  import numpy as np
tests:
  assert a.size == 21  
---
type: coding-question
id: 7c960373-688c-48e5-bce2-59a2da8b4e45
question: |
  Create an array starting with 3 incrementing by 3 with total size 10.
code: |
  import numpy as np
tests:
  assert np.array_equal(a, [ 3,  6,  9, 12, 15, 18, 21, 24, 27, 30])
---
type: testless-coding-question
id: a86a278f-e131-4e8b-a72b-4b4508e3a367
question: |
  Create a (4,5) array with all ones.
code: |
  import numpy as np
---
type: testless-coding-question
id: 951e3c6b-2cf2-408d-9189-1acd2f4bf4f8
question: |
  Create a 4-D array of random numbers with shape (2,3,4,5) and print it.
code: |
  import numpy as np
---
