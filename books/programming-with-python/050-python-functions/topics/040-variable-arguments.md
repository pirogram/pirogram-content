title: Variable Positional Arguments
--- |
  Functions can also take variable number of arguments. In the following function, `args` is a `tuple` of all arguments passed to the function.

---
type: live-code
id: 4a806b47-567e-483c-9cfd-8f0aec77a1de
code: |
  def var_args(*args):
    print(args)

  var_args(4, 5, 6)

--- |
  How is it useful? We can simplify functions like `sum()` to take a list of variable number of arguments instead of a list. Example, compare the following two implementations of `my_sum()`.

---
type: live-code
id: b93eeac4-e940-42c7-a7a6-81add1c3a8f4
code: |
  def my_sum(numbers):
    total = 0
    for number in numbers:
      total += number

    return total

  my_sum([1, 2, 3])

---
type: live-code
id: dbb39295-94ba-4080-9f23-f2717aa3b47a
code: |
  def my_sum(*numbers):
    total = 0
    for number in numbers:
      total += number

    return total

  my_sum(1, 2, 3)

--- |
  Both the approaches work. As you develop large programs, you'll find need for both the variants from time to time. For now, suffice it to say that variable arguments approach is useful.

  Let's look at a variation and create a new function called `greet()`. It takes a salutation and a tuple of names to greet.

---
type: live-code
id: a5967e62-e506-467b-8b49-eb2b174c296d
code: |
  def greet(salutation, *names):
    for name in names:
      print(salutation, name)

  greet('Hi', 'Harry', 'Dumbledore', 'Ron')

--- |
  In this example, the first argument goes into `salutation` and the remaining arguments get accumulated into `names` tuple. We could have also written it as:

---
type: live-code
id: 7fca6bb2-a3f2-4f8a-a80a-67e1f3e6c1b7
code: |
  def greet(salutation, names):
    for name in names:
      print(salutation, name)

  greet('Hi', ['Harry', 'Dumbledore', 'Ron'])

---
type: coding-question
id: b56b6901-ad69-480f-96df-212276da3713
question: |
  Write a function `min_number()` that takes variable number of arguments. It returns the smallest number.
code: |
  # your code goes here.
tests: |
  assert min_number(4, 3, 2, 9) == 2
  assert min_number(4, 2, 2, 1, -1) == -1

---
type: coding-question
id: b65723a4-e36b-42f1-93c6-f65722375817
question: |
  Write a function `max_number()` that takes variable number of arguments. It returns the largest number.
code: |
  # your code goes here
tests: |
  assert max_number(4, 3, 2, 9) == 9
  assert max_number(4, 2, 2, 1, -1) == 4

--- |
  We'll now study a slightly different usage of `my_sum()` function that we worked with earlier.

---
type: live-code
id: c909142f-bfed-4070-bd7c-a139722106c6
code: |
  def my_sum(*numbers):
    total = 0
    for number in numbers:
      total += number

    return total

  numbers = [1, 2, 3]
  my_sum(*numbers)

---
type: testless-coding-question
id: 202929f2-d9d6-4c41-a79e-315006f85f1f
question: |
  Write a function `min_number()` that takes variable number of arguments. It returns the smallest number. Now, ask the user to enter a comma separated list of numbers. Use the `min_number()` function to print the smallest of those numbers.
code: |
  # your code goes here

---
type: testless-coding-question
id: 7dbd6fee-273b-4772-a897-e5b50fccfd43
question: |
  Write a function `max_number()` that takes variable number of arguments. It returns the largest number. Now, ask the user to enter a comma separated list of numbers. Use the `max_number()` function to print the largest of those numbers.
code: |
  # your code goes here
