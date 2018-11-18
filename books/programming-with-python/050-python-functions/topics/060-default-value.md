title: Default Value
--- |
  Some of the arguments to a function can be optional. For such arguments, the functions can specify a default value.

---
type: live-code
id: f30aed11-eaf1-46c5-b613-6479d16dc1f2
code: |
  def diff(num1, num2, absolute=True):
    if absolute:
      return abs(num1 - num2)
    else:
      return num1 - num2

---
type: live-code
id: 322796ff-b114-4232-b95a-d4d445153cbd
code: |
  diff(3, 5)

---
type: live-code
id: bb183f55-7c21-4c25-ac64-326bd0b43987
code: |
  diff(3, 5, False)

--- |
  Let's look at some of the built-in functions in Python that make use of default values. First in line is `string.split()`
---
type: live-code
id: eb4e1ee3-46f6-4c9c-af05-5087f4b6d989
code: |
  'i am a sentence'.split()   # separator defaults to white space ' '

---
type: live-code
id: ceed213f-9ed3-4583-be46-51512c022ed0
code: |
  'comma,separated,words'.split(',')  # separator is provided

--- |
  Next, we look at `int()` function.
---
type: live-code
id: ecb160cc-32bb-4e0b-91d0-20c2cc972187
code: |
  int('12')   # base defaults to 10

---
type: live-code
id: 5fa80c24-b800-41dd-98e2-46b0bc9bfba0
code: |
  int('12', base=16)

---
type: coding-question
id: 8a82f341-643c-497b-9dd8-c83418764926
question: |
  Write a function `arrange()` that takes three arguments: `num1`, `num2` and `increasing`. If `increasing` is `True`, the function returns the numbers arranged in increasing order. Otherwise, it returns them arranged in decreasing order. By default, `increasing` is `True`.
code: |
  # your code goes here
tests: |
  assert arrange(5, 3) == (3, 5)
  assert arrange(3, 5) == (3, 5)
  assert arrange(3, 5, False) == (5, 3)

---
type: coding-question
id: 66224432-5c20-49ad-aec0-3d190cb8ae63
question: |
  Write a function `extreme_value()` that takes two arguments: a list of numbers and `pick_max`. If `pick_max` is `True`, it returns the largest number from list. Otherwise, it returns the smallest number from the list. `pick_max` defaults to `True`.
code: |
  # your code goes here
tests: |
  assert extreme_value([3, 2, 9, 4]) == 9
  assert extreme_value([3, 2, 9, 4], False) == 2
