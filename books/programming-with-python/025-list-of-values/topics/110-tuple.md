title: Tuple
--- |
  We'll now look at another way to organize a list of values: `tuple`. `tuple` is list-like data structure. The verbiage here could get confusing so, let's clarify the naming of things before we look at what `tuple` is.

  There is a general concept of _list-of-values_. Whenever you have multiple values organized as a list, you can call that list the _list-of-values_. Now, to work with _list-of-values_, Python has multiple data structures (or data types if you prefer to call it that). One of those data structure is called `list` (which is what we studied so far) and another of those data structure is called `tuple`.

  `list` as well as `tuple` data structures can be used to organize a list of values and work with the same. The only noticeable difference between `tuple` and `list` is that lists are mutable (i.e. they can be modified) while tuples are immutable (i.e. once created, they cannot be modified).

  Following examples demonstrate the syntax of tuples and how they are list like:

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

  Tuples provide efficient ways of packing and unpacking values. You can achieve the same with list also but tuples are computationally light-weight compared to lists.

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
  You can pack and unpack the values using lists also:
---
type: live-code
id: 811520d9-a6d0-4675-af50-8e8d61e9fbbd
code: |
  [a, b, c] = [5, 6, 7]

  print('a:', a)
  print('b:', b)
  print('c:', c)
--- |
  While the same packing/unpacking is achievable with lists, the syntax of tuples is more intuitive as opposed to the one for lists.

  What could be the real world use of packing/unpacking values? Let's look at a real world example. Python has a function called `enumerate()` that is often used in list iteration. We'll first see it in action and then understand what it is doing:
---
type: live-code
id: e1c41d4a-288e-49d5-bd2e-eb46aec1b6a6
code: |
  fruits = ['apple', 'pineapple', 'orange', 'guava']

  for k in enumerate(fruits):
    print(k)
--- |
  If you run this code, you'll see that by wrapping a list within `enumerate()`, you get a sequence of tuples instead of the list items. The first element of tuple is the index number and second element of tuple is the actual element. In a way, `enumerate()` function _packs_ two values: index & list item. You can unpack it in a single shot during iteration:

---
type: live-code
id: 42f7323c-22a8-4248-8366-1c8f0ad169c9
code: |
  fruits = ['apple', 'pineapple', 'orange', 'guava']

  for index, fruit in enumerate(fruits):
    print(fruit, 'is at index', index)

--- |
  Now we look at another interesting application of a tuple: swapping the values of variables.
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
