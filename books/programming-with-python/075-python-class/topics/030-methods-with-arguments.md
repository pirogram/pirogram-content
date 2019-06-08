title: Methods With Arguments
--- |
  Class methods can also receive arguments (just like regular functions). Here is an example with `Counter` class.

---
type: live-code
id: aa026c1d-f279-4078-b68a-922f0a1064ff
code: |
  class Counter:
    def __init__(self):
      self.current_value = 0

    def increment(self, value=1):
      self.current_value += value

      return self.current_value

  c = Counter()

  print('Increment:', c.increment())
  print('Increment by 5:', c.increment(5))

--- |
  In this example, the `increment()` and `decrement()` methods take the value by which `current_value` should be incremented or decremented. That value defaults to `1` when it is not provided by caller.

---
type: coding-question
id: 9333afdb-1e12-4600-8d1c-7d1836fa888d
question: |
  Implement a `Counter` class. An object of this class represents a counter which can be incremented or decremented. The counter always starts with `0`. Here are the operations supported by this class:
  * `increment` - takes `value` as an argument and increments the counter by given value. Returns the new value of the counter.
  * `decrement` - takes `value` as an argument and decrements the counter by given value. Returns the new value of the counter.
code: |
  # your code goes here.
tests: |
  c = Counter()
  assert c.increment(4) == 4
  assert c.increment(2) == 6
  assert c.decrement(1) == 5
  assert c.decrement(3) == 2

---
type: coding-question
id: 57d8a195-8ee3-4004-9c9d-1a50ba8a7ba6
question: |
  Extend the `Counter` class. Modify the `increment` and `decrement` methods such that `value` argument is optional. The `value` should default to `1` if not specified. For example,
  * `c.increment(2)` will increment the counter `c` by `2`.
  * `c.increment()` will increment the counter `c` by `1`.
code: |
  # your code goes here
tests: |
  c = Counter()
  assert c.increment(2) == 2
  assert c.increment() == 3
  assert c.decrement(2) == 1
  assert c.decrement() == 0

---
type: coding-question
id: 65fe5962-3890-4043-ab35-07c338b6dee1
question: |
  Think of a stack of items. When you put an item, it always goes to the top. When you remove an item, it always comes off the top. And you can see the item that's on the top but not the ones underneath. This is also called LIFO (Last In First Out).

  Write a class called `Stack`. This has a method `put(item)` that puts an item on top of the stack. Another method `pop()` removes the topmost item and returns it. If the stack is empty, `pop()` should return `None`. And yet another method `peek()` returns the item on top of the stack without removing it.

  Hint: inside the class, you can keep a `list`. To put an item on the list, you can use `.append()` method. To remove item from the list, you can use `.pop()` method.
code: |
  # your code goes here

tests: |
  s = Stack()

  s.put(1)
  s.put(2)
  assert s.peek() == 2
  assert s.pop() == 2
  assert s.peek() == 1
  s.put(3)
  assert s.pop() == 3
  assert s.pop() == 1
  assert s.pop() == None

---
type: coding-question
id: 16b1867e-7e60-4217-a18f-cd93404eab6a
question: |
  Define a class `Closet` that has three methods. The method `put(item, quantity)` puts those items in the closet. The method `remove(item, quantity)` removes that many quantities of the given item from the closet. The method `peek(item)` returns the current quantity of that item.

  A couple of nuances.
  * Calling `put()` multiple times for the same item will add the quantity of items. For example, calling `put('shirts', 5)` followed by `put('shirts', 3)` will make the total shirt count in closet 8.
  * Calling `remove()` with quantity as `0` will remove all quantities of the given item. For example, `remove('shirts', 0)` will remove all shirts from the closet.
  * An item cannot have less than 0 quantity in the closet.
  * If `peek()` is called for an item that was never placed in the closet, it still returns `0`.

  Hint: you can internally use a dictionary to keep track of items and their counts.
code: |
  # your code goes here
tests: |
  c = Closet()
  assert c.peek('shirts') == 0

  c.put('shirts', 5)
  c.put('shirts', 3)
  assert c.peek('shirts') == 8

  c.remove('shirts', 2)
  assert c.peek('shirts') == 6

  c.remove('shirts', 0)
  assert c.peek('shirts') == 0

  c.put('shirts', 9)
  c.put('shirts', 10)
  assert c.peek('shirts') == 0
