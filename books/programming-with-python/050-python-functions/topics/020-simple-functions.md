title: Simple Functions
--- |
  The goal of this exercise set is to get you comfortable with the syntax of writing functions. In fact, for those who are new to programming, the goal is to get you comfortable with this whole idea of writing functions.

  As a first step, we'll try to replicate some of the built-in functions in Python that you may have already used by now.

  ## `sum()`

  We'll start with replicating the function `sum()`. Here is a sample usage:
---
type: live-code
id: 54c97f93-7d04-4edb-a24c-95a3983665da
code: |
  numbers = [1, 2, 3, 4]
  total = sum(numbers)
  total

--- |
  This is how we can implement our own `sum()` function:

---
type: live-code
id: 3a2ba4a1-267a-4d71-9068-c239aa97a837
code: |
  def my_sum(numbers):
    sum_total = 0
    for num in numbers:
      sum_total += num

    return sum_total

  total = my_sum([1, 2, 3, 4])
  total

--- |
  ## `max()`

  `max()` gives us the largest item from a sequence of items. Here is a sample usage:
---
type: live-code
id: f9d778b0-25da-404f-a1bb-b9ecf53bab23
code: |
  max_num = max([4, 32, 1, 23, 18, 9])
  max_num

--- |
  Let's implement our own simplistic version of `max()` function:

---
type: live-code
id: fe622be5-4bdf-4bed-bc0a-0277e1baf0a8
code: |
  def my_max(items):
    largest = items[0]
    for item in items[1:]:
      if largest < item:
        largest = item

    return largest

  max_num = my_max([4, 32, 1, 23, 18, 9])
  max_num

---
type: coding-question
id: 1c4661ac-4049-40ca-a4f2-e5ec5472132f
question: |
  Write a function `diff(a, b)` that takes two numbers as arguments. It returns the difference between two numbers. Note: either of the number could be smaller but the difference will always be +ve. For example, the `diff(1, 3)` as well as `diff(3, 1)` should return `2`.
code: |
  # your code goes here

tests: |
  assert diff(1, 3) == 2
  assert diff(-1, -3) == 2

---
type: coding-question
id: 5de6958e-bcf3-4ff6-b081-4bd0b6e78485
question: |
  Write a function `mean(a, b, c)` that takes three numbers as arguments. It returns the mean value (aka average value) of these numbers.
code: |
  # your code goes here

tests: |
  assert mean(1, 2, 3) == 2
  assert mean(3, 4, 5) == 4

---
type: coding-question
id: dcdcaeda-48b7-464b-b1d5-0122cf22ad14
question: |
  Write a function `compare(a, b)` that returns `-1` if a is smaller, `1` if a is bigger and `0` if both the numbers are same.
code: |
  # your code goes here

tests: |
  assert compare(1, 3) == -1
  assert compare(3, 1) == 1
  assert compare(2, 2) == 0

---
type: coding-question
id: e8d93ae8-f22f-4b8e-a154-b62ba01f34db
question: |
  Write a function `fizzbuzz(number)` that takes a number as an input. If the number is divisble by 3, it returns `'Fizz'`. If the number is divisible by 5, it returns `'Buzz'`. If the number is divisible by 3 and 5, it returns `'FizzBuzz'`. Otherwise, it returns the input number itself.
code: |
  # your code goes here

tests: |
  assert fizzbuzz(1) == 1
  assert fizzbuzz(6) == 'Fizz'
  assert fizzbuzz(15) == 'FizzBuzz'
  assert fizzbuzz(10) == 'Buzz'

---
type: coding-question
id: 2cfe7051-f012-41b9-b8bd-4854364346d0
question: |
  Write a function `min_number()` that takes a list of numbers as argument and returns the smallest number from that list.
code: |
  # your code goes here
tests: |
  assert min_number([243, 34, 21, 92]) == 21
  assert min_number([4, 23, 1, 4, 9]) == 1

---
type: coding-question
id: eb6d7e81-493a-451b-ac59-4e4de0c273c3
question: |
  Write a function `item_count(seq, item)` that takes two arguments: a sequence and an item to be searched for in the sequence. The function returns the number of times that item occurs within the sequence.
code: |
  # your code goes here
tests: |
  assert item_count( [1, 2, 3, 2, 1], 1 ) == 2
  assert item_count( 'flabbergasted', 'b') == 2

---
type: coding-question
id: 24345456-8a4c-4d2e-8a2b-51f44e33e2d1
question: |
  Write a function `all_true` that takes a sequence as an input. It returns `True` if all items in the sequence are `True`. If even a single item is `False`, it returns `False`. Note: `''`, `0`, `[]`, `None` etc also evaluate to `False`.
code: |
  # your code goes here
tests: |
  assert all_true( ['all', 'true', 'list'] ) == True
  assert all_true( ['this', 'has', '', 'words'] ) == False
  assert all_true( [1, 23, 4, 9] ) == True
  assert all_true( [1, 23, 4, 9, 0] ) == False
