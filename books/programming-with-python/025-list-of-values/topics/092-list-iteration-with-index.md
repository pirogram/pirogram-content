title: List Iteration With Index
--- |
  Another way to iterate through a list is to use the `enumerate()` function. Let's first understand what `enumerate()` does and then we'll see how it applies to various problems.

---
type: live-code
id: fa1625fb-b6ae-4fdc-83f9-3641cb83adac
code: |
  numbers = [7,   0, -18,   0,  16, -18,   8,  -4,  10, -18,  -9,  -9,  -2,
       2,  -2,  17, -20,  -5,  14, -16]

  for index, number in enumerate(numbers):
      print(index, '->', number)

--- |
  So, `enumerate(list)` gives us the list element as well as the index of the element. This is very useful if we want to update the list as we traverse through it. Let's say, we want to replace all -ve numbers in the list with 0. Here is how we can do it with `enumerate()`:
---
type: live-code
id: 81f9fd73-4281-4e70-81d2-3d5f752bb021
code: |
  numbers = [7,   0, -18,   0,  16, -18,   8,  -4,  10, -18,  -9,  -9,  -2,
       2,  -2,  17, -20,  -5,  14, -16]

  for index, number in enumerate(numbers):
      if number < 0:
          numbers[index] = 0

  print(numbers)

---
type: testless-coding-question
id: f214f62d-04e4-48c7-b046-d6fb4ab89adc
question: |
  You are given a list of numbers. Replace all numbers with their absolute value. You can use [`abs()`](https://docs.python.org/3/library/functions.html#abs) to get the absolute value of a number.
code: |
  numbers = [7,   0, -18,   0,  16, -18,   8,  -4,  10, -18,  -9,  -9,  -2,
         2,  -2,  17, -20,  -5,  14, -16]

  # your code goes here

---
type: testless-coding-question
id: ccaacc76-28e6-469c-89d8-e09ecc433649
question: |
  You are given a list of numbers but they are in `str` data type. Convert them to `int` data type.
code: |
  numbers = ['7', '0', '-18', '0', '16', '-18', '8', '-4', '10', '-18', '-9',
      '-9', '-2', '2', '-2', '17', '-20', '-5', '14', '-16']

---
type: testless-coding-question
id: 9083c875-e6a2-4d84-9580-27679bbf1493
question: |
  You are given a list of numbers. Convert all odd numbers to even by adding 1. For example: `[1, 2, 3]` becomes `[2, 2, 4]`.
code: |
  numbers = [7,   0, -18,   0,  16, -18,   8,  -4,  10, -18,  -9,  -9,  -2,
         2,  -2,  17, -20,  -5,  14, -16]

  # your code goes here
---
type: testless-coding-question
id: fbda9cf5-eeb5-4ab8-816e-13cddce1f34b
question: |
  You are given a list of numbers. Replace all numbers with their square. For example, `[1, 2, 3]` should become `[1, 4, 9]`.
code: |
  numbers = [7,   0, -18,   0,  16, -18,   8,  -4,  10, -18,  -9,  -9,  -2,
         2,  -2,  17, -20,  -5,  14, -16]

  # your code goes here

---
type: testless-coding-question
id: 5799cacf-7d92-401e-8d9f-e0b97afc39f1
question: |
  You are given a list of numbers. Print the sum of numbers that are on even index (i.e. 0, 2, 4 etc).
code: |
  numbers = [7,   0, -18,   0,  16, -18,   8,  -4,  10, -18,  -9,  -9,  -2,
         2,  -2,  17, -20,  -5,  14, -16]

  # your code goes here

---
type: testless-coding-question
id: f8fcc07c-c472-406b-a57f-a2efe9165137
question: |
  You are given a list of numbers. Replace the actual numbers by the running total. For example, if you are given `[2, 3, 6, 5]`, it should be become `[2, 5, 11, 16]`. Running total at a specific index is the sum of all numbers upto that index. For example, running total at index 0 would be `2`; at index 1, it would be `2 + 3 = 5`; at index 2, it would be `2 + 3 + 6 = 11`; at index, it would be `2 + 3 + 6 + 5 = 16`.
code: |
  numbers = [1, 2, 3, 4, 5, 6, 7]
