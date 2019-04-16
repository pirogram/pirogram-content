title: Class Variables
--- |
  We can define some variables at class level instead of at the object level. The class level variables are shared among all objects of that class. Consider the following example:
---
type: live-code
id: 15fdb621-0e5b-4873-8cc0-ba2919f474ac
code: |
  class Counter:
    total_counters = 0

    def __init__(self):
      self.current_value = 0

      Counter.total_counters += 1

    def increment(self):
      self.current_value += 1

    def decrement(self):
      self.current_value -= 1

  c1 = Counter()
  c2 = Counter()

  c1.total_counters, c2.total_counters
--- |
  In this example, `total_counters` is a class level variable. When it is updated, it must be accessed via the class (ref: `Counter.total_counters += 1`). However, when it is read, it could be accessed via the class (i.e. `print(Counter.total_counters)`) or via an object (i.e. `print(c1.total_counters)`).

---
type: testless-coding-question
id: e40cc28a-43af-401e-9fac-720b1c589822
question: |
  Define a class called `ObjectCounter`. In the `__init__` method of the class, print the total number of objects that have been created from this class. The interaction would look like the following:

  ```
  >>> ObjectCounter()
  Object #1 created.
  >>> ObjectCounter()
  Object #2 created.
  >>> ObjectCounter()
  Object #3 created.
  ```
code: |
  # your code goes here
