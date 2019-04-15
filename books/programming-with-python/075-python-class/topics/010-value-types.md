title: Value Types
--- |
  All values that we work have a type (usually called the data type) and we have worked with many different types of values so far. For example, `4` is an `int` type. `4.0` is a `float` type. `'4'` is a `str` type. `[1, 2, 3, 4]` is also a value of type `list`. `{'apples': 2, 'kiwi': 4}` is also a value of type `dict`.

  Some times, we would like to create a new value type. For example, we worked on building a todo application where a todo item has two attributes: the item and state (i.e. whether it is done or not). We can use a dictionary to achieve the same. For example:

type: live-code
id: 9209aae7-3c30-432f-9f3a-30849afe0b1e
code: |
  todo = {}
  todo['text'] = 'Clean house'
  todo['done'] = False

  print('text:', todo['text'])
  print('done:', todo['done'])
  print('type:', type(todo))
--- |

  Alternatively, we can create a new value type called `Todo`. We do this by using `class`:
---
type: live-code
id: 4adda9a6-d7f1-4e68-b171-0071693d20c0
code: |
  class Todo:
    pass

  todo = Todo()
  todo.text = 'Clean house'
  todo.done = False

  print('text:', todo.text)
  print('done:', todo.done)
  print('type:', type(todo))
--- |
  In this code, we have defined a new value type: `Todo`. This value type has two attributes: text & done.

  We can also create multiple todo items:
---
type: live-code
id: 4133eab8-996b-41d7-a51f-ddae6f116275
code: |
  class Todo:
    pass

  todo1 = Todo()
  todo1.text = 'Clean house'

  todo2 = Todo()
  todo2.text = 'Buy milk'

  print('1. text:', todo1.text)
  print('2. text:', todo2.text)
--- |
  From a vocabulary perspective, `Todo` is a class and `todo1`, `todo2` etc are called objects of the class `Todo`.
---
type: multiple-choice-question
id: bb9d3425-68c2-4eb3-881c-7e6fc21ecca4
question: |
  Based on the following code snippet, select the statements that are true.

  ```Python
  class GroceryItem:
    pass

  item1 = GroceryItem()
  item1.name = 'apples'
  item1.quantity = 4

  item2 = GroceryItem()
  item2.name = 'kiwi'
  item2.quantity = 2
  ```
options:
  - text: |
      `item1` and `item2` are objects of the class `GroceryItem`.
    correct: true
  - text: |
      `GroceryItem` is an object.
  - text: |
      `item1.name` is `apples` and `item1.quantity` is `4`.
    correct: true
  - text: |
      `item2.name` is `kiwi` and `item2.quantity` is `0`.

---
type: testless-coding-question
id: 9df7a718-ff5c-41c4-b412-551812876e12
question: |
  Define a class `Book`. Create two objects of this class `book1` and `book2`. Set the `title` attribute of `book1` to `Fellowship of the Ring` and that of `book2` to `Return of the King`.
code: |
  # your code goes here

---
type: testless-coding-question
id: b1383198-2c33-4356-96b7-c2b2a205b406
question: |
  Define a class `Subject` and create two objects of this class: `s1` and `s2`. Set the `name` attribute of `s1` to `Physics` and that of `s2` to `Mathematics`.
code: |
  # your code goes here
