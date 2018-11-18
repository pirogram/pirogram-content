title: Recursion
--- |
  Recursion is about solving a problem by a function calling itself in a recursive manner. Consider the following function that gives you the sum of numbers from `1` to `n`.

---
type: live-code
id: 342b02ac-81ff-4063-a5d0-78d7f432f9bd
code: |
  def sum_digits(n):
    if n == 0:
      return 0

    return n + sum_digits(n - 1)

  sum_digits(5)

--- |
  Here is another example of recursion. This function sums up all numbers in a list by using recursion.

---
type: live-code
id: e17fb17e-322b-4192-a6e5-53737d88e20a
code: |
  def sum_numbers(numbers):
    if len(numbers) == 1:
      return numbers[0]

    return numbers[0] + sum_numbers(numbers[1:])

  sum_numbers([4, 3, 2, 5])

---
type: testless-coding-question
id: c5e7fa5d-9c6b-4655-9681-0ba35f1bf7e7
question: |
  Write a function `print_items()` that takes a list of items as input. It prints each item on a separate line. Use recursion instead of iteration.
code: |
  items = ['a', 'laundry', 'list', 'of', 'items']

  # your code goes here

---
type: testless-coding-question
id: dc49c4f1-50c6-490e-9d69-e357e66817d2
question: |
  Write a function `reverse_print()` that takes a list of items as input. It prints each item on a separate line in the reverse order (last item is printed first). Use recursion instead of iteration.
code: |
  items = ['a', 'laundry', 'list', 'of', 'items']

  # your code goes here

---
type: coding-question
id: 822a7ae3-af3c-44c8-ab5f-49c98f43fa00
question: |
  Write a function `factorial(n)` that takes a number as argument. It returns the multiplication of digits from `1` to `n`. Use recursion instead of iteration.
code: |
  # your code goes here

tests: |
  assert factorial(5) == 120
  assert factorial(3) == 6

---
type: coding-question
id: 2e4bd84f-6039-4f34-b8fd-cd9eb96bd851
question: |
  Write a function `zero_count()` that takes a a list of numbers as input. It returns the number of zeros in the array. Use recursion instead of iteration.
code: |
  # your code goes here.

tests: |
  assert zero_count([1, 1, 4, 32]) == 0
  assert zero_count([1, 1, 0, 32]) == 1
  assert zero_count([1, 0, 0, 32]) == 2
