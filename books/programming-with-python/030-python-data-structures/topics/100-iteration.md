title: Iteration
--- |
  You can iterate over any _sequence-like_ data structure using `for .. in` syntax. It looks like the following:

  ```python
  for item in sequence:
    # do something with item.
  ```

  For `list`, `tuple` and `set`, it looks exactly the same.

---
type: live-code
id: 4163bfdf-21c1-4cba-aa86-5f0ae9e275e2
code: |
  fruits = ['apple', 'orange', 'banana', 'pineapple']

  for fruit in fruits:
    print(fruit)

--- |
  For `dict`, the usual iteration is on the keys of dictionary.

---
type: live-code
id: 5b41e707-18f3-4ccb-82c2-ca4868e731e3
code: |
  fruits = {'apple': 4, 'orange': 3, 'banana': 3, 'pineapple': 1}

  # iteration here is on the keys of dict. You could also write it as
  # for fruit_name in fruits.keys():
  #   print(fruit_name, ':', fruits[fruit_name])

  for fruit_name in fruits:
    print(fruit_name, ':', fruits[fruit_name])

--- |
  There are two more common patterns around iterating over `list` or `dict` that we must study. One is around iterating over `(key, value)` tuples of a `dict`.

---
type: live-code
id: 83802d12-39be-4684-9ad5-5924d3c9d86f
code: |
  fruits = {'apple': 4, 'orange': 3, 'banana': 3, 'pineapple': 1}

  # Each item here is a (key, value) tuple.
  for fruit_name, quantity in fruits.items():
    print(fruit_name, ':', quantity)

--- |
  Another is about iterating over the range of a list's index.

---
type: live-code
id: 76fa126f-afd2-4d50-a80e-a4373d8c864a
code: |
  fruits = ['apple', 'orange', 'banana', 'pineapple']

  for index in range(0, len(fruits)):
    print(fruits[index])

--- |
  Index based iteration on a `list` is particularly useful when you want to modify the `list`. For example, let's write a program that converts all odd numbers in a list to next even number.

---
type: live-code
id: 98d174f4-c259-4939-b62d-9ab2eac5a41c
code: |
  numbers = [0, 1, 2, 3, 4, 5, 6]

  for index in range(0, len(numbers)):
    if numbers[index]%2 == 1:
      numbers[index] += 1

  numbers

---
type: testless-coding-question
id: b3e2de9d-7ccb-4ad6-b03a-ab12a609c024
question: |
  Write the code to print the sum total of all odd and even numbers from a list of numbers. For example, if the list is `[1, 3, 9, 4, 7, 8]`, the output from the program would be:

  ```
  Sum of odd numbers: 20
  Sum of even numbers: 12
  ```
code: |
  numbers = [9, 2, 42, 3, 5, 11, 6]

  # your code goes here

---
type: testless-coding-question
id: 4476053a-a2c9-4b0c-8ace-2e9e0d18ac1c
question: |
  Keep asking the user to enter a number till the user enters 0. Now, print the sum total of all distinct odd and distinct even numbers.
code: |
  # your code goes here

---
type: testless-coding-question
id: ffa0f655-a409-4f90-9a94-335009845e1a
question: |
  Keep asking the user to enter a number till the user enters 0. Now, print the count of single digit numbers entered by the user. If the user entered `1 11 23 4`, your program should print `2`.
code: |
  # your code goes here.
---
type: testless-coding-question
id: 6ddf32f9-5169-42a3-a3f2-478093368889
question: |
  Keep asking the user to enter a number till the user enters 0. Now, print the count of distinct numbers that are multiples of 10. For example, if the user entered `40 50 40 90 42`, the program will print 3 (since the distinct numbers are `40 50 90 42`).
code: |
  # your code goes here.

---
type: testless-coding-question
id: 5fad5fa5-d467-4c3d-bdf8-c5b1b511f226
question: |
  Write the code to update a given list so that each number in the list gets replaced by the square of that number. Example: the list `[1, 2, 3]` should become `[1, 4, 9]`.
code: |
  numbers = [2, 3, 4, 5, 6]

  # your code goes here

---
type: testless-coding-question
id: 642ca429-7fea-4db2-855e-8d343954dbbf
question: |
  Write the code to update a given list so each odd number gets replaced by `1` and each even number gets replaced by `0`. Example: `[3, 2, 9, 4]` becomes `[1, 0, 1, 0]`.
code: |
  numbers = [42, 2, 9, 3, 21, 4]

  # your code goes here

---
type: testless-coding-question
id: 8f9554c0-bfa5-4e2a-a2ed-07ef8ec0fd12
question: |
  Write the code to update a given list such that each multiple of `3` gets replaced by `3`. For example, `[3, 6, 9, 2, 4]` becomes `[3, 3, 3, 2, 4]`.
code: |
  numbers = [3, 6, 9, 2, 4]

  # your code goes here

---
type: testless-coding-question
id: d1b8fad5-9e16-44c3-8572-0a421454d6c2
question: |
  Given two lists, write the code to identify elements present in both the lists and print them.
code: |
  l1 = [0, 1, 2, 3, 4, 5, 6]
  l2 = [2, 4, 6, 8, 10, 12]

  # your code goes here

---
type: testless-coding-question
id: 2b953272-991a-49ac-b407-a829a394911a
question: |
  Update the quantity of grocery items so that anything that's 0 becomes 1.
code: |
  grocery_items = {
    "milk": 0,
    "eggs": 24,
    "bread": 1,
    "cheese": 0
  }

  # your code goes here.

---
type: testless-coding-question
id: a59e94d1-f5a0-474b-9df9-54d1c6739b17
question: |
  Given two dictionaries of grocery items, create a third dictionary that has the items from both the dictionaries. For example: given `{'milk': 1, 'eggs': 6}` and `{'bread': 3, 'cheese': 12}`, create a new dictionary `{'milk': 1, 'eggs': 6, 'bread': 3, 'cheese': 12}`
code: |
  d1 = {'milk': 1, 'eggs': 6, 'cheerios': 1}
  d2 = {'bread': 3, 'cheese': 12, 'salsa': 2}

  # your code goes here.

---
type: testless-coding-question
id: 3a96176c-6bd5-4105-9c87-69ba64bfeaa8
question: |
  Given two dictionaries of grocery items, create a third dictionary that has items from the both the dictionaries. If an item is found in both the dictionaries, add up the quantity in the resulting dictionary. For example, if you are given `{'bread': 1, 'eggs': 6}` and `{'cheese': 12, 'eggs': 12}`, the resulting dictionary is `{'bread': 1, 'eggs': 18, 'cheese': 12}`.
code: |
  d1 = {'milk': 1, 'eggs': 6, 'cheerios': 1, 'cheese': 6, 'bread': 1}
  d2 = {'bread': 3, 'cheese': 12, 'salsa': 2, 'eggs': 12}

  # your code goes here
