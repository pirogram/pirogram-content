title: Initializing An Object
--- |
  When an object is created, it can be initialized with some values. Here is an example:
---
type: live-code
id: 5527f372-a813-468a-ae77-c68a103535a7
code: |
  class Todo:
    def __init__(self, init_text, init_done):
      self.text = init_text
      self.done = init_done

  todo = Todo(init_text='Clean House', init_done=False)

  print('text:', todo.text)
  print('done:', todo.done)

--- |
  When an object is created, the `__init__` method within that class is called. The first argument of a class method is the object it is called upon. And subsequent arguments are the ones that were passed to the method. The `__init__` method leads to a more intuitive way to create and initialize an object.

  Just like regular functions, the `__init__` method can have default values its arguments. In this case, it makes sense to default `init_done` to `False`.

---
type: live-code
id: 84a09351-9682-49a6-af3d-45fe0ef837a3
code: |
  class Todo:
    def __init__(self, init_text, init_done=False):
      self.text = init_text
      self.done = init_done

  todo = Todo(init_text='Clean House')

  print('text:', todo.text)
  print('done:', todo.done)

---
type: coding-question
id: d00acc8a-77be-4cec-b62f-601d14a2afba
question: |
  You are given the class `Rectangle`. Create an object `r` of this class with width 4 and length 8.
code: |
  class Rectangle:
    def __init__(self, length, width):
      self.length = length
      self.width = width

  # your code goes here

tests: |
  assert r.length == 8
  assert r.width = 4.

---
type: coding-question
id: 8f89fa8c-b8bb-4adf-8efc-ac18631197b1
question: |
  Define a class `Book`. The `__init__` method should set the `title` and `author` attributes.
code: |
  # your code goes here
tests: |
  b = Book(title='Lord of the Rings', author='Tolkein')
  assert b.title == 'Lord of the Rings'
  assert b.author == 'Tolkein'

---
type: coding-question
id: 48487908-0c22-4ddf-aac4-fc3cdcf3607f
question: |
  Define a class `Subject`. The `__init__` method should set the `name` and `teacher` attributes.
code: |
  # your code goes here
tests: |
  s = Subject(name='Defense against the dark arts', teacher='Snape')
  assert s.name == 'Defense against the dark arts'
  assert s.teacher = 'Snape'
