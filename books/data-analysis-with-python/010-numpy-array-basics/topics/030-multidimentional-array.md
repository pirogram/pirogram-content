title: N-dimensional Array
--- |
  N-dimensional array (ndarray) is a multidimensional container of items of same type. Look at the size of each dimension by printing array.shape, which returns the shape as a tuple of positive integers
---
type: live-code
id: 96f22101-99e0-43c1-86ce-99cc5ce0c26a
code: |
  # Here is a 2 dimensional array of shape (2,3)
  import numpy as np
  a = np.array([[1, 2, 3],
       [4, 5, 6]])
  a
---
type: live-code
id: 241f8741-eb4a-4110-8ef3-151e6ce0ea63
code: |
  import numpy as np
  a = np.array([[1, 2, 3],
       [4, 5, 6]])
  print("Number of dimensions:", a.ndim)
---
type: live-code
id: 3b00e4d3-a2aa-4b09-baf8-83d306e42250
code: |
  import numpy as np
  a = np.array([[1, 2, 3],
       [4, 5, 6]])
  print("Shape:", a.shape)
---
type: testless-coding-question
id: 8a6d4851-2212-43d1-8d62-a647ee271f21
question: |
  What is the shape and number of dimensions of the following array? Try out with your code in the box.
code: |
  import numpy as np
  a = np.arange(20).reshape(5,4)
---
type: fill-in-the-blank-question
id: b0519ab7-4a71-4e6d-86bc-02d877737eff
question: |
  Look at the array and use appropriate methods to answer the following questions.
code: |
  import numpy as np
  a = np.arange(24).reshape(3,4,2)
  a
blanks:
 - label: How many elements are in a?
   answer: 24
 - label: What is the rank(dimensions) of a?
   answer: 3
 - label: What is the shape of a?
   answer: (3,4,2)
--- |
  Just the way one dimensional arrays can be created from lists; multidimensional arrays can be created from nested lists.
---
type: testless-coding-question
id: 4d1c8071-04f7-4a93-bb8e-667619172c40
question: |
  Create a 2-d array from the nested list given below. Print the number of dimensions and shape.
code: |
  import numpy as np
  l = [[1,2,3,4], [10,20,30,40], [100,200,300,400]]
---
type: fill-in-the-blank-question
id: 2d5be2dc-5500-45fe-aaaf-7d2ecdf911aa
question: |
 Look at the ndarray and answer the following questions.
code: |
  import numpy as np
  a = np.array([[[ 0,  1],
        [ 2,  3]],

       [[ 4,  5],
        [ 6,  7]],

       [[ 8,  9],
        [10, 11]]])
  a
blanks:
 - label: What is the rank(dimensions) of a?
   answer: 3
 - label: What is the shape of a?
   answer: (3,2,2)
---
