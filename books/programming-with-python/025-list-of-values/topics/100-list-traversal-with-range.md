title: List Traversal With Range
--- |
  Using a neat trick, we can combine the _sequence of numbers_ using `range()` and list traversal. Here is a quick example:

---
type: live-code
id: b76ae2e8-7fd1-4fed-af77-90cec22b4a29
code: |
  numbers = [7,   0, -18,   0,  16, -18,   8,  -4,  10, -18,  -9,  -9,  -2,
       2,  -2,  17, -20,  -5,  14, -16]

  for index in range( len(numbers) ):
      print(index, '->', numbers[index])
--- |
  The function `range( len(numbers) )` gives us a sequence of numbers starting from `0` to one less than the length of list. By using this sequence of numbers as the index, we can traverse the list.

  We could have done the same using good old `while` as well:
---
type: live-code
id: 61ee7f7a-d101-4441-9f11-73f7e2788eb5
code: |
  numbers = [7,   0, -18,   0,  16, -18,   8,  -4,  10, -18,  -9,  -9,  -2,
         2,  -2,  17, -20,  -5,  14, -16]

  index = 0
  while index < len(numbers):
      print(index, '->', numbers[index])
      index += 1

  print(numbers)
--- |
  Both these examples have the same effect. Using `range()` function, we get a more compact expression.
---
type: testless-coding-question
id: c56b6531-e960-42d1-b68f-6b1d92b73f0b
question: |
  You are given a list of numbers. Print the numbers from index 3 to index 7.
code: |
  numbers = [7,   0, -18,   0,  16, -18,   8,  -4,  10, -18,  -9,  -9,  -2,
       2,  -2,  17, -20,  -5,  14, -16]

  # your code goes here

---
type: testless-coding-question
id: 8cfeb274-a82d-4b4e-9133-7c9ef0bc2f98
question: |
  Print a list of items in reverse order. You would need to start from last index and go all the way to index 0.

code: |
  fruits = ['apple', 'banana', 'peach', 'pineapple', 'kiwi']

---
type: testless-coding-question
id: 02814b8b-c9d3-4eef-90a8-1aa637e66994
question: |
  You are given a list of numbers. Write a program to reverse the order of numbers within the list. For example, `[1, 2, 3, 4]` should become `[4, 3, 2, 1]`.

  Hint: we need to work with swapping the numbers at first and last index, second and second last index, so on so forth. How to swap the positions of two items in a list? Here is an example:
  ```python
  list[some_index], list[another_index] = list[another_index], list[some_index]
  ```
code: |
  numbers = [1, 2, 3, 4, 5, 6, 7, 8]
