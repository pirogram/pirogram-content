title: Static Methods
--- |
  Just like class variables, there is a notion of static methods and class methods. These methods are defined at the class level and not the object level. There are a lot of good discussions on stackoverflow that discuss these methods:
  * [What is the difference between @staticmethod and @classmethod?](https://stackoverflow.com/questions/136097/what-is-the-difference-between-staticmethod-and-classmethod)
  * [Meaning of @classmethod and @staticmethod for beginner?](https://stackoverflow.com/questions/12179271/meaning-of-classmethod-and-staticmethod-for-beginner)

  Here is an example of staticmethod:

---
type: live-code
id: 2bb72ebd-765f-4fbe-91b6-27ccda5580dc
code: |
  class Counter:
    def __init__(self, initial_value):
      self.current_value = initial_value

    # returns an object of Counter class whose initial value is set to
    # a random number.
    @staticmethod
    def random_counter():
      import random
      return Counter(initial_value=random.randint(0, 100))

  c = Counter.random_counter()
  c.current_value
--- |
  In this example, the static method `random_counter` creates a Counter object that has been initialized to a random value between 0 to 100.

---
type: testless-coding-question
id: 786b8163-86fb-4e2a-b360-b87598911262
question: |
  Extend the following `Counter` class to add a static method `user_initialized_counter()`. This static method asks the user to enter the initial value of the counter. It then creates and returns an object of `Counter` class that's initialized to user specified value.
code: |
  class Counter:
    def __init__(self, initial_value):
      self.current_value = initial_value

    # your code goes here
---
type: coding-question
id: fb5caff3-2462-42e9-a119-c602c8ae9508
question: |
  Define a class `Person`. Add following static methods:
  * `can_drive`: takes person's age as input. If the age is 16 or above, return `True`. Otherwise, return `False`.
  * `can_vote`: takes a person's age as input. If the age is 18 or above, return `True`. Otherwise, return `False`.
code: |
  # your code goes here
tests: |
  assert Person.can_drive(age=16) == True
  assert Person.can_drive(age=15) == False
  assert Person.can_vote(age=18) == True
  assert Person.can_vote(age=17) == False
