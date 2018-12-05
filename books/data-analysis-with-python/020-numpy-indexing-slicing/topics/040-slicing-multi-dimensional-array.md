title:  Slicing Multi dimensional arrays
--- |
  Slicing for multi dimensional arrays work in the similar way as that in one dimensional arrays. A slice is created by specifying the index slice at each dimension separated by commas.

  The code given below returns a slice of the `two_d_a` by selecting the first two elements at each dimension.
---
type: live-code
id: 3ee0fdcd-6fb1-4999-ae3a-4305dbdf31ed
code: |
  import numpy as np
  two_d_a = np.array([[1,2,3], [4,5,6], [7,8,9]])
  two_d_a[:2, :2]
--- |
  The index based slicing can be combined with : which selects all the elements at the specified dimension.
---
type: live-code
id: e8c4625a-d5cd-4a56-96d8-683a3342419b
code: |
  import numpy as np
  four_d_array = np.random.randint(10, 30, 40).reshape(2,5,2,2)
  print(four_d_array)
  print(four_d_array[1,:,:,:])
--- |
  One important distinction while selecting single row or column from an array is that integer index returns a one dimensional array whereas slice returns a two dimensional array.
---
type: live-code
id: 83a972c2-bc93-4be1-a06d-07fa017d35a4
code: |
  import numpy as np
  a = np.arange(12).reshape(4,3)
  print (a[3, :], a[3, :].shape)
  print (a[3:, :],a[3:, :].shape)
---
type: coding-question
id: 03843ad8-2e13-4d86-8149-ab43064a804f
question: |
  Create a slice
      ([[21, 22],
       [24, 25]])
      from the 3-D array given below and save to `a_slice`.
code: |
  import numpy as np
  a = np.arange(36).reshape(4,3,3)
  # Your code goes here.
tests: |
  assert np.array_equal(a_slice, [[21, 22],[24, 25]])
---
type: coding-question
id: fabce785-b952-4eb5-947c-2ddc8567dfe2
question: |
  Create a slice ([[ 3,  9, 15],
       [21, 27, 33]]) from the 4-D array given below and save to `a_slice`.
code: |
  import numpy as np
  a = np.arange(36).reshape(2,3,2,3)
  # Your code goes here.
tests: |
  assert np.array_equal(a_slice, [[ 3,  9, 15],[21, 27, 33]])
---  
type: coding-question
id: 2e05a863-ac4b-4525-88bf-88de1eaaaa35
question: |
  Split the following data into `train` and `test` by allocating last two rows to test and remaining to train.
code: |
  import numpy as np
  a = np.arange(24).reshape(8,3)
  # Your code goes here.
tests: |
  assert np.array_equal(train, [[ 0,  1,  2],[ 3,  4,  5],[ 6,  7,  8],[ 9, 10, 11],[12, 13, 14],[15, 16, 17]])
  assert np.array_equal(test, [[18, 19, 20],[21, 22, 23]])
---
type: coding-question
id: 79a78415-d549-4435-a2bf-7174c49938c5
question: |
  Split the following data into `features` and `label` by assigning the last column to label and remaining to features. Make sure that the shape of the label is (6,1) and not (6,).
code: |
  import numpy as np
  a = np.arange(24).reshape(6,4)
  # Your code goes here.
tests: |
  assert np.array_equal(features, [[ 0,  1,  2],[ 4,  5,  6], [ 8,  9, 10], [12, 13, 14],[16, 17, 18], [20, 21, 22]])
  assert np.array_equal(label, [[ 3],[ 7],[11],[15],[19],[23]])
--- |
  An additional dimension can be added to an existing Numpy array using `newaxis`. It is generally used with slicing at the position where the new dimension is required and creates an axis of length one. `newaxis` is an alias for ‘None’, and ‘None’ can be used in place of it with the same result.
---
type: live-code
id: bef69671-c8c5-40ce-b5d6-8d2ec4507f5d
code: |
  import numpy as np
  a = np.arange(5)
  print(a, a.shape)
  # Use all elements from the first dimension and add a second dimension.
  a = a[:, np.newaxis]
  print(a, a.shape)
---
type: live-code
id: cb3c01f4-782a-40dd-a43d-8812e1d1229e
code: |
  import numpy as np
  a = np.arange(5)
  print(a, a.shape)
  # Add multiple dimensions.
  a = a[np.newaxis, :, np.newaxis]
  print(a, a.shape)
---
