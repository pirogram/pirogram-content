title: Tuple
--- |
  Tuples are like immutable lists. They support all operations that lists support except that once created, tuples cannot be modified.

  Following example shows the list-likeness of tuples. Try playing with the index numbers.

---
type: live-code
id: c56d2e82-ed6b-49d9-aaa4-fe64c4132fcf
code: |
  # note: we use `()` for tuples unlike `[]` for lists.
  one_to_ten = (1, 2, 3, 4, 5, 6, 7, 8, 9, 10)
  one_to_ten[2]
---
type: live-code
id: 7a107742-01a1-4316-8fb0-42bcddb9a927
code: |
  one_to_ten = (1, 2, 3, 4, 5, 6, 7, 8, 9, 10)
  one_to_ten[-3]
---
type: live-code
id: e18a129d-ca96-4293-8893-c647a53251dc
code: |
  # you can even skip the `()` for tuples and just provide
  # comma separated values to create a tuple.
  fruits = 'apple', 'pineapple', 'orange', 'guava'

  fruits

--- |
  In a way, tuples may seem inferior to lists. `list` can do everything that a `tuple` can do and much more because a `list` can also be modified (elements added, removed, reordered etc).

  The main usage of tuples is in packing and unpacking values. Let's look at an example:

---
type: live-code
id: 3e64e01e-701b-4796-9d66-1ac151a64851
code: |
  # pack some numbers into a tuple
  numbers = 5, 6, 7

  # unpack the tuple into variables
  a, b, c = numbers

  print('a:', a)
  print('b:', b)
  print('c:', c)

---
type: live-code
id: 83dd468d-f135-4442-95a6-88ad92790933
code: |
  # you can pack and unpack in a single step!
  a, b, c = 5, 6, 7

  print('a:', a)
  print('b:', b)
  print('c:', c)

--- |
  Now we look at one of the most interesting application of a tuple: swapping the values of variables.

---
type: live-code
id: f12c2f27-ba0d-42a4-9dbb-6413b9d7b4f9
code: |
  a, b = 1, 2

  print('[before swap] a:', a)
  print('[before swap] b:', b)

  # can we swap the values of a & b?
  a, b = b, a

  print('[after swap] a:', a)
  print('[after swap] b:', b)

---
type: testless-coding-question
id: 18d9a76b-b145-4579-91b6-111136238ed7
question: |
  Swap the values of variables `c` and `d` using tuple assignment.

code: |
  c = 4
  d = 6

  # your code goes here

---
type: testless-coding-question
id: 1db22d28-bf4f-44ae-9a99-f8443165d31d
question: |
  Swap the values so that `a` takes the value of `b`, `b` takes the value of `c`, `c` takes the value of `d` and `d` becomes 0.

code: |
  a, b, c, d = 1, 2, 3, 4

  # your code goes here
