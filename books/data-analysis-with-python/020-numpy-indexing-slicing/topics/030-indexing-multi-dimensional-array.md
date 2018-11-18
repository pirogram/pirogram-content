title: Indexing Multi dimensional arrays
--- |
  Multi dimensional arrays can be accessed using `integer index` similar to that in one dimensional arrays. The difference being, they need to be indexed/sliced on each dimension by specifying the index at each dimension separated by commas.

  In the example given below, the rows of the `two_d_a` are the first dimension whereas the columns are the second dimension. To access the first element 1, we need an intersection at row `index 0` and column `index 0`.
---
type: live-code
id: c8a3d519-55b8-4f75-8d25-23b0429c20ca
code: |
  import numpy as np
  two_d_a = np.array([[1,2,3], [4,5,6]])
  two_d_a[0,0]
--- |
  The code below prints element at second row (`index 1`) and third column (`index 2`) from the array `two_d_a`
---
type: live-code
id: ad09ea3b-dbe8-4bf1-b5bb-24646d2f414a
code: |
  import numpy as np
  two_d_a = np.array([[1,2,3], [4,5,6]])
  two_d_a[1, 2]
---
type: multiple-choice-question
id: 40ff3bf1-ac45-4780-8d32-7fc9842287ab
question: |
  What would be the return value of the following code.
code: |
  import numpy as np
  two_d_a = np.array([[1,2,3], [4,5,6]])
  two_d_a[1,0]
options:
  - text: "1"
  - text: "2"
  - text: "4"
    correct: True
  - text: "5"
---
type: fill-in-the-blank-question
id: 59625036-ac51-4b28-8868-1f33b687ba1d
question: |
  Look at the two dimensional array given below and answer the questions.
code: |
  import numpy as np
  a = np.array([ [5,3,8,13,9,7], [2,12,4,16,19,15], [11,6,10,21,14,18] ])
  a
blanks:
- label: What element is present at a[1,4]?
  answer: 19
- label: What element is present at a[0,5]?
  answer: 7
- label: How will you access the element at the last row and the last column (18)?
  answer: a[2,5]
- label: What code would you use to get the number 21 which is the 4th element in the last row?
  answer: a[2,3]
--- |
  Indexing `Ndarrays` with more than two dimensions work in similar way, we need to specify the index at each `dimension` separated by commas.
---
type: coding-question
id: 36c87041-4629-4f13-9290-b232d7d170f2
question: |
  Here is a 3-D array of numbers 0 to 39. Print the array and write a code to access the number 20. Save to `number_twenty`.
code: |
  import numpy as np
  a = np.arange(40).reshape(5,4,2)
  # Your code goes here.
tests: |
  assert number_twenty == 20
---
type: testless-coding-question
id: eac220d7-3436-458e-82cc-6521cd7644c9
question: |
  Create a numpy array of random integers between 1 and 20 with shape (2,3,5). (Hint: look at random.randint). How would you access the last element?
code: |
  import numpy as np
  # Your code goes here.
---
