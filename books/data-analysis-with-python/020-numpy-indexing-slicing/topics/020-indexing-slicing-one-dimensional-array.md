title: Indexing and Slicing One dimensional arrays
--- |
  Lets look at the basic indexing in Numpy which is similar to Python indexing.
---
type: live-code
id: 4a43630c-d649-4ba2-96f5-5feb5f954920
code: |
  import numpy as np
  a = np.array([10, 20, 30, 40, 50])
  for index in range(len(a)):
    print ("Element at index",index, ':', a[index])
--- |
  We can select an element or slice of an array using the index. The notation is `array[index]`.
---
type: live-code
id: 0ccb90d8-67e4-4bad-a314-282eb81ba8ac
code: |
  import numpy as np
  a = np.array([10, 20, 30, 40, 50])
  # Select third element (element at index number 2)
  a[2]
--- |
  The basic syntax for slicing an array is `array[start:stop:step]`
---
type: live-code
id: d4246d23-542d-42f9-9f20-2f4904869277
code: |
  import numpy as np
  a = np.arange(10)
  # Create a slice of the array to return 4th, 5th and 6th elements.
  a[3:6]
--- |
  `Steps` can be used in conjunction with `start` or `stop` alone to return an array slice from the beginning or the end of the array with the specified step.
---
type: live-code
id: f4ce85bd-ce47-4924-9034-eb621770e81e
code: |
  import numpy as np
  a = np.arange(31)
  # Return every third element in the given array starting from 3.
  a[3::3]
--- |
   `Negative indices` are interpreted as counting from the end of the array. Negative `steps` go towards smaller indices.
---
type: live-code
id: 28d806e8-e681-4597-b76f-b0127c035b5d
code: |
  import numpy as np
  a = np.arange(10)
  a[-2:-10:-4]
---
type: coding-question
id: 37dd1c3d-572e-4d0c-9cbd-8b46f249fd7f
question: |
  Select the first 5 elements of the following array using `indexing` and save to `a_first_five`.
code: |
  import numpy as np
  a = np.arange(20)
tests: |
  assert np.array_equal(a_first_five, [0,1,2,3,4])
---
type: coding-question
id: 61ae6417-30ce-4e29-865e-6dfe7ed0d22e
question: |
  Select the last 5 elements of the following array using `negative indexing` and save to `a_last_five`.
code: |
  import numpy as np
  a = np.arange(30)
tests: |
  assert np.array_equal(a_last_five, [25, 26, 27, 28, 29])
---
type: coding-question
id: 7a92d1b9-b711-4c8b-9350-1d033331a2e1
question: |
  Select a slice of the following array using `steps` to return an array of positive numbers, exclude zero. Save to `a_pos`.
code: |
  import numpy as np
  a = np.array(25)
tests: |
  assert np.array_equal(a_pos, [ 2,  4,  6,  8, 10, 12, 14, 16, 18, 20, 22, 24])
---
type: coding-question
id: ae761ee0-e9fd-4651-b9dd-4aec2b32e9a4
question: |
  Here is an array of numbers from 130 to 0 in descending order. Return an array of ascending numbers in the table of 13 from the given array and save to `a_table_of_13`.
code: |
  import numpy as np
  a = np.arange(130,-1,-1)
tests: |
  assert np.array_equal(a_table_of_13 ,[ 13,  26,  39,  52,  65,  78,  91, 104, 117, 130])
---
