title: Multiple Return Values
--- |
  You can have a function return multiple values instead of just one. Here is a function that takes two numbers as input, it returns them in the increasing order.

---
type: live-code
id: b03e943b-9a3e-4f96-9ff1-70f6313e3ea1
code: |
  def increasing(a, b):
    if a < b:
      return a, b
    else:
      return b, a

  increasing(20, 10)
---
type: live-code
id: 7b547e79-2b3c-487e-9bae-ff9d9cb9e5ae
code: |
  smaller, bigger = increasing(2, 5)
  print('smaller ->', smaller)
  print('bigger ->', bigger)

---
type: live-code
id: a09557f7-7464-42fc-b421-97f99359e1c0
code: |
  smaller, bigger = increasing(5, 2)
  print('smaller ->', smaller)
  print('bigger ->', bigger)

---
type: coding-question
id: 277bbc94-46d2-4fe9-92cd-89b4d4da9f6c
question: |
  Write a function `decreasing()` that takes two numbers as input. It returns the numbers in decreasing order.
code: |
  # your code goes here
tests: |
  assert decreasing(10, 20) == (20, 10)
  assert decreasing(20, 10) == (20, 10)

---
type: coding-question
id: 00d466e0-6945-480c-b1fa-36fe88d0692c
question: |
  Write a function `min_max()` that takes a sequence as an input. It returns the smallest and the largest items from the sequence.
code: |
  # your code goes here
tests: |
  assert min_max( [4, 3, 9, 23, 11] ) == (3, 23)
  assert min_max( 'harry' ) == ('a', 'y')

---
type: coding-question
id: 48e2f816-31d6-4001-8dd8-5f02e646afb7
question: |
  Write a function `diff_sum()` that takes two numbers as input. It returns the difference between two numbers as well as the sum of two numbers. Note, the difference between `(4, 6)` as well as `(6, 4)` is `2`.
code: |
  # your code goes here
tests: |
  assert diff_sum(4, 6) == (2, 10)
  assert diff_sum(5, 5) == (0, 10)
  assert diff_sum(6, 4) == (2, 10)
