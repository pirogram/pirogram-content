title: One dimensional array
---
type: live-code
id: 3deb52e7-fbdd-4230-a9d3-3fc06c6b3a79
code: |
  import numpy as np
  a = np.array([1,2,3,4,5])
  a
---
type: live-code
id: d84409fe-7839-4ec0-a86e-d91cd23d8b4c
code: |  
  # Number of elements in a
  a.size
---
type: live-code
id: 6bd677a5-8d7e-4a3e-b5dd-716d8d7ce01f
code: |
  # Number of axes (dimensions) in a
  a.ndim
---
type: live-code
id: 524dc235-ad81-45e2-a3d8-b353af0dc48c
code: |
  # Size of an a in each dimension
  a.shape
---
type: live-code
id: d9a8d816-2e1e-4603-97f6-4779377d6b7e
code: |
  # Datatype of the elements of a
  a.dtype
---
type: testless-coding-question
id: 9c7f94b0-d13b-45ac-a872-9d6edd4af02d
question: |
  Use appropriate code to print dimension, shape, size and datatype of the following array a.
code: |
  import numpy as np
  a = np.array([1,2,3,4,5,6,7,8,9])
---
type: fill-in-the-blank-question
id: 45ca500e-3cdb-4d5f-9718-4a3e65389916
question: |
 Print the following the array and answer the questions.
code: |
  import numpy as np
  a = np.arange(10)
  a

blanks:
 - label: How many elements are in a?
   answer: 10
 - label: What is the rank(dimensions) of a?
   answer: 1
 - label: What is the shape of a?
   answer: (10,)
---
