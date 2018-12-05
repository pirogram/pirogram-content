title: More on List Indexing
--- |
  The following code snippets show some of the basic functionality w.r.t. list indexing. Try changing the index numbers in the code to get a better feel. Also try some index numbers that are invalid (e.g. `100`) and see what happens.

---
type: live-code
id: 592d13b2-a79d-4647-9a4e-b26bfc3ccb32
code: |
  words = ['This', 'is', 'a', 'small', 'list', '.']

  # index starts from 0
  words[0]
---
type: live-code
id: 42f553c6-2d28-4e34-ad57-63beeac03db6
code: |
  words = ['This', 'is', 'a', 'small', 'list', '.']
  words[2]
---
type: live-code
id: 04101e97-1f6b-48a5-9e29-a75fa872a6dc
code: |
  words = ['This', 'is', 'a', 'small', 'list', '.']

  # -ve index numbers traverse the list in reverse direction
  words[-1]
---
type: live-code
id: 8358b439-dca2-40ee-80a4-ad5ed0fb64f9
code: |
  words = ['This', 'is', 'a', 'small', 'list', '.']
  words[-3]
---
type: live-code
id: d69ba413-bb97-44f7-b754-c699eaa83cca
code: |
  # you can also update list contents using index.
  numbers = [1, 2, 3, 4, 5]
  numbers[0] = 6
  numbers

---
type: live-code
id: 4c263082-470e-44a7-bc3e-5918a815866a
code: |
  # you can also use -ve indexing for updating a list.
  numbers = [1, 2, 3, 4, 5]
  numbers[-1] = 6
  numbers

---
type: categorization-question
id: 9f73ec0f-f252-42e8-889c-e9c4eb4ee827
question: |
  Select the correct answers from dropdown based on following list definition:

  ```python
  grocery_items = ['apple', 'orange', 'cabbage', 'okra', 'milk', 'eggs']
  ```
categories: ['apple', 'orange', 'cabbage', 'okra', 'milk', 'eggs']
mappings:
  "grocery_items[0]": apple
  "grocery_items[2]": cabbage
  "grocery_items[-1]": eggs
  "grocery_items[-5]": orange

---
type: categorization-question
id: 5c916d1b-70c2-4566-84bb-0662d13e5b5a
question: |  
  Select the correct answers from dropdown based on following list definition:

  ```python
  one_to_ten = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
  ```
categories: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 'Invalid']
mappings:
  "one_to_ten[4]": 5
  "one_to_ten[7]": 8
  "one_to_ten[10]": Invalid
  "one_to_ten[-3]": 8
  "one_to_ten[-10]": 1

---
type: categorization-question
id: c82a3b38-819b-4cba-a852-d5faa46c3edb
question: |  
  Select the correct answers from dropdown based on following code:

  ```python
  numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
  numbers[3] = 11
  numbers[-5] = 12
  ```
categories: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12]
mappings:
  "one_to_ten[3]": 11
  "one_to_ten[7]": 8
  "one_to_ten[5]": 12
  "one_to_ten[-3]": 8
  "one_to_ten[-7]": 11

---
type: categorization-question
id: 185f75b3-2ed7-4fec-a527-b99776ff14d0
question: |
  Select the correct answers from dropdown based on following list definition:

  ```python
  potterverse = ['Snape', 'Dumbledore', 'Harry', 'Hermione', 'Ron', 'He-Who-Cannot-Be-Named']
  ```
categories: [0, 1, 2, 3, 4, 5]
mappings:
  "What's the list index for Harry?": 2
  "What's the list index for Ron?": 4

---
type: categorization-question
id: 361ffb79-35fc-4680-b389-116a11d83dbd
question: |
  Select the correct answers from dropdown based on following code:

  ```python
  potterverse = ['Snape', 'Dumbledore', 'Harry', 'Hermione', 'Ron', 'He-Who-Cannot-Be-Named']

  potterverse[2] = 'Neville'
  potterverse[-2] = 'Sirius'
  ```
categories: [0, 1, 2, 3, 4, 5, 'Not In List']
mappings:
  "What's the list index for Harry?": "Not In List"
  "What's the list index for Ron?": "Not In List"
  "What's the list index for Sirius?": 4

---
type: categorization-question
id: b90bce07-fab1-4346-a0e3-9a75bd0cbbe9
question: |
  Select the correct answers from dropdown based on following list definition:

  ```python
  flowers = ['rose', 'lotus', 'lily', 'dahlia', 'daisy']
  ```
categories: [-1, -2, -3, -4, -5]
mappings:
  rose: -5
  dahlia: -2

---
type: testless-coding-question
id: b981a2ad-6819-4826-86a5-29ee1ebeb9a3
question: |
  Correct the `print` statement in the following code so that it prints `Harry Won Over He-Who-Cannot-Be-Named`.
code: |
  potterverse = ['Snape', 'Dumbledore', 'Harry', 'Hermione', 'Ron', 'He-Who-Cannot-Be-Named']

  print(potterverse[0], 'Won Over', potterverse[4])

---
type: testless-coding-question
id: 4d450c2c-75e0-46d5-bbf6-9176334e3e4b
question: |
  In the following code, add flower `petunia` to the list in such a way that the code prints 'I love petunia' instead of 'I love lily'. Note, you must not modify the `print` statement. Just modify the list definition.
code: |
  flowers = ['rose', 'lotus', 'lily', 'dahlia', 'daisy']

  print('I love', flowers[2])
