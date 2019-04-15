title: Methods
--- |
  We'll now add some methods to our class. Let's say, in our program, we are working with lots of square shaped things. So, we define a class called `Square` which looks like following:

---
type: live-code
id: 46b838d6-d056-4c28-bef9-95f5363812c5
code: |
  class Square:
    def __init__(self, side)
      self.side = side

    def perimeter(self):
      return 4 * self.side

    def area(self):
      return self.side * self.side


  s = Square(3)

  print("Perimeter:", s.perimeter())
  print("Area:", s.area())
--- |
  The `__init__` method of the class `Square` takes an argument `side` which is the length of each side of the square. This class also has methods `perimeter` and `area` that return the perimeter and the area of the square.

  The syntax for invoking a class method is `object.method()`. All methods defined in a class receive the calling object as first argument.

---
type: coding-question
id: 56024afb-4bd3-4f31-ae51-ede73daec08e
question: |
  Define a class `Rectangle` whose `__init__` method takes two arguments: `length` and `width`. Also, implement `perimeter` and `area` methods within the class.
code: |
  # your code goes here
tests: |
  r = Rectangle(length=2, width=4)

  assert r.perimeter() == 12
  assert r.area() == 8
