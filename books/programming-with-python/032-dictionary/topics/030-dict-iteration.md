title: Dict Iteration
--- |
  In a way, `dict` is a little bit list-like. For example, consider the following dictionary:

  ```Python
  students = {
    'Harry': 90,
    'Hermione': 85,
    'Ron': 92,
    'Malfoy': 91
  }
  ```

  We can think of three different lists here:
  * *keys:* `['Harry', 'Hermione', 'Ron', 'Malfoy']`
  * *values:* `[90, 85, 92, 91]`
  * *items (or key-values):* `[('Harry', 90), ('Hermione', 85), ('Ron', 92), ('Malfoy', 91)]`

  Even though, a `dict` is not a list, it does allow us to iterate through these 3 list-like things: _keys_, _values_ and _items_. This is what it looks like:
---
type: live-code
id: 85d29a83-801c-48d1-ba9b-62bc2c1879cd
code: |
  students = { 'Harry': 90, 'Hermione': 85, 'Ron': 92, 'Malfoy': 91 }

  for name in students:
    print(name)
--- |
  We can also modify this example so that we can print the student name as well as the height in one go:
---
type: live-code
id: c38e66d1-b241-476a-80e1-77a31eab1e72
code: |
  students = { 'Harry': 90, 'Hermione': 85, 'Ron': 92, 'Malfoy': 91 }

  for name in students:
    print(name, ':', students[name])
--- |
  If we would like to iterate through values, there is a way to do that as well:
---
type: live-code
id: d303a812-a8f5-4f08-ab94-2213c9de73db
code: |
  students = { 'Harry': 90, 'Hermione': 85, 'Ron': 92, 'Malfoy': 91 }

  for height in students.values():
    print(height)

--- |
  `dict.values()` gives a list-like thing that helps us iterate through the values within the `dict`. Iterating through the values is generally less useful because you can't reverse-map it to the key. However, there are times when it comes handy.

  And as I mentioned earlier, we can also iterate through the items (i.e. key-value pairs) of the dictionary.
---
type: live-code
id: dc53c2a9-2484-45b8-bdcd-afc31777cc59
code: |
  students = { 'Harry': 90, 'Hermione': 85, 'Ron': 92, 'Malfoy': 91 }

  for item in students.items():
    print(item)

--- |
  If you run the above code, you'll notice that `item` is a `tuple`. First element of the `tuple` is key and the second element is value. And if you remember from [`tuple`](/@list-of-values/tuple), you can unpack a tuple into different variables. For example, look at the following code:

---
type: live-code
id: 892dfc20-47e3-4b7f-a30c-42600215e16b
code: |
  item = ('Harry', 90)
  name, height = item

  print(name, ':', height)
--- |
  In this example, `item` is a `tuple` and we unpacked it into two variables: `name` and `height`. Similarly, we can unpack the `item` tuple while iterating through `dict.items()`:
---
type: live-code
id: df7b4352-4c7f-4c00-bca5-88bd23520667
code: |
  students = { 'Harry': 90, 'Hermione': 85, 'Ron': 92, 'Malfoy': 91 }

  for name, height in students.items():
    print(name, ':', height)

---
type: testless-coding-question
id: 41e74eb6-3286-4ad2-9cc2-bb4fdd6fe93c
question: |
  For the given dictionary, print all the keys in the dictionary.
code: |
  grocery_items = { 'potatoes': 20, 'tomatoes': 12, 'eggs': 18, 'apples': 6 }

  # your code goes here

---
type: testless-coding-question
id: 6294744d-d94d-42a0-a70f-2c05dcfae66a
question: |
  For the given dictionary, print all key-value pairs. It should print something like:
  ```
  potatoes : 20
  tomatoes : 12
  eggs : 18
  apples : 6
  ```
code: |
  grocery_items = { 'potatoes': 20, 'tomatoes': 12, 'eggs': 18, 'apples': 6 }

  # your code goes here
---
type: testless-coding-question
id: 2b953272-991a-49ac-b407-a829a394911a
question: |
  Update the quantity of grocery items so that anything that's 0 becomes 1.
code: |
  grocery_items = {
    "milk": 0,
    "eggs": 24,
    "bread": 1,
    "cheese": 0
  }

  # your code goes here.
---
type: testless-coding-question
id: a59e94d1-f5a0-474b-9df9-54d1c6739b17
question: |
  Given two dictionaries of grocery items, create a third dictionary that has the items from both the dictionaries. For example: given `{'milk': 1, 'eggs': 6}` and `{'bread': 3, 'cheese': 12}`, create a new dictionary `{'milk': 1, 'eggs': 6, 'bread': 3, 'cheese': 12}`
code: |
  d1 = {'milk': 1, 'eggs': 6, 'cheerios': 1}
  d2 = {'bread': 3, 'cheese': 12, 'salsa': 2}

  # your code goes here.

---
type: testless-coding-question
id: 3a96176c-6bd5-4105-9c87-69ba64bfeaa8
question: |
  Given two dictionaries of grocery items, create a third dictionary that has items from the both the dictionaries. If an item is found in both the dictionaries, add up the quantity in the resulting dictionary. For example, if you are given `{'bread': 1, 'eggs': 6}` and `{'cheese': 12, 'eggs': 12}`, the resulting dictionary is `{'bread': 1, 'eggs': 18, 'cheese': 12}`.
code: |
  d1 = {'milk': 1, 'eggs': 6, 'cheerios': 1, 'cheese': 6, 'bread': 1}
  d2 = {'bread': 3, 'cheese': 12, 'salsa': 2, 'eggs': 12}

  # your code goes here
