title: Index Based Iteration
--- |
  In the previous topic (i.e. list iteration), we first looked at the `while index < len(list)` way of iterating over the list items and then we looked at more idiomatic way of `for item in list`. To refresh your memory, here are the examples for finding the sum total of numbers in a list.
---
type: live-code
id: 71b0b81e-ab89-4f77-9afe-816e0645d5e9
code: |
  numbers = [9, 2, 34, 2, 7, 8, 23, 4, 9]

  index = 0
  total = 0
  while index < len(numbers):
    total += numbers[index]
    index += 1

  print('Total:', total)

---
type: live-code
id: eef14f6d-1c1f-4eb9-b034-72d3e4d1a1f3
code: |
  numbers = [9, 2, 34, 2, 7, 8, 23, 4, 9]

  total = 0
  for num in numbers:
    total += num

  print('Total:', total)

--- |
  Both do the same thing but the latter is more concise, more elegant and I would argue more intuitive. However, the former is more general purpose and there is a class of problems that can be solved only when you iterate based on the index. Especially when you want to transform the values in a list, you must iterate with the index.

  Let's look at an example problem. You are given a list of numbers and you want to set all -ve numbers to `0`.
---
type: live-code
id: c87650da-9ccd-4008-a698-fbe816d413c1
code: |
  numbers = [7,   0, -18,   0,  16, -18,   8,  -4,  10, -18,  -9,  -9,  -2,
         2,  -2,  17, -20,  -5,  14, -16]

  index = 0
  while index < len(numbers):
    if numbers[index] < 0:
      numbers[index] = 0

    index += 1

  print(numbers)
--- |
  In this example, we must iterate using the index (rather than `for item in list:`) because what we need to do on line number 7: `numbers[index] = 0`. If we don't know the index of the -ve number, we cannot replace it with `0` in the list. Right?

  Let's look at another example. This time, we want to replace the numbers by their absolute value (i.e. `-7` becomes `7`).
---
type: live-code
id: 80df67a5-91ed-4ab1-82ac-adf3e77e922c
code: |
  numbers = [7,   0, -18,   0,  16, -18,   8,  -4,  10, -18,  -9,  -9,  -2,
         2,  -2,  17, -20,  -5,  14, -16]

  index = 0
  while index < len(numbers):
    numbers[index] = abs(numbers[index])

    index += 1

  print(numbers)
--- |
  [`abs()`](https://docs.python.org/3/library/functions.html#abs) gives the absolute value of a number. In this example, we again need the index so that we can replace the item within the list.

  We'll now look at an alternate technique to solve these problems without using the `while` loop. Let's start with the first example: set all -ve numbers to `0`.

---
type: live-code
id: 59fce163-6ab2-4cc1-b420-0eab611c027d
code: |
  numbers = [7,   0, -18,   0,  16, -18,   8,  -4,  10, -18,  -9,  -9,  -2,
         2,  -2,  17, -20,  -5,  14, -16]

  for index in range( len(numbers) ):
    if num < 0:
      numbers[index] = 0

  print(numbers)
--- |
  `range()` effectively gives us a sequence of numbers that starts with 0 and goes upto 1 less than the argument given to it. For example, `range(9)` would give us the sequence [0, 1, 2, 3, 4, 5, 6, 7, 8]. On the other hand, `range(2, 9)` would give us the sequence [2, 3, 4, 5, 6, 7, 8]. So, the way you can read this code is that you are iterating through the sequence of index numbers for the list.

  Here is a quick way of seeing what `range()` is doing:
---
type: live-code
id: 6fa9c327-aefa-416a-85c4-e72ef4cf8aae
code: |
  for index in range(9):
    print(index)
---
type: live-code
id: e50fe514-ee1e-4f20-b196-286954388bc9
code: |
  for index in range(2, 9):
    print(index)

---
type: testless-coding-question
id: 2a9f8cb1-773c-40bd-9482-bdb52e870951
question: |
  You are given a list of numbers. Replace all numbers with their absolute value. Perform index based iteration using `for in range(len(list)):` approach. You can use [`abs()`](https://docs.python.org/3/library/functions.html#abs) to get the absolute value of a number.
code: |
  numbers = [7,   0, -18,   0,  16, -18,   8,  -4,  10, -18,  -9,  -9,  -2,
         2,  -2,  17, -20,  -5,  14, -16]

  # your code goes here

---
type: testless-coding-question
id: f0220bdc-045a-468c-b9a9-296d139594df
question: |
  You are given a list of numbers. Convert all odd numbers to even by adding 1. For example: `[1, 2, 3]` becomes `[2, 2, 4]`.
code: |
  numbers = [7,   0, -18,   0,  16, -18,   8,  -4,  10, -18,  -9,  -9,  -2,
         2,  -2,  17, -20,  -5,  14, -16]

---
type: testless-coding-question
id: 55db8dd0-6e93-4ba6-b8f5-ab59332c2fbd
question: |
  You are given a list of numbers but they are in `str` data type. Convert them to `int` data type.
code: |
  numbers = ['7', '0', '-18', '0', '16', '-18', '8', '-4', '10', '-18', '-9',
      '-9', '-2', '2', '-2', '17', '-20', '-5', '14', '-16']

---
type: testless-coding-question
id: 8cfeb274-a82d-4b4e-9133-7c9ef0bc2f98
question: |
  Print a list of items in reverse order. You would need to start from last index and go all the way to index 0.
code: |
  fruits = ['apple', 'banana', 'peach', 'pineapple', 'kiwi']

---
type: testless-coding-question
id: f8fcc07c-c472-406b-a57f-a2efe9165137
question: |
  You are given a list of numbers. Replace the actual numbers by the running total. For example, if you are given `[2, 3, 6, 5]`, it should be become `[2, 5, 11, 16]`. Running total at a specific index is the sum of all numbers upto that index. For example, running total at index 0 would be `2`; at index 1, it would be `2 + 3 = 5`; at index 2, it would be `2 + 3 + 6 = 11`; at index, it would be `2 + 3 + 6 + 5 = 16`.
code: |
  numbers = [1, 2, 3, 4, 5, 6, 7]

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
