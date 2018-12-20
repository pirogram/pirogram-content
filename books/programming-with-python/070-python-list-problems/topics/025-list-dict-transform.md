title: List & Dict Transformation
---
type: testless-coding-question
id: bada537f-50c3-4f31-a3f3-5e52055a68a2
question: |
  Write a function that takes a dictionary as an argument. It flattens the dictionary into a list. For example, given `{'banana': 5, 'apple': 2, 'kiwi': 3}`, the function returns `['banana', 5, 'apple', 2, 'kiwi', 3]`.
code: |
  def dict_to_list( d):
    # your code goes here

---
type: testless-coding-question
id: 614d9e6e-8af7-40c1-a471-cda36d32b3c3
question: |
  Write a function that takes a dictionary as an argument. It flattens the dictionary into two lists: one for key and another for value. The index number for corresponding key & value must be the same. For example, given `{'banana': 5, 'apple': 2, 'kiwi': 3}`, the function returns `['banana', 'apple', 'kiwi']` and `[5, 2, 3]`.
code: |
  def dict_to_key_value_lists( d):
    # your code goes here

---
type: coding-question
id: 9f4efa2f-96fb-462d-ba84-12d116ea78f9
question: |
  Write a function that takes a list as an argument and converts it into a dictionary. The key & value in list alternate. For example, give a list `['banana', 5, 'apple', 2, 'kiwi', 3]`, the function returns `{'banana': 5, 'apple': 2, 'kiwi': 3}`.
code: |
  def list_to_dict( l):
    # your code goes here
tests: |
  assert list_to_dict(['a', 1, 'b', 2]) == {'a': 1, 'b': 2}

---
type: coding-question
id: bd826d77-1573-44ac-b724-acc9dd0265be
question: |
  Write a function that takes two lists as arguments and converts them into a dictionary. One list has dictionary keys and the other list has dictionary values. Corresponding keys & values are on the same index. For example, given `['banana', 'apple', 'kiwi']` and `[5, 2, 3]` as arguments, the function returns `{'banana': 5, 'apple': 2, 'kiwi': 3}`.
code: |
  def lists_to_dict(keys, values):
    # your code goes here
tests: |
  assert lists_to_dict(['a', 'b'], [1, 2,]) == {'a': 1, 'b': 2}

---
type: coding-question
id: e9b4a80d-c83a-4492-a395-0d07ea6d1dc0
question: |
  Write a function that takes a list of lists as an input and it flattens them into a single list. For example, given the following list:
  ```Python
  [
    [1, 2, 3],
    [4, 5, 6]
  ]
  ```
  the function returns the following list:
  ```Python
  [1, 2, 3, 4, 5, 6]
  ```
code: |
  def flatten_list( l):
    # your code goes here
tests: |
  assert flatten_list([[1, 2, 3], [4, 5, 6]]) == [1, 2, 3, 4, 5, 6]
